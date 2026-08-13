# Jneopallium — LF AI & Data Sandbox Project Proposal

* **Name of proposed project:**

  Jneopallium

* **Requested project maturity level [Graduation or Incubation or Sandbox]:**

  **Sandbox.** The project is a mature codebase (started 2018, 47 Maven modules, ~1,600 Java
  source files, 127 test classes) but a small community (a single principal maintainer, 8 GitHub
  stars at the time of writing). Sandbox is the honest and appropriate entry stage: the project
  seeks LF AI & Data hosting precisely to build the multi-organization contributor base and the
  neutral governance that Incubation requires.

* **Project description [what it does, why it is valuable, origin and history, ongoing development]:**

  **What it does.** Jneopallium is a Java framework for modelling natural neuron networks at a
  *user-chosen* level of biological detail. It decouples neuron-network processing logic from the
  concrete neuron and signal types — the same way `java.util.Collections` decouples container
  algorithms from the elements they hold — via generics and interfaces. A model author defines:

  1. **Functional logic** — arbitrary signal types (`ISignal`), neuron receptor interfaces
     (`INeuron`), and stateless processors (`ISignalProcessor<S, N>`) that pair one signal type
     with one receptor. A neuron implementing several receptor interfaces has several receptors,
     using plain Java multiple-interface inheritance.
  2. **Structural logic** — topology generated from per-layer neuron-class appearance
     probabilities, vertical adjacency constraints (`NeighboringRules`), and a pluggable
     `IConnectionGenerator`. Layers can be resized at runtime through `LayerManipulatingNeuron`.
  3. **I/O logic** — any number of input sources (`IInitInput`) and output sinks
     (`IOutputAggregator`), each with its own processing frequency; one network's output can be
     wired as another network's input (`INeuronNetInput`).

  Three distinguishing capabilities:

  - **Heterogeneous signal processing.** A network is not restricted to one kind of signal or one
    kind of neuron. Arbitrarily many signal types coexist in the same network, each with its own
    propagation characteristics, and each is handled by its own processor. Receptor heterogeneity
    falls out of the type system: a neuron implementing several receptor interfaces has several
    receptors, and each `ISignalProcessor<S, N>` binds exactly one signal type to one receptor
    interface, so the same neuron responds to a bioelectric spike, a neuromodulator and a
    domain-specific measurement through three independent, separately-testable code paths. An
    ordered `ISignalChain` determines the pipeline invoked on activation. The consequence is that
    heterogeneity is expressed in ordinary Java types rather than encoded into a tensor layout:
    adding a new signal class to an existing model is an additive change that leaves every
    unrelated processor untouched, and the engine resolves the classes at runtime by
    fully-qualified name, so the engine itself never depends on any of them at compile time.
  - **Multi-timescale scheduling, per signal type.** Two nested loops give the coarse structure: a
    *fast* loop runs every tick, and a *slow* loop runs every N fast ticks, with N controlled at
    runtime by a `CycleNeuron`. The finer structure is what matters: **inside both loops, every
    individual signal type carries its own processing frequency.** Each signal type and each input
    source declares a `ProcessingFrequency(loop, epoch)` — `loop` selects the fast or slow loop,
    `epoch` divides that loop further, so a signal with `epoch = 3` on the fast loop is processed
    every third tick, and a signal with `epoch = 10` on the slow loop is processed every 100 ticks
    at N = 10. A single configuration therefore expresses a whole hierarchy of natural timescales
    simultaneously — sensorimotor spikes at every tick, slower integrative signals every few ticks,
    neuromodulatory diffusion two or three orders of magnitude slower — rather than forcing one
    uniform update step on the entire network. This is what makes the ~100–1000× speed gap between
    bioelectric conduction and neuromodulator diffusion representable, and the frequencies are
    reconfigurable at runtime rather than fixed at build time.
  - **A safety-gated bridge framework.** Every adapter between an external real-world system and
    the signal pipeline is a *bridge*, and all bridges implement one shared write algorithm —
    interlock → override → clamp → rate-limit → diff-suppress → audit — enforced by a template
    method in the `bridge-api` module. Every write emits an audit record whether it was applied,
    clamped, or rejected, and every bridge starts each loop in `SHADOW` mode. Each protocol
    declares a structural safety ceiling (READ-ONLY, EXPORT-ONLY, ADVISORY, SIM-ONLY, or
    AUTONOMOUS) that is enforced both at configuration load and at runtime. Bridges shipped or
    specified today cover OPC UA, Apache PLC4X, MQTT/Sparkplug B, FMI/FMU, ROS 2/DDS, Lab
    Streaming Layer, HL7 FHIR, DICOM, Apache Kafka, OpenTelemetry, Eclipse Ditto, IEC 61850,
    MAVLink, CANopen, LTI/xAPI, and Nengo.

  On top of the engine the project ships 14 domain modules (industrial, security, ad-fraud, swarm,
  clinical, BCI, tutoring, affect, glia, sleep, curiosity, embodiment, LLM, AGI) and an
  autonomous-agent architecture: 16 signal types (bioelectric fast-loop signals plus dopamine,
  serotonin, norepinephrine, acetylcholine and GABA neuromodulators on the slow loop), 28 neuron
  classes across 8 layers, 11 signal processors, a loop-prevention subsystem with four graduated
  circuit-breaker strategies, and a human-harm discriminator. The harm discriminator is a
  *consequence model* rather than an output filter: it simulates a projected action, scores it
  across five welfare dimensions (physical safety, psychological wellbeing, autonomy, social harm,
  long-term consequences) and vetoes the action before execution, with a set of structurally
  inviolable hard constraints. An optional LLM knowledge-base integration lets a network consult a
  local (Ollama) or hosted LLM as an advisory oracle — restricted to the slow loop so it can never
  block real-time sensorimotor processing, cross-validated against internal models before use, and
  designed so the network operates at full capability when the LLM is unavailable.

  **Why it is valuable.** Mainstream ML frameworks fix the abstraction (dense tensors, a small set
  of activation functions, one signal type) and optimise it. High-detail neuroscience simulators
  such as NEURON and CoreNeuron fix the opposite end (biophysically exact compartment models).
  Jneopallium deliberately occupies the space between: the abstraction depth is a parameter the
  modeller chooses. That makes it useful for (a) computational-neuroscience work that needs
  neuromodulatory and multi-timescale dynamics without full biophysical cost, (b)
  biologically-inspired AI research on architectures that are not gradient-descent-shaped, and
  (c) — via the bridge framework — cyber-physical applications where an AI system touches
  industrial, clinical, aerial, or grid equipment and every actuation must be interlocked,
  clamped, vetoable, and auditable by construction. The safety and auditability work is the part
  we believe is most immediately reusable by the wider LF AI & Data community, independent of the
  neuron model.

  **Origin and history.** The project was started in June 2018 by Dmytro Rakovskyi (Kharkiv,
  Ukraine) as a framework to express neuron-network structures that fixed-abstraction libraries
  could not represent. The approach was published in the *International Journal of Science and
  Research (IJSR)*, Vol. 13 Issue 7, July 2024 — "Framework for Natural Neuron Network Modeling:
  The Jneopallium Approach", DOI [10.21275/SR24703042047](https://dx.doi.org/10.21275/SR24703042047),
  ISSN 2319-7064. Roughly 700 commits have landed since. The core engine and the HTTP distributed
  mode are complete; the codebase has passed pre-alpha and the architecture is considered stable.

  **Ongoing development.** Current work: gRPC cluster mode (in progress), Kafka input source,
  first Maven Central release under `io.github.rakovpublic.jneopallium` (the release profile and
  signing pipeline have just landed), hosted Javadoc, Docker/Kubernetes packaging, and a graphical
  neuron-net designer. Nine runnable demo suites exercise the framework end-to-end — industrial
  cascade control, pump-fleet predictive maintenance, substation protection monitoring, drone
  geofence supervision, ICU deterioration early warning, BCI motor-imagery cursor control, digital
  twin anomaly advisory, adaptive tutoring, and an autonomous agent sandbox — each producing
  deterministic JSONL traces, safety summaries, and audit artifacts for review.

* **Statement on alignment with LF AI’s mission:**

  LF AI & Data exists to build and support an open AI and data community, and to drive open source
  innovation in AI, data and analytics by enabling collaboration and the creation of new
  opportunities for all participants. Jneopallium aligns on three axes:

  1. **Open, vendor-neutral innovation in AI.** The framework is permissively licensed
     (BSD 3-Clause), has no proprietary dependencies (prohibited by project policy), and targets a
     research direction — programmable-abstraction, multi-timescale, neuromodulatory neural
     modelling — that is not represented in the current LF AI & Data portfolio. It complements
     rather than duplicates existing hosted projects.
  2. **Trusted and responsible AI.** LF AI & Data's Trusted AI committee works on
     fairness, robustness and explainability of models. Jneopallium contributes a different and
     complementary layer: *actuation-time* trust. The universal write algorithm, per-protocol
     safety ceilings, `SHADOW`-mode defaults, override registry, mandatory audit records, and the
     pre-execution harm veto are mechanisms for making an AI system's effects on the physical
     world constrained and reviewable. We would like to develop this work in the open, under
     neutral governance, with input from the Trusted AI community.
  3. **Community growth.** The project has one principal maintainer and needs exactly what the
     Foundation provides: a neutral home, a path to multi-organization contribution, and the
     discipline of the OpenSSF Best Practices programme. The governance groundwork has been done
     rather than merely promised — `GOVERNANCE.md`, `MAINTAINERS.md`, `RELEASES.md`, `SUPPORT.md`,
     `SECURITY.md`, `CODEOWNERS` and DCO enforcement in CI are all in the repository, and the
     governance model is explicitly written to expire its own single-maintainer clauses as soon as
     more maintainers exist. What remains — the Technical Charter, the Project Contribution
     Agreement, LF co-ownership, 2FA enforcement and the OpenSSF badge registration — the
     maintainer commits to completing on acceptance.

* **Describe identified possible collaboration opportunities with current LF AI hosted projects:**

  - **Adversarial Robustness Toolbox / AI Fairness 360 / AI Explainability 360 (Trusted AI).** The
    strongest fit. Jneopallium's harm discriminator and bridge audit trail address trust at the
    point of action; ART/AIF360/AIX360 address trust at the point of prediction. Joint work could
    define a common vocabulary and artifact format for "why was this action taken, and what was
    rejected" across model-level and actuation-level assurance, and expose Jneopallium's
    transparency JSONL traces to AIX360-style explanation tooling.
  - **ONNX.** Jneopallium networks are not tensor graphs, so full ONNX export is not the goal.
    However, models frequently embed conventional sub-networks (for example the CNN-style patch
    recogniser in the UAV demo). A bounded ONNX import path — running an ONNX sub-model inside a
    Jneopallium signal processor — is a concrete, well-scoped integration, and would let ONNX
    models participate in a safety-gated actuation chain.
  - **Marquez / OpenLineage / Egeria.** Every bridge write already emits a structured
    `BridgeAuditRecord`. Emitting those as OpenLineage events, and describing bridge bindings as
    Egeria metadata, would give cyber-physical AI deployments end-to-end lineage from sensor tag
    to actuator write — something these projects currently cover for data pipelines but not for
    control loops.
  - **Milvus.** The memory and LLM knowledge-base subsystems currently use in-process caching.
    Milvus is the natural backing store for episodic memory retrieval and for the
    `LLMKnowledgeNeuron` cache, and would replace bespoke code with a hosted-project dependency.
  - **Adlik / IREE / Kompute.** The project's roadmap includes FPGA targets through the gRPC
    cluster mode. Adlik's model-compilation and inference-deployment work, IREE's compiler
    targets, and Kompute's GPU backend are all plausible acceleration paths for the per-tick
    processor execution.
  - **DeepCausality.** The harm discriminator's consequence model is, in effect, a hand-rolled
    causal simulator. DeepCausality's causal-reasoning primitives are a candidate replacement or
    cross-validation reference for that component.
  - **Flyte / Kedro.** Reproducible orchestration of the demo suites and of multi-run
    parameter sweeps; the demos already emit deterministic manifests, which maps cleanly onto both
    projects' reproducibility models.
  - **NNStreamer.** Edge sensor pipelines feeding Jneopallium input sources on embedded targets.

* **License name, version, and URL to the license text:**

  BSD 3-Clause "New" or "Revised" License (SPDX: `BSD-3-Clause`), an OSI-approved license.

  - Project copy: https://github.com/rakovpublic/jneopallium/blob/master/LICENSE.MD
  - Canonical text: https://opensource.org/license/bsd-3-clause

* **URL to location of source code (GitHub, etc.):**

  - Primary: https://github.com/rakovpublic/jneopallium
  - Mirror: https://gitlab.com/rakovpublic/jneopallium

* **Please list tools in use by the project:**

  | Purpose | Tool |
  | --- | --- |
  | Language / runtime | Java 17 (LTS) |
  | Build | Apache Maven 3.9+ (47-module reactor, aggregator POM) |
  | CI | GitHub Actions — `maven-verify` (`mvn -B -U clean verify` on JDK 17 / Temurin, on every push to `master` and every pull request) and `dco` (sign-off validation on every pull request) |
  | Static analysis / security | GitHub CodeQL workflow; Dependabot dependency updates |
  | Testing | JUnit 5, Mockito, Maven Surefire (unit) and Failsafe (integration), plus a dedicated `integration-tests` module for cross-domain tests |
  | Artifact publishing | `central-publishing-maven-plugin` with GPG signing, source and Javadoc jars (Maven Central, `io.github.rakovpublic.jneopallium`) |
  | Serialization / RPC | Protocol Buffers + gRPC, Jackson, Gson |
  | Logging | Log4j 2 over SLF4J |
  | Demo tooling | POSIX shell and PowerShell runner scripts, Python plant simulators for the FMI demo |
  | Docs | Markdown in-repo (`doc/`, `docs/`), per-module and per-bridge specifications |

* **Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use.**

  **GitHub Issues**, on https://github.com/rakovpublic/jneopallium/issues. Confirmed in use.
  Bug-report, feature-request and custom issue templates are configured under
  `.github/ISSUE_TEMPLATE/`. The project will remain on GitHub Issues; no migration is requested.

* **Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use:**

  In use today: GitHub Issues and pull requests, and direct email to the maintainer
  (rakovpublic@gmail.com). Where to ask what, and the response times to expect, are documented in
  `SUPPORT.md`. Community discussion has also happened on the DOU forum thread
  (https://dou.ua/forums/topic/49673/) and around the IJSR publication.

  The project has no mailing list, chat channel or wiki today — this is a genuine gap that
  Sandbox hosting is meant to close. On acceptance we would like to adopt, in order of priority:
  a `jneopallium-technical-discuss` mailing list on LF's Groups.io, a channel on the LF AI & Data
  Slack, and GitHub Discussions. Meeting recordings and notes would be published in-repo.

* **External dependencies including licenses (name and version) of those dependencies.**

  All runtime and test dependencies are open source under OSI-approved licenses; the project
  policy in `CONTRIBUTING.md` explicitly forbids adding proprietary code or dependencies. Versions
  are pinned centrally in the aggregator POM.

  **Runtime (engine and cluster):**

  | Dependency | Version | License |
  | --- | --- | --- |
  | Jackson (`jackson-databind`, `jackson-annotations`, `jackson-dataformat-yaml`, `jackson-datatype-jsr310`) | 2.17.2 | Apache-2.0 |
  | Google Gson | 2.11.0 | Apache-2.0 |
  | Protocol Buffers Java (`protobuf-java`) | 3.25.5 | BSD-3-Clause |
  | gRPC Java (`grpc-netty-shaded`, `grpc-protobuf`, `grpc-stub`) | 1.75.0 | Apache-2.0 |
  | Apache Log4j 2 (`log4j-api`, `log4j-core`, `log4j-slf4j2-impl`) | 2.25.4 | Apache-2.0 |
  | SLF4J API | 2.0.16 | MIT |
  | Spring Boot (`spring-boot-starter-web`, `spring-boot-starter-tomcat`) — master node HTTP mode | 3.3.5 | Apache-2.0 |
  | Jakarta Annotations API | 2.1.1 | EPL-2.0 with GPL-2.0-with-classpath-exception secondary |
  | Redis client (`redis.clients:jedis`) — optional meta storage | 5.2.0 | MIT |

  **Runtime (optional, per-bridge — pulled in only by the bridge module that needs them):**

  | Dependency | Version | License |
  | --- | --- | --- |
  | Eclipse Milo (`milo-sdk-client`, `milo-sdk-server`) — OPC UA bridge | 1.1.1 | EPL-2.0 |
  | Eclipse Tahu (`tahu-core`) — MQTT Sparkplug B bridge | 1.0.7 | EPL-2.0 |
  | HiveMQ MQTT Client | 1.3.3 | Apache-2.0 |
  | Apache Kafka clients | 3.9.2 | Apache-2.0 |
  | OpenTelemetry Java (`opentelemetry-api`, `-sdk`, `-exporter-otlp`, `-sdk-extension-autoconfigure`) | 1.43.0 | Apache-2.0 |
  | dronefleet MAVLink (`io.dronefleet.mavlink:mavlink`) | 1.1.11 | MIT |

  **Test-scope only:**

  | Dependency | Version | License |
  | --- | --- | --- |
  | JUnit 5 (`junit-jupiter`) | 5.10.2 | EPL-2.0 |
  | Mockito (`mockito-core`, `mockito-junit-jupiter`) | 5.11.0 | MIT |
  | Spring Boot Starter Test | 3.3.5 | Apache-2.0 |
  | OpenTelemetry SDK Testing | 1.43.0 | Apache-2.0 |

  Bridges that are currently specification-only (DICOM, FHIR, LSL, LTI/xAPI, Nengo, PLC4X, ROS 2,
  IEC 61850, CANopen, Ditto) carry no third-party runtime dependency yet; each will be reviewed for
  license compatibility before its implementation is merged.

* **Initial committers (name, email, organization) and how long have they been working on project?**

  | Name | Email | Organization | Working on project since |
  | --- | --- | --- | --- |
  | Dmytro Rakovskyi | rakovpublic@gmail.com | Independent (individual contributor) | June 2018 — creator, author of the IJSR paper, and author of substantially all commits |

  This is a single-maintainer project today, and we state that plainly rather than padding the
  list. Growing to at least three actively contributing organizations is the explicit goal of
  Sandbox participation and the gate we intend to clear before requesting Incubation.

* **Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.**

  Yes. https://github.com/rakovpublic/jneopallium/blob/master/MAINTAINERS.md defines Contributor,
  Committer and Maintainer, and is the authoritative list of who currently holds each role.
  [GOVERNANCE.md](https://github.com/rakovpublic/jneopallium/blob/master/GOVERNANCE.md) §3 and §4
  give the nomination, approval, inactivity and for-cause removal criteria for each, together with
  the Emeritus policy. `.github/CODEOWNERS` maps review ownership onto the module structure, with
  the safety-critical paths (`bridge-api/`, `bridges/`, and the AGI, clinical and industrial
  domains) called out explicitly.

  `CONTRIBUTING.md` has been rewritten to match: build and test instructions, branch conventions,
  pull-request expectations, mandatory DCO sign-off, the licensing and dependency policy, code
  conventions, and the additional rules that apply to contributing a bridge.

* **Total number of contributors to the project including their affiliations at the time of submitting this proposal:**

  **1 human contributor.** Dmytro Rakovskyi (independent; commits appear under several historical
  git identities and past employer email addresses, all the same person). Automated dependency
  updates are contributed by Dependabot. Repository signals at the time of submission: ~700
  commits, 8 stars, 2 forks.

* **Does the project have a release methodology? Please document it in RELEASES.md.**

  Yes — https://github.com/rakovpublic/jneopallium/blob/master/RELEASES.md. It covers:

  - **Versioning.** Semantic Versioning 2.0.0. All 47 modules share one version inherited from the
    aggregator POM (`io.github.rakovpublic.jneopallium:wrapper`). The document enumerates exactly
    which types and on-disk formats the compatibility promise covers — the `worker-core` neuron,
    signal and processor contracts, the `bridge-api` SPI, the `agi-base` base types, the structure
    and configuration file formats, the audit record schema, and the worker entrypoint CLI — and
    states that everything else may change in a minor release.
  - **Two rules that override normal semver:** a change that weakens a safety invariant is never a
    patch release and is always called out in the release notes; and security fixes are backported
    as patch releases to every supported line.
  - **Cadence and support window** — patch as needed and immediately for security, minor roughly
    quarterly, major rarely and never without a deprecation cycle; current minor plus previous
    minor supported, previous major for six months.
  - **Deprecation policy** — `@Deprecated` with a named replacement, kept working for at least two
    minor releases and six months, removed no earlier than the next major. Configuration keys and
    format fields follow the same rule and are never silently ignored.
  - **The release procedure itself** — CI green on `master`, `mvn versions:set` across the reactor,
    release notes drafted before publishing, `mvn -Prelease clean deploy` producing source jar,
    Javadoc jar and GPG detached signatures, manual confirmation in the Central portal
    (`autoPublish=false`, so nothing goes live unreviewed), tag, then back to a snapshot version.
  - **Release-notes structure** — breaking changes first, then safety-relevant changes, then
    security fixes with CVE references, features, deprecations and the Java baseline.
  - **Artifact integrity** — every artifact GPG-signed, the key held by a maintainer and absent
    from the repository and CI secrets, published under the verified `io.github.rakovpublic`
    namespace, and never re-published under the same version.

  The mechanical Maven Central setup is documented separately in
  `docs/publishing-to-maven-central.md`. Phase delivery plans are in `TestPlanPhase1.md`,
  `TestPlanPhase2.md` and `TestPlanPhase2Optional.md`; the running design log is `WorkDiary.md`.

* **Does the project have a code of conduct? If yes, please share the URL. If no, please created CODE_OF_CONDUCT.md and point to https://lfprojects.org/policies/code-of-conduct/. You can use conduct@lfai.foundation as email for contact on this topic.**

  Yes — Contributor Covenant v2.x, at
  https://github.com/rakovpublic/jneopallium/blob/master/CODE_OF_CONDUCT.md

  On acceptance the file will be updated to reference
  https://lfprojects.org/policies/code-of-conduct/ and to list `conduct@lfai.foundation` as the
  reporting contact.

* **Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?**

  Nothing unusual. In rough priority order:

  1. **Mailing list** (Groups.io) and a **channel on the LF AI & Data Slack**.
  2. **Governance onboarding** — Technical Charter, Project Contribution Agreement, DCO app
     installation, adding the Linux Foundation as repository co-owner, and guidance on reaching the
     OpenSSF Best Practices *Passing* badge.
  3. **CI capacity for hardware-adjacent testing.** Most of the value of the bridge framework is in
     conformance against real protocol stacks (OPC UA, IEC 61850, MAVLink SITL, ROS 2, FMI). Access
     to LF CI runners able to host protocol simulators, or guidance on an acceptable
     containerised equivalent, would materially raise test quality.
  4. **Documentation hosting** for generated Javadoc and the bridge specifications, and a project
     web page under lfaidata.foundation.
  5. **Artifact publishing guidance** — whether to keep publishing under
     `io.github.rakovpublic.jneopallium` or migrate to a foundation-neutral Maven coordinate. The
     project prefers a neutral coordinate and would welcome help doing that migration cleanly.

  No dedicated build hardware, GPU capacity, or paid SaaS is being requested.

* **Project website - Do you have a web site? If no, did you reserve a domain, and would like you to have a website created?**

  No website and no reserved domain today. Project information lives in the GitHub README and the
  IJSR paper. We would like assistance creating a project page (and, if the Foundation considers it
  appropriate, registering a neutral domain such as `jneopallium.org`) as part of Sandbox
  onboarding. A minimal documentation site generated from the in-repo Markdown plus published
  Javadoc would be sufficient to start.

* **Project governance - Do you have a working governance model for the project? Please provide URL to where it is documented, typically GOVERNANCE.md.**

  Yes — https://github.com/rakovpublic/jneopallium/blob/master/GOVERNANCE.md.

  The model is deliberately written to be honest about the project's current size while describing
  the structure it grows into. It covers:

  - **Principles** — decisions made in public on issues and pull requests; influence follows
    contribution rather than affiliation; no proprietary dependencies; stricter review for
    safety-critical code.
  - **Roles and transitions** — Contributor, Committer and Maintainer, with nomination processes,
    evidence expectations, review windows, and objection handling (§2–§3). A single-maintainer
    clause makes the present state explicit and **expires automatically** once three Maintainers
    exist, so the document does not need amending to stop being a one-person project.
  - **Losing a role** (§4) — voluntary, twelve-month inactivity with a two-week objection window,
    and for-cause removal by two-thirds Maintainer vote. Emeritus status is reversible on request.
  - **A Technical Steering Committee** (§5) that forms once there are three or more Maintainers
    from at least two organizations, with an annually elected Chair, public meetings with published
    notes, and a cap of one third of seats per organization once the TSC reaches six members.
  - **Decision-making** (§6) — lazy consensus by default, an explicit single-maintainer exception
    that still requires changes to go through pull requests so the reasoning is on the record, and
    escalation to a `decision` issue resolved by TSC consensus or simple majority. A named class of
    changes requires broader agreement: the bridge write algorithm, the `SHADOW` default, any
    protocol's safety ceiling, the audit schema, the harm discriminator's hard constraints,
    dependency changes, public API breaks, and the governance documents themselves. **Weakening a
    safety ceiling, removing an audit point, or letting a write bypass the universal algorithm
    requires explicit Maintainer approval and a written rationale, without exception.**
  - **Security decisions** (§7), Code of Conduct enforcement with a recusal path so nobody
    adjudicates a report about themselves (§8), the amendment procedure (§9), and an explicit
    statement that an LF AI & Data Technical Charter would take precedence over this document
    wherever the two conflict (§10).

  Supporting documents, all present in the repository: `MAINTAINERS.md`, `RELEASES.md`,
  `SUPPORT.md`, `.github/CODEOWNERS`, and a rewritten `SECURITY.md` with a real coordinated
  disclosure process — private reporting via GitHub advisories or email, a 3-working-day
  acknowledgement target, a 90-day disclosure embargo, an explicit in-scope list covering
  write-path bypass and safety-ceiling escalation, and operator responsibilities for deployments
  driving real equipment.

  **Who handles security issues:** Dmytro Rakovskyi (rakovpublic@gmail.com) is the named security
  contact, as recorded in `SECURITY.md` and `MAINTAINERS.md`. This is a single point of failure and
  we know it; expanding it to a small security team is one of the reasons the project wants
  co-maintainers. We would welcome the LF AI & Data security mailing list described in the
  Lifecycle document's Sandbox task list.

  Still outstanding, and stated as commitments rather than claimed as done:

  - the LF AI & Data Technical Charter and Project Contribution Agreement, to be adopted on
    acceptance;
  - **moving the code into its own GitHub organization.** The repository currently lives under the
    founder's personal account (`github.com/rakovpublic/jneopallium`). The Lifecycle document
    requires a dedicated organization, and the maintainer agrees to create one and transfer the
    repository as part of onboarding — with the transfer done as a GitHub repository transfer so
    existing stars, forks, issues and clone URLs continue to resolve;
  - the Linux Foundation (`@thelinuxfoundation`) added as a co-owner of that organization;
  - the GitHub DCO app. DCO sign-off is already **mandatory and enforced in CI** by
    `.github/workflows/dco.yml`, which validates that every non-merge commit in a pull request
    carries a `Signed-off-by` trailer matching its author; that workflow is a documented stopgap
    to be deleted once the Foundation's DCO app is installed;
  - two-factor authentication enforced on all accounts with write access;
  - the OpenSSF Best Practices Badge. The self-assessment has been prepared in advance at
    `docs/openssf-best-practices.md`, which maps every Passing criterion onto concrete repository
    evidence and reduces registration to filling in a form; it also documents what Silver and Gold
    would additionally require.

* **Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts?**

  No dedicated project social accounts. Public presence to date:

  - GitHub: https://github.com/rakovpublic/jneopallium
  - GitLab mirror: https://gitlab.com/rakovpublic/jneopallium
  - IJSR paper: https://www.ijsr.net/getabstract.php?paperid=SR24703042047
    (DOI https://dx.doi.org/10.21275/SR24703042047)
  - DOU community discussion thread: https://dou.ua/forums/topic/49673/

  Project accounts would be created under Foundation naming and branding guidance if hosted.

* **Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.**

  **None.** The project has received no funding, no corporate sponsorship, no cloud credits and no
  paid staffing. All work to date has been done by the maintainer on personal time.

  Non-financial acknowledgements: the Department of Informatics at Kharkiv National University of
  Radio and Electronics, and Eugen Putiatin, Helen Matat, Tatiana Sinelnikova and Volodymyr Brytik
  for review and advice on the underlying research.

  The project does not currently have an LF AI & Data member sponsor and is seeking one; the
  maintainer would appreciate the TAC's help identifying a member organization willing to sponsor
  the Sandbox application, as required by the Project Lifecycle document.

---

## Appendix A — Repository facts at time of submission

| Item | Value |
| --- | --- |
| First commit | 14 June 2018 |
| Commits on `master` | ~700 |
| Maven modules | 47 (engine, master node, shared foundation, 14 domains, 16 bridges, 7 demos, integration tests) |
| Java source files | ~1,600 |
| Test classes | 127, plus a dedicated cross-module `integration-tests` module |
| Language / build | Java 17, Maven 3.9+ |
| License | BSD-3-Clause |
| GitHub stars / forks | 8 / 2 |
| CI | GitHub Actions (`maven-verify`, CodeQL), Dependabot |
| Publication | IJSR Vol. 13 Issue 7 (July 2024), DOI 10.21275/SR24703042047 |

## Appendix B — Sandbox readiness checklist

Against §2 of the Project Lifecycle document (approved 1 June 2023).

**Stage requirements:**

| Requirement | Status |
| --- | --- |
| 1. Fits the scope and mission of LF AI & Data | Yes — see the alignment statement above |
| 2. Sponsor who is an existing LF AI & Data member | **Not yet secured — help requested** |
| 3. Open and documented technical governance | Yes — [`GOVERNANCE.md`](https://github.com/rakovpublic/jneopallium/blob/master/GOVERNANCE.md) |
| 4. OSI-approved license | Yes — BSD-3-Clause |
| 5. Technical Charter + Project Contribution Agreement | **To be adopted on acceptance** |

**Tasks for the project team:**

| Task | Status |
| --- | --- |
| Submit proposal via pull request | This document |
| Move code into its own GitHub org, not the founder's | **To be done** — currently under `github.com/rakovpublic` |
| Two-factor authentication for all org members | **To be enforced** when the org is created |
| Install the GitHub DCO app on all repos | **To be installed** — `.github/workflows/dco.yml` enforces sign-off in CI meanwhile |
| Add `@thelinuxfoundation` as org co-owner | **To be done on acceptance** |
| OpenSSF Best Practices Badge (Passing) | **Not yet registered** — full self-assessment prepared at `docs/openssf-best-practices.md`; registration is an owner account action |
| Identify who handles security issues | Yes — Dmytro Rakovskyi, named in `SECURITY.md` and `MAINTAINERS.md` |
| Security vulnerability mailing list | To be set up by LF AI & Data; welcomed |

**Required files:**

| File | Status |
| --- | --- |
| `LICENSE` | Present (`LICENSE.MD`) — BSD-3-Clause |
| `README.md` | Present |
| `CONTRIBUTING.md` | Present — rewritten with PR expectations, DCO, dependency policy and bridge-safety rules |
| `CODEOWNERS` | Present (`.github/CODEOWNERS`), mapped onto the module structure |
| `CODE_OF_CONDUCT.md` | Present (Contributor Covenant) — to point at the LF Code of Conduct on acceptance |
| `RELEASE.md` | Present as `RELEASES.md` — versioning, cadence, criteria, support window, deprecation policy |
| `GOVERNANCE.md` | Present |
| `SUPPORT.md` | Present |
| `SECURITY.md` | Present — coordinated disclosure, scope, response targets, operator responsibilities |
| *(also)* `MAINTAINERS.md` | Present — roles and current holders |

**Optional but recommended:**

| Item | Status |
| --- | --- |
| SPDX short-form identifiers in source file headers | **Not yet** — ~1,600 source files; will be applied as a mechanical pass |

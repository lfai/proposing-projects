### Name of proposed project:

Substra Framework

### Requested project maturity level [Graduation or Incubation]:

Incubation

### Project description [what it does, why it is valuable, origin and history, ongoing development]:

Substra is a framework offering distributed orchestration of machine learning
tasks among partners while guaranteeing secure and trustless traceability of
all operations. It enables *privacy-preserving federated learning* projects,
where multiple parties collaborate on a Machine Learning objective while each
one keeps their private datasets behind their own firewall.

Origin and history:

- Following-up on a previous collaborative initiative called
    [Morpheo](http://morpheo.co/), the main concepts underlying the Substra Framework
    were designed during the elaboration of a multi-partner research project,
    named HealthChain, in H2 2017 - H1 2018. This HealthChain project was
    supported by Bpifrance as part of the Digital Investments Program for the
    major challenges of the future. This enabled the creation of a consortium consortium
    coordinated by Owkin (a private company), including
    Substra Foundation, Apricity (a private company), the Assistance Publique
    des Hôpitaux de Paris, the University Hospital Center of Nantes, the Léon
    Bérard Center, the French National Center for Scientific Research, the
    École Polytechnique, the Institut Curie and the University of Paris
    Descartes.
- It was open sourced under the Apache 2.0 license in October 2019.

It is currently under development by the Substra engineering team at Owkin. The
[compatibility table](https://github.com/SubstraFoundation/substra#compatibility-table)
provides details on the existing versions.

### Statement on alignment with LF AI’s mission:

LF AI & Data's mission includes to drive open source innovation in the AI, ML,
DL, and Data domains by enabling collaboration and the creation of new
opportunities for all the members of the community. In its effort to enable and
foster new privacy-preserving collaborations on Machine Learning challenges,
Substra Framework aligns well and complements other LF AI & Data supported
projects in the field of federated learning and privacy-preserving AI.

### Describe identified possible collaboration opportunities with current LF AI hosted projects:

- [Adversarial Robustness Toolbox](https://lfaidata.foundation/projects/adversarialrobustnesstoolbox/). 
    This toolbox could help audit algorithms prior to be shipped to a substra deployed network. 
- [AI Explainability 360](https://lfaidata.foundation/projects/aiexplainability360/)
    This toolkit could help interpret models once they are created within a substra deployed network.

### License name, version, and URL to the license text:

[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)

### URL to location of source code (GitHub, etc.):

- [Substra CLI and SDK](https://github.com/SubstraFoundation/substra)
- [Substra backend](https://github.com/SubstraFoundation/substra-backend)
- [Substra chaincode](https://github.com/SubstraFoundation/substra-chaincode)
- [hlf-k8s](https://github.com/SubstraFoundation/hlf-k8s)
- [Substra
    documentation](https://github.com/SubstraFoundation/substra-documentation)

### Please list tools in use by the project:

- [Hyperledger Fabric](https://www.hyperledger.org/use/fabric)
- [DockerHub](https://hub.docker.com/orgs/substrafoundation)
- [PyPI](https://pypi.org/project/substra/)
- [Helm Charts](https://artifacthub.io/packages/search?page=1&repo=substra)

### Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use

[GitHub](https://github.com/SubstraFoundation/substra/issues) is used as issue
tracker.

### Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use:

The main collaboration tool in use is Substra Slack Workspace (recommended
channels: #general and #help). It is publicly accessible via [this link](https://substra.us18.list-manage.com/track/click?e=2effed55c9&id=fa49875322&u=385fa3f9736ea94a1fcca969f).

We also use Github issues to collaborate around issues / enhancement proposals around the framework.

### External dependencies including licenses (name and version) of those dependencies

- [Hyperledger Fabric](https://www.hyperledger.org/use/fabric) v2.0 - licence: Apache 2.0 

### Initial committers (name, email, organization) and how long have they been working on project?

Initial committers:

- [Camille Marini](https://github.com/camillemarini) - 3 years
- [Guillaume Cisco](https://github.com/GuillaumeCisco) - 3 years
- [Kelvin Moutet](https://github.com/Kelvin-M) - 3 years
- [Jérémy Morel](https://github.com/jmorel) - 3 years
- [Thibault Robert](https://github.com/thibaultrobert) - 2,5 years
- [Clément Gautier](https://github.com/ClementGautier) - 2,5 years
- [Samuel Lesuffleur](https://github.com/samlesu) - 2 years
- [Inal Djafar](https://github.com/inalgnu) - 2 years
- [Mael Debon](https://github.com/maeldebon) - 2 years
- [Aurélien Gasser](https://github.com/AurelienGasser) - 2 years
- [Alexandre Picosson](https://github.com/AlexandrePicosson) - 1 year
- [Nathanaël Cretin](https://github.com/natct10) - 1 year
- [Thaïs de Boisfossé](https://github.com/Esadruhn) - 0,5 year

### Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.

It is mentioned in the
[`CONTRIBUTING.md`](https://github.com/SubstraFoundation/.github/blob/master/CONTRIBUTING.md) 
and formally defined as code owners for each repository. 
Code owners review is necessary for a merge in the master branch.

### Total number of contributors to the project including their affiliations at the time of submitting this proposal:

Regular contributors at the time of submitting this proposal:

- Owkin - design and development: 15 contributors  
- Substra Foundation - documentation, dissemination, animation, feature requests: 3 contributors  
- Apricity - tests, bug reports and feature requests: 2 contributors  
- 14 other organizations contribute to testing, reporting bug and suggestion new features

### Does the project have a release methodology? Please document it in RELEASES.md

Yes the project has a release methodology - however it remains to be documented
in `RELEASES.md`.

### Does the project have a code of conduct? If yes, please share the URL. If no, please created CODE_OF_CONDUCT.md and point to https://lfprojects.org/policies/code-of-conduct/. You can use conduct@lfai.foundation as email for contact on this topic

[Link to the project's code of conduct](https://github.com/SubstraFoundation/.github/blob/master/CODE_OF_CONDUCT.md).

### Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?

Nothing identified at that stage.

### Project website - Do you have a web site? If no, did you reserve a domain, and would like you to have a website created?

The project website's is located at [www.substra.ai](https://www.substra.ai),
other tld reserved include `.org`, `.io` and `.fr`.

### Project governance - Do you have a working governance model for the project? Please provide URL to where it is documented, typically GOVERNANCE.md

The governance model is mentioned in the
[`CONTRIBUTING.md`](https://github.com/SubstraFoundation/.github/blob/master/CONTRIBUTING.md),
however it is not precisely and formally defined yet.

### Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers

- Twitter account: [@substra_org](https://twitter.com/Substra_org) and [@OWKINscience](https://twitter.com/OWKINscience)
- LinkedIn account: [/substra](https://fr.linkedin.com/company/substra) and [/Owkin](https://www.linkedin.com/company/owkin/mycompany/)

### Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any

The Substra Framework project received support from:

- EU/EFPIA Innovative Medicines Initiative 2 Joint Undertaking (MELLODDY grant
    n°831472)
- Bpifrance as part of the "Healthchain" project, which resulted from the
    "Digital Investments Program for the major challenges of the future" RFP.
    As part of the “Healthchain” project, a consortium coordinated by Owkin (a
    private company) has been established, including the Substra association,
    Apricity (a private company), the Assistance Publique des Hôpitaux de
    Paris, the University Hospital Center of Nantes, the Léon Bérard Center,
    the French National Center for Scientific Research, the École
    Polytechnique, the Institut Curie and the University of Paris Descartes

== Flyte Project Proposal

*Name of project*: Flyte 

*Requested project maturity level*: Incubation 

*Project description* (what it does, why it is valuable, origin and history, ongoing development).
Flyte is a production-grade, declarative, structured and highly scalable cloud-native workflow
orchestration platform. It allows users to describe their ML/Data pipelines
using Python, Java or (in the future other languages) and Flyte manages the
data flow, parallelization, scaling and orchestration of these pipelines. Flyte
builds on top of Docker containers and kubernetes.

The feature-set and extensibility of Flyte makes it extremely useful for
Machine Learning pipelines - like Feature Engineering, Adhoc and periodic Model
Training, Model evaluation, ML monitoring, ETL and general data processing. Flyte has extensions for
Pandas, Tensorflow, Pytorch, Spark and integrates with Hosted cloud services
like AWS Sagemaker, Athena etc.

Flyte was built at Lyft and is used in production at Lyft, Level-5 (autonomous), Spotify,
Freenome and other companies.

*Statement on alignment with LF AI’s mission*. 
Flyte is built to streamline - Data Scientists, ML Engineers journey from idea
to production. Its mission is to break down silos between infrastructure,
data, ML and product teams. Flyte can be a backbone that can help integrate the
various technologies under LF umbrella.

*Have you identified possible collaboration opportunities with current LF AI hosted projects (https://lfai.foundation/projects/)? Please explain.*
Flyte is a natural platform for collaboration and it improves because of
collaboration. At Lyft, Flyte was already used in conjunction with horovod and
it can be easily integrated with ONNX, Ludwig, Mars, Amundsen, EDL, Feast-
feature serving, Marquez etc. It might be a great central system for many projects
to interact and enrich the users workflows.

*License name, version, and URL to license text*
Apache 2.0
https://github.com/flyteorg/flyte/blob/master/LICENSE

*Source control (GitHub, etc.) - Please confirm tools in use.*
Github: https://github.com/flyteorg/flyte

*Does the project sits in its own GH organization?*
Yes

*Do you have the GH DCO app active in the repos?*

*Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use.*
https://github.com/flyteorg/flyte/issues

*Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use and state request for tools you'd like to use.*
Slack: http://flyte-org.slack.com/
Mailing List: https://groups.google.com/a/flyte.org/g/users?pli=1
ReadTheDocs: http://flyte.readthedocs.org/
Github Workflows for CI.

*External dependencies including licenses (name and version) of those dependencies.*
- Kubernetes
- Postgres
- Golang
- Python
- Java

*Initial committers (name, email, organization) and how long have they been working on project?*
- Ketan Umare ketan.umare@gmail.com - Lyft (formerly) (48 months+)
- Haytham Abuelfutuh
- Anand Swaminathan
- Yee Tong
- Honxing
- Gleb Kanterov
- Jeev
- Katrina Rogan


*Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.*
Not yet - but in the process.

*Total number of contributors to the project including their affiliations.*
45+ - Will add a link here

*Does the project have a release methodology? Please document it in RELEASES.md.*
Since open sourcing we have never broken any of our users (no backwards incompatible changes), but we release a new `minor` version every month end. 

*Does the project have a code of conduct? If yes, please share the URL. If no, please created CODE_OF_CONDUCT.md and point to https://lfprojects.org/policies/code-of-conduct/. You can use conduct@lfai.foundation as email for contact on this topic.*

*Did the project achieve any of the CII best practices badges? A different badge is required depending on the requested incubation level.*

* Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?

*Project website - Do you have a web site? If no, did you reserve a domain, and would like you to have a website created?*
We have a website [https://flyte.org](https://flyte.org), we definitely want to update the content and have a proper build process around it.

*Project governance - Do you have a working governance model for the project?  Please provide URL to where it is documented, typically GOVERNANCE.md.*

*Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers.*
Only Twitter as of now - [#flyteorg](https://twitter.com/flyteorg)

*Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.*
This project was incubated and created at Lyft. Now it is used by other major organizations and with a sizeable number of contributors. 

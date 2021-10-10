* Name of proposed project: KServe

* Requested project maturity level [Graduation or Incubation]: Incubation

* Project description [what it does, why it is valuable, origin and history, ongoing development]:

  KServe provides a Kubernetes Custom Resource Definition for serving machine learning (ML) models on arbitrary frameworks. It aims to solve production model serving use cases    by providing performant, high abstraction interfaces for common ML frameworks like Tensorflow, XGBoost, ScikitLearn, PyTorch, and ONNX.

It encapsulates the complexity of autoscaling, networking, health checking, and server configuration to bring cutting edge serving features like GPU Autoscaling, Scale to Zero, and Canary Rollouts to your ML deployments. It enables a simple, pluggable, and complete story for Production ML Serving including prediction, pre-processing, post-processing and explainability.

* Statement on alignment with LF AI’s mission:

* Describe identified possible collaboration opportunities with current LF AI hosted projects:

* License name, version, and URL to the license text:

  Apache 2.0 https://github.com/kserve/kserve/blob/master/LICENSE

* URL to location of source code (GitHub, etc.):

  https://github.com/kserve/kserve

* Please list tools in use by the project:

* Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use.

  https://github.com/kserve/kserve/issues

* Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use:

  - Slack: https://kubeflow.slack.com/join/shared_invite/zt-cpr020z4-PfcAue_2nw67~iIDy7maAQ

  - Mailing List: https://groups.google.com/u/3/g/kfserving

  - Website: https://kserve.github.io/website

  - Github Workflows for PR review and approval process.

* External dependencies including licenses (name and version) of those dependencies.

* Initial committers (name, email, organization) and how long have they been working on project?

  - Dan Sun @yuzisun Bloomberg(30 months+)
  - Animesh Singh @animeshsingh IBM(30 months+)
  - Clive Cox @cliveseldon Seldon(30 months+)
  - David Goodwin @deadeyegoodwin NVIDIA(30 months+)
  - Yuzhui Liu @yuzliu Bloomberg(30 months+)
  - Theofilos Papapanagiotou @theofpa Prosus(18 months+)
  - Qianshan Chen @iamlovingit Inspur(18 months+)
  - Paul Van Eck @pvaneck IBM(12 months+)

* Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.

  We have defined the appprovers and reviewers in https://github.com/kserve/kserve/blob/master/OWNERS

* Total number of contributors to the project including their affiliations at the time of submitting this proposal:

  Total 137 contributors

* Does the project have a release methodology? Please document it in RELEASES.md.

  https://github.com/kserve/kserve/blob/master/release/RELEASE_PROCESS.md

* Does the project have a code of conduct? If yes, please share the URL. If no, please created CODE_OF_CONDUCT.md and point to https://lfprojects.org/policies/code-of-conduct/. You can use conduct@lfai.foundation as email for contact on this topic.

* Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?

* Project website - Do you have a web site? If no, did you reserve a domain, and would like you to have a website created?

  Currently we are hosting the website on github pages https://kserve.github.io/website, but we have reserved the domain `kserve.io`.

* Project governance - Do you have a working governance model for the project? Please provide URL to where it is documented, typically GOVERNANCE.md.

* Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers. 

* Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.

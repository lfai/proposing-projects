**Name of proposed project:**
 
Dataset Lifecycle Framework (project renamed Datashim)

**Requested project maturity level:**
  
Incubation

**Project description:**

DLF is enabling and accelerating data access for Kubernetes/Openshift workloads in a transparent and declarative way.
It's opensource since September of 2019 and it is growing to support use-cases related to data access in AI projects.
It brings benefits across different entities:

Data scientists/engineers: Focus on workload/experiments development and not on configuring/tuning data access
Storage Providers: Increase adoption since the framework is extensible without hindering the User Experience
Data-oriented Frameworks: Can build  capabilities (caching,  scheduling)  on top of DLF using  a declarative way to access/manage data sources

Currently it supports connection to S3,NFS,HostPath-based data sources and will expand to support more in the future.

**Statement on alignment with LF AI’s mission:**

DLF's goal is to provide a more user-friendly experience to the new and non-power Kubernetes users as configuration of data
access has been a pain-point. To that end, more AI projects and framework can be provided in Kubernetes, therefore increasing
their adoption.

**Describe identified possible collaboration opportunities with current LF AI hosted projects:**

The projects that can greatly benefit from DLF are:

- Horovod
- Ludwig
- ForestFlow

The above list is not exhaustive and can definitely be leveraged by any LF AI & Data Foundation project which involves
data access.

**License name, version, and URL to the license text:**

Apache License 2.0 (https://github.com/IBM/dataset-lifecycle-framework/blob/master/LICENSE)

**URL to location of source code (GitHub, etc.):**

https://github.com/IBM/dataset-lifecycle-framework

**Please list tools in use by the project:**

- Docker
- Operator SDK
- Minikube
- Travis CI

**Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use.**

We use Github for checking issues and feature requests (https://github.com/IBM/dataset-lifecycle-framework/issues)

**Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use:**

We maintain a wiki in our Github repo (https://github.com/IBM/dataset-lifecycle-framework/wiki)

**External dependencies including licenses (name and version) of those dependencies.**

The framework uses the Operator SDK for scaffolding which has Apache Licence 2.0 (https://github.com/operator-framework/operator-sdk/blob/master/LICENSE)

**Initial committers (name, email, organization) and how long have they been working on project?**

- Yiannis Gkoufas, yiannisg@ie.ibm.com, IBM Research Europe, 1 year
- Christian Pinto, christian.pinto@ibm.com, IBM Research Europe, 1 year
- Srikumar Venugopal, srikumarv@ie.ibm.com, IBM Research Europe, 1 year
- Panos Koutsovasilis, Koutsovasilis.Panagiotis1@ibm.com, IBM Research Europe, 6 months

**Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.**

Not yet, but will add the MAINTAINERS.md in the future.

**Total number of contributors to the project including their affiliations at the time of submitting this proposal:**

In the core framework we have 5 contributors from IBM.
Contributions in design and use cases:
- European Bioinformatics Institute (https://www.ebi.ac.uk/)
- Pachyderm (https://www.pachyderm.com/)
- OpenDataHub (https://opendatahub.io/)

**Does the project have a release methodology? Please document it in RELEASES.md.**

Not fully established yet, but do have a travis pipeline which does executes the integration tests and builds the latest Docker images and pushes them in quay.io/ibm-dlf registry

**Does the project have a code of conduct?**

Yes, in https://github.com/IBM/dataset-lifecycle-framework/blob/master/CODE_OF_CONDUCT.md

**Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?**

Travis CI currently covers our needs for integration testing and building.

**Project website - Do you have a web site?** 

We have a website hosted on Github pages: https://ibm.github.io/dataset-lifecycle-framework/

**Project governance - Do you have a working governance model for the project? Please provide URL to where it is documented, typically GOVERNANCE.md.**

Not yet. Currently, all interested contributors are encouraged to open an issue and submit pull requests.

**Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers.** 

Not yet.

**Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.**

This project has received funding from the European Union’s Horizon 2020 research and innovation programme under grant agreement No 825061 (EVOLVE).

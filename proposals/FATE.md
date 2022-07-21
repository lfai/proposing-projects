## FATE Project Proposal

### Name of proposed project:
FATE

### Requested project maturity level [Graduation or Incubation]:
Incubation

### Project description [what it does, why it is valuable, origin and history, ongoing development]:
FATE (Federated AI Technology Enabler) is the world's first industrial grade federated learning open source framework to enable enterprises and institutions to collaborate on data while protecting data security and privacy. It implements secure computation protocols based on homomorphic encryption and multi-party computation (MPC). Supporting various federated learning scenarios, FATE now provides a host of federated learning algorithms, including logistic regression, tree-based algorithms, deep learning and transfer learning.

Federated learning is one of the most promising ML technologies to help overcome data silos — strengthening data privacy and security — while still complying with laws and regulations, such as General Data Protection Regulation (GDPR). FATE enables the production-level application of federated learning in many industries including smart cities' security, finance, medicine, etc.

FATE was originally initiated by WeBank, the first digital bank in China. It was open-sourced in the February 2019 and donated to Linux Foundation in June 2019. It is now maintained by a Technical Steering Committee composed of contributors from dozens of organizations. The ongoing development of FATE is driven by the [FATE Development Committee](https://github.com/FederatedAI/FATE-Community/blob/master/meeting-minutes/FATE_Dev_Meeting/README.md). The development planning and progress are tracked in [GitHub projects](https://github.com/orgs/FederatedAI/projects?type=beta)

### Statement on alignment with LF AI’s mission:

The goals and values of FATE project are to further productize federated learning applications and build a *FederatedAI* ecosystem where community members can use this trusted, open-sourced platform to fulfill their real-world business needs while complying with all the privacy and security regulations and requirements. It is also designed to be easily extensible so that people can experiment, implement and deploy their federated learning algorithms and ideas rapidly. Besides that, due to the nature of project FATE and federated learning, data and related processing techniques are also one of the key focuses where many innovations happen.

These goals and designs of FATE align well with and can further benefit LF AI & DATA's mission on building and supporting an open AI and data community, and driving the AI & data innovations with collaborations with community members. In fact, FATE already has some integrated workflow with the KServe project and is also looking at other collaboration opportunities with more projects in the AI & DATA field.

### Describe identified possible collaboration opportunities with current LF AI hosted projects:
- KServe, the FATE project already has support to work with KServe to create online serving service from federated learning models.
- ONNX, the trained FATE models could potentially be converted to ONNX format for broder workflows.

### License name, version, and URL to the license text:
[Apache License 2.0](https://github.com/FederatedAI/FATE/blob/master/LICENSE)

### URL to location of source code (GitHub, etc.):
https://github.com/FederatedAI  
Projects under this FederatedAI organization all belong to the FATE project.

### Please list tools in use by the project:
There are many tools this project use for development, building and releasing:
* [bash](https://formulae.brew.sh/formula/bash), [coreutils](https://formulae.brew.sh/formula/coreutils), [findutils](https://formulae.brew.sh/formula/findutils), [grep](https://formulae.brew.sh/formula/grep), [gawk](https://formulae.brew.sh/formula/gawk), [gnu-tar](https://formulae.brew.sh/formula/gnu-tar), [gnu-sed](https://formulae.brew.sh/formula/gnu-sed) (macOS only)
* [GNU parallel](https://www.gnu.org/software/parallel/)
* Git & Git LFS
* Python3 & pip
* Flake8
* Node.js & npm
* JDK & Maven
* Docker & DockerHub
* Helm
* Golang
* MkDocs

### Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use.
https://github.com/FederatedAI/FATE/issues

### Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use:
Mailing List: https://groups.io/g/Fate-FedAI
And we also use GitHub projects and issues for general discussions: https://github.com/orgs/FederatedAI/projects?type=beta

### External dependencies including licenses (name and version) of those dependencies.
FATE core projects are developed using Python and use the following dependencies as libraries:  
https://github.com/FederatedAI/FATE/blob/master/python/requirements.txt  
Some of the main dependencies are:
* Flask (BSD-3-Clause)
* numpy (BSD-3-Clause)
* PyMySQL (MIT)
* pyspark (Apache-2.0)

KubeFATE project uses Golang and uses the following dependencies as libraries:  
https://github.com/FederatedAI/KubeFATE/blob/master/k8s-deploy/go.mod  
Some of the main dependencies are:
* helm.sh/helm/v3 (Apache-2.0)
* k8s.io/client-go (Apache-2.0)
* github.com/gin-gonic/gin (MIT)
* gorm.io/gorm (MIT)

FATEBoard and FATE-Serving projects uses Java and Node.js and use the following dependencies as libraries:  
https://github.com/FederatedAI/FATE-Serving/blob/master/pom.xml  
https://github.com/FederatedAI/FATE-Board/blob/master/pom.xml  
https://github.com/FederatedAI/FATE-Serving/blob/master/fate-serving-admin-ui/package.json  
https://github.com/FederatedAI/FATE-Board/blob/master/resources-front-end/package.json  
Some of the main dependencies are:
* Spring Boot (Apache-2.0)
* log4j (Apache-2.0)
* Apache ZooKeeper (Apache-2.0)
* Vue.js (MIT)

FATE deployment and running also uses these projects as external services:

| Name          | Link                                        | License                            | 
|---------------|---------------------------------------------|------------------------------------|
| Apache Spark  | https://github.com/apache/spark             | Apache-2.0 license                 |
| Apache Pulsar | https://github.com/apache/pulsar            | Apache-2.0 license                 |
| Apache HDFS   | https://github.com/apache/hadoop            | Apache-2.0 license                 |
| Apache HIVE   | https://github.com/apache/hive              | Apache-2.0 license                 |
| RabbitMQ      | https://github.com/rabbitmq/rabbitmq-server | Mozilla Public License Version 2.0 |
| Eggroll       | https://github.com/WeBankFinTech/eggroll    | Apache-2.0 license                 |
| MySQL         | https://github.com/mysql/mysql-server       | GNU General Public License         |
| Nginx         | https://github.com/nginx/nginx              | 2-Clause BSD                       |
 
### Initial committers (name, email, organization) and how long have they been working on project?
| Name         | GitHub ID                                           | Affiliation   | Time           |
|--------------|-----------------------------------------------------|---------------|----------------|
| Dylan Fan    | [dylan-fan](https://github.com/dylan-fan)           | WeBank        | 3 years        |
| Jarvis Zeng  | [jarviszeng-zjc](https://github.com/jarviszeng-zjc) | WeBank        | 3 years        |
| Guoqiang Ma  | [mgqa34](https://github.com/mgqa34)                 | WeBank        | 3 years        |
| Henry Zhang  | [hainingzhang](https://github.com/hainingzhang )    | VMware        | 3 years        |
| Layne Peng   | [LaynePeng](https://github.com/LaynePeng)           | VMWare        | Almost 3 years |
| Chenlong Ma  | [owlet42](https://github.com/owlet42)               | VMWare        | Almost 3 years |
| Wenbin Wei   | [weiwee](https://github.com/weiwee)                 | WeBank        | 3 years        |
| Kai Deng     | [forgivedengkai](https://github.com/forgivedengkai) | WeBank        | Almost 3 years |
| Junxue Zhang | [snowzjx](https://github.com/snowzjx)               | Clustar       | Almost 3 years |
| Peng Wang    | [wpdata](https://github.com/wpdata)                 | EB China Tech | Almost 3 years |

### Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.
* TSC board and maintainers are defined in: https://github.com/FederatedAI/FATE-Community/blob/master/TSC%20Board.md and https://github.com/FederatedAI/FATE-Community/blob/master/TSC%20MAINTAINERS.md
* The roles for development and releasing process are defined in: https://github.com/FederatedAI/FATE-Community/blob/master/FederatedAI_PROJECT_PROCESS_GUIDELINE.md
* The specific maintainers and reviewers list will be added in the future.

### Total number of contributors to the project including their affiliations at the time of submitting this proposal:
The number of contributors from the main sub-projects, at the time of writing this proposal:
* [FATE core](https://github.com/FederatedAI/FATE): 65
* [KubeFATE](https://github.com/FederatedAI/KubeFATE): 21
* [FATE-Serving](https://github.com/FederatedAI/FATE-Serving): 17
* [FATE-Flow](https://github.com/FederatedAI/FATE-Flow): 11
* [FATEBoard](https://github.com/FederatedAI/FATE-Board): 11

The main affiliated organizations of these contributors include:
[WeBank](https://www.webank.com/#/home), [VMware](https://www.vmware.com/), [Clustar](https://www.clustar.ai/en/about), [ICBC](https://www.icbc.com.cn/ICBC/en/default.htm), [UnionPay](https://www.unionpayintl.com/en/), [CCBFT](https://www.ccbft.com/), [Tencent](https://www.tencent.com/en-us/), [EB China Tech](https://www.ebchinatech.com/), [ABC](https://www.abchina.com/en/), [BOC](https://www.boc.cn/en/), [China Telecom](https://www.chinatelecomglobal.com/), and many others.

### Does the project have a release methodology? Please document it in RELEASES.md.
The release process is defined in: https://github.com/FederatedAI/FATE-Community/blob/master/FederatedAI_PROJECT_PROCESS_GUIDELINE.md  
The release content is described in: https://github.com/FederatedAI/FATE/blob/master/RELEASE.md

### Does the project have a code of conduct? If yes, please share the URL. If no, please created CODE_OF_CONDUCT.md and point to https://lfprojects.org/policies/code-of-conduct/. You can use conduct@lfai.foundation as email for contact on this topic.
The general code-of-conduct is defined in https://github.com/FederatedAI/FATE-Community/blob/master/CODE_OF_CONDUCT.md

### Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?
N/A. Tough it is not necessary, it may be helpful that LF AI can provide some cloud resources for FATE's testing.

### Project website - Do you have a web site? If no, did you reserve a domain, and would like you to have a website created?
https://www.fedai.org/

### Project governance - Do you have a working governance model for the project? Please provide URL to where it is documented, typically GOVERNANCE.md.
The general governance document is: https://github.com/FederatedAI/FATE-Community/blob/master/GOVERNANCE.md

### Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers.
Twitter: [@FATEFedAI](https://twitter.com/FateFedAI)

### Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.
This project was originally initiated by [WeBank](https://www.webank.com/#/home). Now it is governed by TSC board members including WeBank, [VMware](https://www.vmware.com/), [Clustar](https://www.clustar.ai/en/about), [ICBC](https://www.icbc.com.cn/ICBC/en/default.htm), [UnionPay](https://www.unionpayintl.com/en/). It is developed and maintained by TSC members and community contributors from 10+ companies and organizations.

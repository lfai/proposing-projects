### Name of proposed project: 

LakeSoul

### Requested project maturity level: 

Incubation

### Project Description:

LakeSoul is an end-to-end realtime Lakehouse framework for both BI and AI applications. LakeSoul includes a centralized metadata layer on PostgreSQL to manage large scale of tables, partitions and files on data lakes with supports of concurrent row-level upserts and ACID control. LakeSoul also provides tools to ingest data from RDBMS CDC streams and Kafka log streams in realtime, with automatic table/topic discovery and DDL synchronization. Data managed by LakeSoul is stored in Apache Parquet format and is accessed via a native Parquet IO layer optimized for cloud storages. Access layers are provided for big data engines like Spark and AI engines like PyTorch, so that both BI and AI applications can benefit from realtime Lakehouse.

More information in GitHub: https://github.com/meta-soul/LakeSoul and in documentation: https://www.dmetasoul.com/en/docs/lakesoul/intro/ .

### Statement on alignment with LF AI’s mission:

We would like to build an opensource community that encourages collaboration and contribution, develop an opensource ecology, and contribute its value to AI and Data opensource community. We believe that such a goal is in line with LF AI&Data's mission .

### Possible collaboration opportunities with current LF AI hosted projects: (https://lfai.foundation/projects/)

LakeSoul provides a Lakehouse framework to enable large scale data ingestion, management and query. It could be used to build data source for various LF AI hosted projects, including data processing projects like Sparklyr, and AI feature/sample building projects like feast and feathr.

### License name, version, and URL to license text

Apache License 2.0

https://github.com/meta-soul/LakeSoul/blob/main/LICENSE

### Source control

GitHub - https://github.com/meta-soul/LakeSoul.git

### Does the project sits in its own GH organization?

Currently no. Will transfer to its own GH organization.

### Do you have the GH DCO app active in the repos?
No

### Issue tracker (GitHub, JIRA, etc)

GitHub Issues: https://github.com/meta-soul/LakeSoul/issues

### Collaboration tools

Most collaborations are done via Github issues. We also have WeChat group and Slack channel:

Slack: https://join.slack.com/t/dmetasoul-user/shared_invite/zt-1681xagg3-4YouyW0Y4wfhPnvji~OwFg

### External dependencies including licenses (name and version) of those dependencies.

* Apache-2.0 licenses
  - commons-lang
  - guava
  - fastjson
  - scala-library
  - scala-reflect
  - scala-compiler
  - parquet-hadoop-bundle
  - scalatest
  - log4j
  - assertj-core
  - pegdown
  - spark
  - flink
  - flink-cdc-connector
  - arrow-rs
  - datafusion
* BSD 2-Clause
  - flexmark-all
  - postgresql(pgjdbc) 
* MIT License
  - tokio
  - derivative
  - atomic_refcell
  - heapless
  - Bytes
  - futures
* GPL 2.0
  - mysql-connector-java
* Eclipse Public License-v2.0
  - junit

### Initial committers (name, email, organization) and how long have they been working on project?

| Name        | Email                   | Organization | Time     |
| ----------- | ----------------------- | ------------ | -------- |
| Xu Chen     | chenxu@dmetasoul.com    | DMetaSoul    | 1.5 year |
| Maosen Sun  | sunmaosen@dmetasoul.com | DMetaSoul    | 1.5 year |
| Dongfeng Du | dongf@dmetasoul.com     | DMetaSoul    | 1 year   |
| Hua Zeng    | huazeng@dmetasoul.com   | DMetaSoul    | 1 year   |
| Kai Sun     | sunkai@dmetasoul.com    | DMetaSoul    | 1 year   |
| Zhiwei Xu   | xuzw@dmeatsoul.com      | DMetaSoul    | 1 year   |

### Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.

Community Guide: https://github.com/meta-soul/LakeSoul/blob/main/community-roles.md

Contribution Guide: https://github.com/meta-soul/LakeSoul/blob/main/community-guideline.md

### Total number of contributors to the project including their affiliations.

11 in total:

* 7 from DMetaSoul
* 2 from Peking University
* 1 from Xiamen Institute of Technology
* 1 individual contributors

https://github.com/meta-soul/LakeSoul/graphs/contributors

### Does the project have a release methodology? Please document it in RELEASES.md.

No. We are working on formalizing a release schedule.

### Does the project have a code of conduct?

https://github.com/OpenLineage/OpenLineage/blob/main/CODE_OF_CONDUCT.md

### Did the project achieve any of the CII best practices badges? A different badge is required depending on the requested incubation level.

No.

### Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?

No.

### Project website - Do you have a web site? If no, did you reserve a domain, and would like you to have a website created?

Currently the website is within company's main site: https://www.dmetasoul.com/en/docs/lakesoul/intro/ . We plan to create a dedicated site for LakeSoul and host it on Github page.

### Project governance - Do you have a working governance model for the project? Please provide URL to where it is documented, typically GOVERNANCE.md.

https://github.com/meta-soul/LakeSoul/blob/main/community-roles.md

### Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers.

Twitter: https://twitter.com/LakeSoul_01

LinkedIn: https://www.linkedin.com/in/lakesoul-%E5%BC%80%E6%BA%90%E6%B9%96%E4%BB%93%E6%A1%86%E6%9E%B6-90a7ba273/

### Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.

DMetaSoul Inc.
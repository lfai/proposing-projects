### Name of proposed project:
1chipML

### Requested project maturity:
Sandbox 

### Project description [what it does, why it is valuable, origin and history, ongoing development]:
The aim of this project is to have an open source library for basic numerical
crunching and machine learning that can run on the various families of
microcontrollers developed by AVR and ARM. These devices, especially the ARM
Cortex-M family, have recently shown relatively advanced computing capabilities,
both in terms of clock speed and memory access. This allows these extremely low
power demanding microcontrollers to perform mathematical and machine
learning algorithms that were practically impossible in the past. As, we are
gradually entering the era of the Internet of Things (IoT) and of Edge Computing, a library like this is highly desirable to enable practical applications in real life. To the best of our knowledge, we are not aware of any similar project in the Free/Open community.

The main core of the current team for this library has long and thorough
experiences with numerical crunching and machine learning on different
platforms ranging from simple microcontrollers to huge clusters (or
supercomputers) which should advantage us in continuously developing novel
features in the library. Some of us have even years of experience in creating and maintaining free/open source software packages.

### Statement on alignment with LF AI’s mission:
We are aligned with the LF AI’s mission since our aim is to provide unique AI
capabilities for very specific hardware that is becoming part of the AI revolution currently in progress. We plan to create a community around our code and to share it with anyone, and everyone is welcome to contribute to it. This project will always be open, transparent and accessible to anyone who wants to use it or improve it through any sort of contributions.

### Describe identified possible collaboration opportunities with current LF AI hosted projects:
From our past experience, we know that collaborations with other open source
projects can be very beneficial for our own project, and we obviously plan to find opportunities to interact with other LF AI projects.

In particular, we have selected 3 different projects which could have a huge
potential of collaboration. The list below reports those projects along with the
reasons why we think it could be likely and beneficial to collaborate with them:

* ONNX; this project offers an open standard to represent machine learning
models. This, in turn, provides ways to maximize performances across hardware.
We expect that an interaction with the team of this project might bring some
advantages for 1chipML. We also expect that this interaction could go the other
way around, i.e., the ONNX project could get advantages since they are not
targeting microcontrollers yet.
* Horovod; this project provides a distributed deep learning training framework
for known ML libraries/frameworks such Tensorflow, etc. We might get some
advantage in interacting with this team since we could obtain a similar framework
developed for 1chipML as well. Even in this case, we expect that there could be a
mutual benefit in doing so since Horovod does not seem to target
microcontrollers for now.
* Angel ML; this is a high-performance distributed machine learning platform. We
might have something similar for the 1chipML library and we intend to start
some conversation with the team of this project as well.

### License name, version, and URL to the license text:
Apache 2, version 2.0, https://www.apache.org/licenses/LICENSE-2.0

### URL to location of source code (GitHub, etc.):
The URL to location of the source code is (github):
https://github.com/1chipML/1chipML

### Please list tools in use by the project:
There are mainly three tools one can use for this project: 

1. gcc compiler, needed  for compilation on computer to see the behavior of the code before migrating to microcontrollers, 
2. gcc-avr compiler, needed for compilation on AVR/ARM microcontrollers, alternatively 
3. the Arduino IDE which is free to download as well. 

These are tools which are free and can be found anywhere (for example,
they can be easily installed by using the apt-get command in a linux shell). All the above tools are free/open and we have no plan to use proprietary tools.

### Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use.
It will be the GitHub issue tracker.

### Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use:

We plan to use github requests, mailing lists, a dedicated Slack channel along
with wiki pages/forums. We also plan to have biweekly meeting to synchronize
on the collaborations.

### External dependencies including licenses (name and version) of those dependencies.
There are no external dependencies. Everything is developed in ANSI C.

### Initial committers (name, email, organization) and how long have they been working on project?

* Jean Michel Sellier, jean.michel.sellier@ericsson.com, Ericsson
* Hardik Dalal, hardik.dalal@ericsson.com, Ericsson
* Yimin Nie, yimin.nie@ericsson.com, Ericsson
* Qinan Qi, qinan.qi@ericsson.com, Ericsson
* Salman Memon, salman.memon@ericsson.com, Ericsson

### Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.
Yes, the project has defined a list of maintainers, contributors, etc. which is
documented in the file MAINTAINERS.md which can be found in the repository.
Its URL is:
https://github.com/1chipML/1chipML/blob/main/MAINTAINERS.md

### Total number of contributors to the project including their affiliations at the time of submitting this proposal:
The initial number of contributors is 5, all coming from GAIA Ericsson. They
are:

* Jean Michel Sellier, jean.michel.sellier@ericsson.com, Ericsson
* Hardik Dalal, hardik.dalal@ericsson.com, Ericsson
* Yimin Nie, yimin.nie@ericsson.com, Ericsson
* Qinan Qi, qinan.qi@ericsson.com, Ericsson
* Salman Memon, salman.memon@ericsson.com, Ericsson

### Does the project have a release methodology? Please document it in RELEASES.md.
Yes, we do have a release methodology which is described in the file
RELEASES.md. Its URL is:
https://github.com/1chipML/1chipML/blob/main/RELEASES.md

### Does the project have a code of conduct? If yes, please share the URL. If please created CODE_OF_CONDUCT.md and point to https://lfprojects.org/policies/code-of-conduct/. You can use conduct@lfai.foundation as email for contact on this topic.
We do have a code of conduct which is documented in the file
“CODE_OF_CONDUCT.md”. Its URL is:
https://github.com/1chipML/1chipML/blob/main/CODE_OF_CONDUCT.md

### Do you have any specific infrastructure requests needed as part of the project in the LF AI?
Not really at the moment. We already have a GitHub repository and we plan to
use it massively. 

### Project website - Do you have a web site? If no, did you reserve a and would like you to have a website created?
We have not done anything in this direction yet (see answer above). There are
plenty of options to use on Github and we intend to use them.

### Project governance - Do you have a working governance model for project? Please provide URL to where it is documented, typically GOVERNANCE.md.
Yes, we do have a “GOVERNANCE.md” file. Its URL is:
https://github.com/1chipML/1chipML/blob/main/GOVERNANCE.md

### • Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers.
Not yet but we intend to have a presence at least on Twitter.

### Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.
The project has not received any external funding.

== Project Proposal Template


* Name of project -- or proposed name (must be unique within LF AI)  
OAAX.

* Requested project maturity level: Sandbox | Incubation | Graduated.   
Sandbox.

* Project description (what it does, why it is valuable, origin and history, ongoing development).  
OAAX (Open AI Accelerator eXchange) is a standard that aims to provide a unified  interface for using AI accelerators, enabling AI applications developers to write their applications **once** and run them on any AI accelerator that complies with the OAAX specification.  


* Statement on alignment with LF AI’s mission.   
The OAAX standard is an open source and vendor-neutral initiave that is intended to promote adoption of AI accelerators by providing a unified interface for deploying trained AI models on them **with ease**. This aligns with LF AI's mission to promote open source AI projects and to foster collaboration and innovation in the AI space.

* Have you identified possible collaboration opportunities with current LF AI hosted projects (https://lfai.foundation/projects/)? Please explain.  
    - ONNX: ONNX can be seen as a building block for OAAX, with OAAX benefiting from onnx/TurnkeyML’s tools to automate deploying and running runtimes across multiple remote devices, and at the same time, TurnkeyML’s modular structure can leverage OAAX’s hardware-specific runtimes to deploy ONNX models across multiple hardware.
    - NNStreamer: OAAX and NNStreamer can streamline the deployment and execution of AI applications on edge devices, where efficient streaming and hardware acceleration are crucial.

* License name, version, and URL to license text    
Apache 2, version 2.0, https://www.apache.org/licenses/LICENSE-2.0

* Source control (GitHub, etc.) - Please confirm tools in use.  
Github.

* Does the project sits in its own GH organization?  
Yes, all OAAX repositories are under the [OAAX organization.](https://github.com/OAAX-standard)

* Do you have the GH DCO app active in the repos?   
No.

* Issue tracker (GitHub, JIRA, etc) - Please confirm tools in use.   
Github.

* Collaboration tools (mailing lists, wiki, IRC, Slack, Glitter, etc.) - Please confirm tools in use and state request for tools you'd like to use.
    - Slack

* External dependencies including licenses (name and version) of those dependencies.  
    - ONNX Runtime (MIT license)
    - RE2 (BSD-3-Clause license)
    - CPUInfo (BSD-2-Clause license)
    - nlhomann (MIT license)
    - HailoRT (Unlicensed)

* Initial committers (name, email, organization) and how long have they been working on project?
    - Ayoub Assis (Network Optix)
    - Josef Joubert (Network Optix)
    - Maurits Kaptein (Network Optix)
    - Robin Van Emden (Network Optix)

* Have the project defined the roles of contributor, committer, maintainer, etc.? Please document it in MAINTAINERS.md.   
No.

* Total number of contributors to the project including their affiliations.  
    - 4 contributors from Network Optix.
    - A few contributors from Axelera, Hailo, and MemryX.


* Does the project have a release methodology? Please document it in RELEASES.md.   
No.


* Does the project have a code of conduct? If yes, please share the URL. If no, please created CODE_OF_CONDUCT.md and point to https://lfprojects.org/policies/code-of-conduct/. You can use conduct@lfai.foundation as email for contact on this topic.   
No. We'll be using the LF code of conduct.

* Did the project achieve any of the CII best practices badges? A different badge is required depending on the requested incubation level.   
No.

* Do you have any specific infrastructure requests needed as part of hosting the project in the LF AI?   
    - Container registry for OAAX toolchains.
    - CDN for OAAX runtimes.
    - Github runners for CI/CD pipelines.
    - AI accelerators used to automate testing of OAAX artifacts.

* Project website - Do you have a web site? If no, did you reserve a domain, and would like you to have a website created?   
https://www.oaax.org/

* Project governance - Do you have a working governance model for the project? Please provide URL to where it is documented, typically GOVERNANCE.md.   
No.

* Social media accounts - Do you have any Twitter/LinkedIn/Facebook/etc. project accounts? Please provide pointers.   
No.

* Existing sponsorship (e.g., whether any organization has provided funding or other support to date, and a description of that support), if any.   
This project is sponsored by [Network Optix](https://www.networkoptix.com/). They provided marketing and development resources to the project.
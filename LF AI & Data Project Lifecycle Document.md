
![5pz0bca3](https://github.com/user-attachments/assets/7a1f9969-c5c5-4bd1-9534-7394b35d4335)

# LF AI & Data Foundation Project Lifecycle Document #

## Table of contents ##

## 1 - Introduction <br>  
## 2 - Sandbox Stage Requirements  
 &nbsp; &nbsp; Tasks to be performed by the project’s team requesting incubation status <br>  
## 3 - Incubation Stage Requirements <br>  
## 4 - Graduation Stage Requirements <br>  
## 5 - Benefits Associated with each Lifecycle Stage <br>  
 &nbsp; &nbsp; Support Programs - Sandbox Stage Projects <br>  
 &nbsp; &nbsp; Support Programs - Incubation Stage Projects <br>  
 &nbsp; &nbsp; Support Programs - Graduation Stage Projects <br>  
## 6 - Emeritus Stage Projects <br>  
## 7 - Process of Archiving a Project <br>  
## 8 - Annual Review <br>  
## 9 - Maintaining and Approving this Document <br>  
## 10 - Feedback <br>

_Approved and in effect as of June 1st, 2023_ <br>

___
**1 - Introduction** 

The document explains the four stages of LF AI & Data project hosting
(Sandbox, Incubation, Graduation and Emeritus), the requirements for
each stage, the benefits, and how to transition from one stage to the
next.

The following figure illustrates the various incubation stages, TAC
sponsor requirements, and the required voting for a project to be
accepted into the foundation and promoted across the incubation stages.

![xum5y022](https://github.com/user-attachments/assets/d46ad123-57f2-4735-b54c-514eb88713ec)


Please note that if a project’s request to transition to a higher level
stage is not approved, the project is eligible to re-apply after six
months of the first request.
___

**2 - Sandbox Stage Requirements**

To be accepted into the Sandbox stage, a project must meet the following
requirements: 

> 1\. Fit the scope and mission of LF AI & Data <br>
> 2\. Have a sponsor who is an existing LF AI & Data member.<br>
> Alternatively, a new organization would join LF AI & Data and sponsor
> the project’s incubation application.
>
> 3\. Have an open and documented technical governance. The Linux
> Foundation team can help set this up as part of the onboarding
> process. <br>
>
> 4\. Have an OSI-approved license. <br>
>
> 5\. The project's founders adopt an open governance model documented
> in a Technical Charter for the project, and execute the Project
> Contribution Agreement transferring the project’s assets to the Linux
> Foundation.

Tasks to be performed by the project’s team requesting incubation status

> 1\. Submit a Project Contribution Proposal via a GitHub pull request to
> <u><https://github.com/lfai/proposing-projects/tree/master/proposals>.</u> <br>
> 2\. Move the project’s code into its own GitHub organization and not under its founder’s organization. <br>
> 3\. Enable two-factor authentication for all members of the project’s GitHub org. <br>
> 4\. Install the [<u>GitHub DCO app</u>](https://github.com/apps/dco) on all repos. <br>
> 5\. Add @thelinuxfoundation as a co-owner of the GitHub org. <br>
> 6\. Achieve and maintain an [<u>OpenSSF Best Practices Badge Program</u>](https://bestpractices.coreinfrastructure.org/) (Passing). <br>
> 7\. Identify who on the project will handle security issues (could be a team). <br>
> 8\. LF AI & Data will set up a mailing list to receive and discuss security vulnerability reporting. <br>
> 9\. Have the following files in GitHub:
>
* LICENSE.mdat the root of the repository specifying the terms and conditions for using, distributing, and modifying the software. In addition, you should provide information on the license of any third-party code included in the project.

* README.md welcomes new community members to the project and explains why the project is useful and how to get started.
* CONTRIBUTING.mdexplains how to contribute to the project. The file explains the types of contributions needed and how the development process works.
* CODEOWNERS to define individuals or teams responsible for code in a repository; document current project owners and emeritus committers.
* CODE_OF_CONDUCT.md sets the ground rules for participants’ behavior and helps facilitate a friendly, welcoming environment. By default, projects should leverage the [<u>Linux Foundation Code of Conduct</u> (https://lfprojects.org/policies/code-of-conduct/) unless an alternate Code of Conduct is approved prior.

* RELEASE.mdprovides documentation on the release methodology, cadence, criteria, etc.
* GOVERNANCE.mddocuments the project’s technical governance.
* SUPPORT.md lets users and developers know how to get help with the project.
* SECURITY.mdinforms users and developers on how to report security issues and vulnerabilities.
* \[Optional but highly recommended\] Include a Software Package Data Exchange (SPDX) short-form identifier in a comment at the top headers of each source code file.

After achieving a majority TAC vote, a project will be welcomed into the Sandbox stage.
___

**3 - Incubation Stage Requirements**

To be accepted into the Incubation stage, a project must meet all the
requirements of the Sandbox stage plus:

> 1\. Have at least three organizations actively contributing to the
> project.
>
> 2\. Have a defined Technical Steering Committee (TSC) with a
> chairperson identified, with open and transparent communication.
>
> 3\. Have reached a minimum of 500 stars on GitHub.
>
> 4\. Have achieved and maintained an [<u>OpenSSF Best Practices Badge
> Program</u>](https://bestpractices.coreinfrastructure.org/) (Silver).

After achieving a majority TAC vote, a project will be welcomed into the
Incubation stage.
___

**4 - Graduation Stage Requirements** 

To be accepted into the Graduation stage, a project must meet the
Incubation stage requirements plus:

> 1\. Have a healthy number of code contributions from at least five
> organizations. 2. Have reached a minimum of 1000 stars on GitHub.
>
> 3\. Have achieved and maintained an [<u>OpenSSF Best Practices Badge
> Program</u>](https://bestpractices.coreinfrastructure.org/) (Gold).
>
> 4\. Have demonstrated a substantial ongoing flow of commits and merged
> contributions for the past 12 months\*.
>
> 5\. Have completed at least one collaboration with another LF AI &
> Data hosted project

Since some of these criteria can vary depending on a project's type,
scope, and size, the TAC has final judgment over the activity level
adequate to meet these criteria.

To graduate, the project must receive the affirmative vote of the TAC
and the Governing Board.

When a project graduates, it will be eligible to have a technical lead
appointed to represent the project on the LF AI & Data Technical
Advisory Council. The project is expected to nominate a lead to the TAC
who can attend and participate in the bi-weekly TAC calls.

___

**5 - Benefits Associated with Each Lifecycle Stage** 

_Support Programs - Sandbox Stage Projects_ 

Sandbox stage projects are eligible to receive the following benefits:

* Neutral hosting of the project’s trademark and assets by LF AI & Data.
* Appointment of a TAC member as a project sponsor and provide recommendations regarding governance best practices.
* LF AI & Data blog post or similar announcing the project's hosting in the Foundation (quarterly announcements).
* Right to refer to the project as an [“<u>LF AI & Data Sandbox Project</u>](https://github.com/lfai/artwork/tree/main/lfaidata-assets/lfaidata-project-badge),” with the right, subject to applicable trademark usage guidelines, to
display the LF AI & Data logo on the project’s code repository.
* An initial and regularly scheduled license scan of the project’s codebase with results reported to the project’s mailing list.
* Ongoing source code security scans and reports.
* Infrastructure support includes mailing lists, wiki space, slack channel, etc.
* Marketing, communication, and PR support are limited to significant announcements.
* Access to the [<u>LFX</u>](https://lfx.linuxfoundation.org/) platform.
* Support of the Foundation staff who are eager to help with the project.

_Support Programs - Incubation Stage Projects_

Incubation stage projects are eligible to receive all the benefits of
the Sandbox stage projects plus:

* Right to refer to the project as an [“<u>LF AI & Data Incubation Project</u>](https://github.com/lfai/artwork/tree/main/lfaidata-assets/lfaidata-project-badge)<u>,</u>” with the right, subject to applicable trademark usage guidelines, to
display the LF AI & Data logo on the project’s code repository.
* Creative and artwork support covering website, logo, and other required creative work. ● Marketing, communication, and PR support, including project promotion via blog posts, social media, and LF AI & Data website.
* Access to the Bevy platform for community-hosted events.

_Support Programs - Graduation Stage Projects_

Graduation stage projects are eligible for all the benefits of
Incubation stage projects plus:

* LF AI & Data blog announcement or similar announcing the project graduation, including promotion activities.
* Graduation stage projects may receive support as determined by the Governing Board.
* Right to refer to the project as an [“<u>LF AI & Data Graduation Project</u>](https://github.com/lfai/artwork/tree/main/lfaidata-assets/lfaidata-project-badge),” with the right subject to applicable trademark usage guidelines, to display the LF AI & Data logo on the project’s code repository.
* Voting seat on the TAC.
* Advanced IT infrastructure support (pending board approval).
* Additional ecosystem development opportunities include training courses, certification development, and conformance programs (pending board approval).

___

**6 - Emeritus Stage Projects** 

There are times when projects become inactive for various reasons. There are cases where the TAC may no longer support a project. The project will be transitioned to the Emeritus stage and archived in such cases.

What does archiving for an LF AI & Data project mean?

* LF AI & Data will no longer provide support for the project beyond what’s deemed necessary as part of the archiving process.
* LF AI & Data will list the project online as archived.
* All assets, including trademarks of archived projects, will remain hosted by LF AI & Data and the Linux Foundation.


___

**7 - Process of Archiving a Project** 

* A proposal must be submitted to the TAC via the regularly scheduled TAC call.
* The proposal will be presented to the TAC and include an explanation supporting archiving of the project.
* The proposal must remain open for at least two weeks of discussion.
* A vote must be finalized with 2/3 approval from the TAC and 2/3 approval from the Governing Board.

___

**8 - Annual Review** 

The TAC will annually review all LF AI & Data projects. This annual
review will include assessing whether projects in Sandbox and Incubation
are making adequate progress towards the Graduation stage; and whether
projects in the Graduation stage are maintaining positive growth and
adoption. Any project may be moved to the Emeritus stage, provided the
TAC and the Governing Board approve the transition via a 2/3 affirmative
vote.

___

**9 - Maintaining and Approving this Document** 

The TAC is responsible for maintaining the Project Lifecycle Document.
To update the document, both the TAC and the Governing Board must vote
in favor of the proposed changes.

___

**10 - Feedback** 

To provide feedback on this document, please email
info@lfaidata.foundation or subscribe to the [<u>TAC mailing
list</u>](https://wiki.lfaidata.foundation/pages/viewpage.action?pageId=7733361&src=contextnavpagetreemode)
and email directly to the list.



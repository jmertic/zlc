 # ZLC Working Sessions
 
 ## Goals for this session



*   Answer these questions
    *   What is Zowe/What isn't Zowe/Zowe scope/measurable objectives for success 
    *   ZLC and it's role/purpose/measurable objectives for success 
    *   Squad organization retrospective and measurable objectives for success


## Anti-goals for this session



*   Not having answers to any of the above questions
*   Getting into implementation details
*   ???


# Question 1


## What is Zowe?

<fill in 2-3 sentence description>


### Intent (Why was it created?):

Need for a next generation, open source (framework|platform|ecosystem)? for z/OS developers and admins to work with z/OS to address:



*   Lack of integration possibilities. This missing has caused...
    *   siloing between z/OS and other platform development 
    *   IT that has slowed delivery and improve quality of z/OS applications
*   High skill barrier to engage z/OS technologies. This missing has caused…
    *   low appeal to bringing in new developers to the z/OS platform 
    *   z/OS appears to be an ‘antiquated’ platform

Individual vendors tried to solve this problem - but found it was challenging to solve alone causing fragmentation, and could only be solved with a community approach.


### Components

Zowe consists of many sub-projects that align with a defined lifecycle and delivery mechanisms.


#### Vectors of projects


##### Project maturity ( incubation, active, emeritus )

From: [https://github.com/zowe/zlc/blob/master/process/stages.md](https://github.com/zowe/zlc/blob/master/process/stages.md) 


###### Incubation Stage

To be accepted to the Incubation Stage, a sub-project must complete the [proposal process](https://github.com/zowe/zlc/blob/master/process/proposal_process.md).

Every 12 months, each Incubation Stage sub-project will come to a vote with the ZLC. A supermajority vote is required to renew a sub-project at Incubation Stage for another 12 months or move it to Active Stage. If there is not a supermajority for any of these options, the sub-project is not renewed.

In the case of an Incubation Stage sub-project that is not renewed with Zowe, the trademark will be returned to the project maintainers or an organization they designate.


###### Active Stage

To graduate from Incubation Stage, or for a new sub-project to join as an Active Stage project, a sub-project must complete the[ proposal process](https://github.com/zowe/zlc/blob/master/process/proposal_process.md) plus:



*   Have committers from at least two organizations.
*   Have achieved and maintained a Core Infrastructure Initiative [Best Practices Badge](https://bestpractices.coreinfrastructure.org/) ( note that this badge must be achieved on the sub-project itself )
*   Explicitly define a sub-project governance and committer process. This preferably is laid out in a GOVERNANCE.md file and references an OWNERS.md file showing the current and emeritus committers. A recommended governance process is defined at[ example_governance.md](https://github.com/zowe/zlc/blob/master/process/example_governance.md)
*   Have known project adopters and a public list of project adopters for at least the primary repo (e.g., ADOPTERS.md or logos on the project website).
*   Fulfill any requirements for the delivery mechanism of the sub-project.
*   Receive a supermajority vote ( ⅔ of voting members ) from the ZLC to move to Active Stage.

Sub-projects start at the Active Stage if they can demonstrate sufficient maturity. Sub-projects can remain in an Incubation Stage indefinitely, but they are normally expected to move to Active Stage within two years.


###### Emeritus Stage

Sub-projects like products have lifecycles, and often in open source the relevance for a given sub-project over time can diminish. Nonetheless, having a home for sub-projects no longer receiving active development is crucial for long-term sustainability and asset management.

Sub-projects only can enter the Emeritus Stage by either:



*   On request from the sub-project itself, requiring a supermajority votes of all active sub-project committers
*   By a supermajority vote of the ZLC if there has been insufficient activity in the sub-project over the course of 6 months.

When in the Emeritus Stage, the sub-project's code repository administration is transferred to a designated individual by the ZLC. No new features or bug fixes will be addressed, unless it is deemed a security issue. Open Mainframe Project and Zowe will hold all assets in perpetuity.

A sub-project can move back to Active Stage following the guidelines for a project being accepted at the Active Stage above.


##### Delivery mechanism 


###### Core 

Zowe Core sub-projects are defined as one of...
*   Infrastructure to make Zowe work ( App Framework, API Mediation Layer, CLI )
*   Tools to access base z/OS Operating System functionality leveraging the above infrastructure of Zowe

Zowe Core sub-projects that reach the Active Stage will be included in the subsequent Zowe release and future Zowe releases until the sub-project reaches Emeritus Stage. Active Stage projects may be included in a current active LTS release by supermajority vote of the ZLC.

Zowe Core sub-projects are listed on zowe.org for the given Zowe release it pertains to, and delivered via GitHub and technology specific channels (such as VS Code Marketplace, npm, etc).


###### Extended

Zowe Extended sub-projects are defined as open source components within the Zowe project, that isn’t in Zowe Core, and intended for direct end-user usage

Zowe Extended sub-projects should maintain a current Zowe Conformant Application status to attain Active status.

Zowe Extended sub-projects are delivered via GitHub and technology specific channels (such as VS Code Marketplace, npm, etc) and not tied to the Zowe release schedule.


###### Development Tooling

Zowe Development Tooling are open source components within the Zowe project, that isn’t in Zowe Core that are intended for developers and products to use to build upon or better leverage Zowe Core. This code would be available under both an Apache 2 and an EPLv2 license.

Zowe Extended sub-projects are delivered via GitHub and technology specific channels (such as VS Code Marketplace, npm, etc) and not tied to the Zowe release schedule.


#### Zowe Sub-projects matrix by maturity and delivery mechanism


<table>
  <tr>
   <td>
   </td>
   <th>Core</th>
   </td>
   <th>Extended</th>
   </td>
   <th>Development Tooling</th>
   </td>
  </tr>
  <tr>
   <td valign="top"><strong>Active \
(today)</strong>
   </td>
   <td valign="top"><strong>Everything in zowe z/OS convenience build + SMP/e build</strong>
<p>
(content varies over version boundaries)
<p>
List below is current snapshot of v1 LTS
<p>App Framework
<p>
- JES/MVS/USS explorer
<p>
- core apps (3270 terminal, VT editor, File editor)
<p>
API Mediation Layer [zowe/api-layer]
<p>
-Gateway
<p>
-Catalog
<p>
-Discovery Service
<p>
- ZAAS authentication, authorization microservice
<p>
API:
<p>
- MVS/USS Explorer API
<p>
- JES Explorer API
<p>
- ZSS, x-mem server
<p>
Zowe installer:
<p>
Convenience build install and configure
<p>
SMP/e build install
<p>
<strong>Everything in zowe.org CLI core downloadable</strong>
<p>
CLI + SCS plugin
<p>
Zowe Explorer downloadable on VS Code marketplace
<p>
Support for all Zowe working alongside all z/OS enterprise security managers 
<p>
New pre-reqs or updated system requirements and deployment configurations must be agreed by ZLC supermajority
   </td>
   <td valign="top">API:
<p>
CLI:
<p>
CICS (CMCI), Db2, MQ, IMS, FTP
<p>
SDK apps for desktop
   </td>
   <td valign="top"><strong>For all z/OS Developers:</strong>
<p>
<strong>For Zowe Extenders:</strong>
   </td>
  </tr>
  <tr>
   <td valign="top"><strong>Incubation \
(in the works)</strong>
   </td>
   <td valign="top"><strong>Candidates for promotion to Active</strong>
<p>
Zowe Explorer 
<ul>

<li>Offline Downloadable plugin

<li>Extensible Framework

<p>
<strong>Still Maturing</strong>
<p>
Mobile
</li>
</ul>
   </td>
   <td valign="top"><strong>Candidates for promotion to Active</strong>
<p>
<strong>Still Maturing</strong>
<p>
API:
<p>
IMS Operations
<p>
criteria zowe.org repo, zowe.org pipeline, smoke tests, support resource
<p>
CLI:
<p>
AppFW:
<p>
Jupyter App
<p>
DB Browser App
   </td>
   <td valign="top"><strong>Candidates for promotion to Active</strong>
<p>
Client SDK for NodeJS
<p>
<strong>Still Maturing</strong>
<p>
Client SDK for Python
<p>
API SDK: In development by the APIML squad
<p>
AppFW: May need to create a coherent “sdk”. Composed of: Sample apps, zlux-build?
<p>
C code: ZSS based on zowe-common-c libraries, may be their own SDK.
   </td>
  </tr>
  <tr valign="top">
   <td><strong>Emeritus</strong>
   </td>
   <td>Some apps may be stabilized within a version and sunset/removed in the next version.  Criteria is that these are not included in the vnext current 
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
</table>



### Platform Value and Expected Market Impact



*   Bruce 
    *   Value to the platform 
        *   Defacto (and vendor neutral) collection of opinionated standards to speed platform modernization such as: 
            *   Security (SSO), REST API access security, App to app notifications and launch in context (enabling cross vendor collaboration), on platform REST API management
        *   Increase integration options within the Enterprise and hybrid clouds environments via REST APIs, web technology, CLI and additional user interfaces such as Zowe Explorer and/or mobile 
        *   Bridging the gap between z/OS and open software practices to bring today’s z/OS tools and products into the this generation of development process (agile) and technologies 
    *   Expected Market Impact 
        *   Provide z/OS a cloud-like facade to enable wider adoption and increased workload (driving revenue for all commercial software providers) 
        *   Accelerate closure of the skills gap between mature and next gen IT staff by giving a common, easy to adopt infrastructure of shared services  
        *   Provide a open software “sandbox” for innovation (new for z/OS community) and set of processes for world wide roll out 


## What isn't Zowe?



*   Peter
    *   Is not synonymous with open source on z/OS
*   Mark
    *   
*   Bruce 
    *   Not a full solution (other than some basic apps) - it is not “the” answer but a key part of an answer 
    *   Not one “thing” with one use case (it is a plugable microservices architecture)  
    *   Not intended for non-z/OS platforms 
    *   Not yet meeting the expectations of hard core z/OS customers 


## How can Zowe measure it’s success?


# Question 2


## What is the ZLC’s role/purpose?

Approving releases of Zowe, which consist of projects included in Zowe Core

Maintaining the platform support matrix


## What is NOT the ZLC’s role/purpose?


## How can the ZLC measure it’s success?


# Question 3


## What has gone well with the squad organization?


## What hasn't gone well with the squad organization?


## How are measurable objectives to ensure the squads are successful?


# Past Meetings scratchpad



*   Active
    *   Core 
        *   Definition
            *   Infrastructure to make Zowe work ( App Framework, API Mediation Layer, CLI )
            *   Tools to access base z/OS Operating System functionality leveraging the above infrastructure of Zowe
            *   All of the above infrastructure and tooling must be in an LTS phase to be eligible for Zowe Core status
        *   Components
            *   App Framework
            *   API Mediation Layer
            *   CLI
            *   
        *   Delivery
            *   Zowe release
            *   Technology specific channels (vs code marketplace, npm, etc )
    *   Extended
        *   Definition
            *   Open source components within the Zowe project, that isn’t in Zowe Core.
            *   Intended for direct end-user usage
            *   Current Zowe Conformant Application
        *   Components
            *   Additional CLI plugins/packages
        *   Delivery 
            *   Technology specific channels ( vs code marketplace,npm, etc )
    *   Development Tooling
        *   Definition
            *   Open source components within the Zowe project, that isn’t in Zowe Core.
            *   Intended for developers and products to use to build upon or better leverage Zowe Core.
        *   Components
            *   None yet
        *   Delivery 
            *   Technology specific channels ( vs code marketplace,npm, etc )
*   Incubation
    *   Definition
        *   New projects coming into Zowe that are still in formation
    *   Components
        *   Mobile framework? ( incubation now )
        *   Zowe Explorer for VS Code
        *   Python SDK
        *   Node SDK
    *   Delivery 
        *   Technology specific channels ( vs code marketplace, npm, etc )
*   Emeritus
    *   Definition
        *   Components not longer actively maintained
    *   Delivery
        *   Existing channels
*   Developed independently downstream of Zowe
    *   Zowe Conformant Applications

Components in the Zowe repo today….



*   API Mediation Layer 
    *   API Catalog, Simple API Management, token based authentication SSO, Multi Factor Authentication, edge server to facade legacy z/OS apps with modern REST, websocket, load balancing (?), discovery of services, app store extensibility management of services
*   CLI and plug-ins
    *   Automation, text interface, token based authentication SSO, MFA, extensible,
*   App Framework
    *   Single Page App of Single Page Apps
        *   UI framework to manage & empower the Apps (notifications, app2app communication, uri resolver, logging...)
    *   Application Server (nodejs, but liberty/tomcat-like) to power the core UI
        *   But, Apps can use independent microservices as desired
    *   Unit of extensibility: “App”
        *   Apps are UI, (micro)service, or both. Unit of delivery that can be both client and server.
*   ZSS - Zowe Secure Services
    *   Low-level server to enable managing z/OS objects for the high-level components of Zowe
        *   Built on a library of C code that can be reused for other low-level projects
    *   Unit of extensibility: A portion of the same “App” standardization
        *   Zero or more services of an App can be a DLL plug-in to ZSS
*   App Framework apps
    *   Built on the “App” unit of extensibility
    *   Apps shipped in the core:
        *   USS/MVS/JES Explorers
        *   TN3270/SSH Terminals
        *   “Editor”
        *   App Generator
        *   Angular/React/plainjs-in-iframe “Samples”
*   Client SDK
    *   Language bundles that facade z/OS services and works alongside API services.  Currently Node, onboarding Python, future could be Java, Typescript, …
*   Bring your own IDE
    *   Zowe Explorer (Visual Studio Code plugin)
*   Selected REST APIs 
    *   Front end “orchestration” with z/OSMF  

Platform value: 

	

Expected market impact:

Theme words:  Open, Modern, Vendor Neutral, Extensible, Community, Skills challenge, Cloud like,  Familiar to non z/OS, Marketplace, Increase speed and agility of z/OS IT



*   Peter:
    *   Intent:
        *   Open, vendor-neutral, common interface for unified mainframe access by modern end-points
    *   Open, modern, platform for app-dev, devops on z/OS
        *   Architecturally, it is to the end user
            *   AML infrastructure
            *   CLI infrastructure
            *   GUI infrastructure (now workstation and eventually to include mobile)
    *   Integration container/platform providing a “virtuous cycle” for making participating apps more powerful
    *   A (as opposed to ‘the’) principal vehicle for keeping z relevant (and even expanding workload) in coming years with next generation of developers and users
*   Mark
    *   Zowe is a collection of open components which together constitute a modern z/OS interaction framework, built for extensibility and shipped with a ‘core’ suite of functionality to allow instant exploitation and leverage/display its extensibility capabilities.
    *   Zowe is open, vendor-neutral technology aiming to bridge developer and platform administrator workflow gaps with those in other ‘modern’ technologies - typically in the cloud space - mirroring software and interaction paradigms like CLIs, UIs, REST APIs, Gateway, IDE Extensions, etc.
            *   Skills gap shrinks
            *   Product velocity and quality improve
        *   Opinionated on pattern, but not content - REST, CLI, UI
            *   Can be part of a solution in many spaces
*   Bruce: 
    *   Open framework 
    *   “Cloudy like” interfaces 
    *   Extensible 
    *   Intent to reduce learning curve, attract new people, reduce complexity 
    *   Consumer choice 
    *   Breaking down historical product silos 
    *   Infrastructure to make z/OS platform more agile - easier to integrate this cloud and distributed systems 
        *   Primarily for system administrative and development tools to the mainframe. (as opposed to line of business apps) 
        *   An extensible software framework on z/OS for connecting primarily – but not limited to – system administrative and development tools to the mainframe.
    *   
*   Sujay: 
    *   Aims to open up the z/OS platform for easy consumption of its services in **patterns** similar to what cloud platforms like AWS, IBM Cloud, Azure, etc are following for all IT and development roles.
            *   Lower skill barrier
            *   Make it more appealing for new folks
            *   Improve integration possibilities with off-platform tools
            *   Remove siloing between mainframe and other platform development and IT
            *   Change perception of mainframe as antiquated
            *   Speed up delivery and improve quality of mainframe applications
    *   Establish a common standard for this **pattern** that can be vendor-agnostic
    *   The scope of this “openness” is **fluid and growing**
        *   APIs
        *   CLI
        *   Standard SDKs for popular languages
        *   Standard UI representation
        *   Standard IDE representation
        *   Standard Mobile representation
    *   Zowe is NOT a business application interface
*   Joe: 
    *   Tools platform for vendors building offerings for personas who work at mainframe IT shops serving their business units
    *   Base platform - core Zowe - has out of the box useful function but more importantly has function that attracts extenders - undifferentiated heavy lifting killer apps !
    *   Ecosystem that encourages individuals, companies already on z/OS or not considering z/OS, to get engaged. 
    *   Modernize z/OS experience to be more cloud like, mobile, bring your own IDE, bring your own language, bring your own existing familiar tool and Zowe provides bridge/SDK/APIs so z/OS is familiar to non z/OS folks
    *   Distribution, marketplace, delivery, packaging of software to make z/OS tools space as simple and familiar as other platforms
*   Sean:
    *   Next gen, open source standardized user experience for mainframers (devs, admins, not point-of-sale) to work with the mainframe.
        *   Last time everyone was using the same interface, it was via 3270. There has been a fragmentation of the user experience of the mainframe since those days where different parties modernize in different ways. Through open source we hope to make it a community effort to make the mainframe experience best for the current & next gen of users
    *   1 community, 2 scopes, 3 pillars, 4 components.
        *   Scopes
            *   Client
            *   Server
        *   Pillars
            *   UI
            *   CLI
            *   Services (network APIs, application servers, microservices)
        *   Components, all plugin-based for growth, community, vendors
            *   APIML
            *   CLI
            *   App framework
            *   ZSS (+ZIS)
    *   Technologically, roughly cloudlike. Our user experience revolves around the mainframe but a lot of the interesting code operates on a client device.

<!-- Docs to Markdown version 1.0β20 -->

# Azure Technical Academy - Architect track 01
Focus on different architect scenarios of hybrid cloud.

Azure Stencils [download](!https://www.microsoft.com/en-us/download/details.aspx?id=41937).

What to answer for each scenario
- Detailed schema - Azure components, network design, security aspects
- Role management
- Price (price calculator)

## Scenario 1: Enable Azure in organization
Existing environment:
* Active Directory for whole company that is synchronized with AAD Connect to Azure Active Directory, that is used for Office365, which has been deployed last year
* For DevTest environment there is separate AD domain for developers to be able to create service accounts, accounts for external developers and configurations without affecting security if main AD
* Your company consist of 3 different brands with significant autonomy, but there is central team overlooking networking and security. Many Azure projects are expected in each company delivered by their own teams or external partners.
* Certain security guidelines exist in your organization including corporate VM images for some highly sensitive production environments, regulatory needs to keep data in EU and data encryption at rest and in transit in production environments
* Centralized network security devices are used to enforce segmentation between brands, key projects, customers and partners
* Company has one primary data center in Prague and small secondary location in Brno
* ITSM tool Service Now is used for ticketing
* QRadar is used as SIEM solution

Design solution and describe areas of concern to enable Azure in organization:
* Propose solution for authentication and authorization (role based access control) for Azure administrators. With that consider the following:
  * For highly privileged provide maximum security
  * Follow principles of least privilege and just in time access
  * Focus achieving single identity per user (eg. consider federations) including externals
  * Describe how rights assignments are maintained to simplify operations and prevent mistakes (such as access to systems after changing role in organization or canceling contract)
* Design EA enrollment hierarchy to optimaly manage environments, self-service and costs
* Design cost management solution to be able to get clear costs of each brand, each project and each environment (dev, test, prod) to track budgets and cost effectiveness
* Design policies and describe solution to automate and enforce/audit them
* Design network architecture to meet segmentation goals and private connectivity between Azure and on-premises data centers
* Design integration with ITSM a SIEM

Useful links:
* [Azure readiness guide](https://docs.microsoft.com/en-us/azure/architecture/cloud-adoption/ready/azure-readiness-guide/)
* [Governance guide](https://docs.microsoft.com/en-us/azure/architecture/cloud-adoption/governance/journeys/)
* [Onboarding guide](https://azure.microsoft.com/mediahandler/files/resourcefiles/d8e7430c-8f62-4bbb-9ca2-f2bc877b48bd/Azure%20Onboarding%20Guide%20for%20IT%20Organizations.pdf)
* [Enterprise cloud adoption](https://docs.microsoft.com/en-us/azure/architecture/cloud-adoption/appendix/azure-scaffold)
* [Azure virtual datacenter](https://docs.microsoft.com/en-us/azure/architecture/vdc/)
* [AAD features and editions](https://azure.microsoft.com/en-us/pricing/details/active-directory/)
* [SIEM integration](https://azure.microsoft.com/en-us/blog/use-azure-monitor-to-integrate-with-siem-tools/)
* [ITSM integration](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/itsmc-overview)
* [Cost management](https://azure.microsoft.com/en-us/services/cost-management/)
* [Azure Blueprints](https://azure.microsoft.com/en-us/services/blueprints/)

## Scenario 2: DevTest hybrid environment
Existing environment:
* Dev and test environment is built manually, there are capacity and agility issues. Continuos Integration is used mainly with Team Foundation Server, but there are teams using Jenkins also.
* QA team is manually installing latest build to test new application versions
* Support and training team is manually installing deployed versions in sandbox environment to replicate reported bugs and train users

Architect solution to leverage Azure for DevTest and training environments:
* Design architecture, process and tooling to automatically create DevTest environments in Azure
* Design techniques to manage costs and protect company from using more than needed (such as running VMs that are not used over night)
* Find easy to use solution for support people and training team so they can easily create VMs without knowing too much about Azure, how it works and how applications are deployed
* For DevTest keep in mind that in mid-term there is plan to also use Azure for production on some of applications so procedures for DevTest should help you gain experience that you can leverage to deploy production in Azure

## Scenario 3: Protect and monitor your on-premises environment
Existing environment:
* 10 applications using Windows platform, .NET, SQL and joined to AD
* 10 web-based applications using Linux, Java and PostgreSQL
* 5 applications are business critical with large databases (one is 10TB)

Architect solution to protect and monitor your environment leveraging Azure
* Azure as secondary backup location
* Documents archival in Azure
* Monitor VM health, aggregate logs, monitor telemetry
* Monitor network traffic and communications between components
* Monitor security including Update management, changes in system files and installed applications
* Add cloud-based SIEM solution
* Use Azure as DR location with RPO <6h and RTO <6h

## Scenario 4: Hybrid infrastructure
Existing environment:
* 3 modern customer-facing applications deployed in Azure that need backend connectivity to on-prem systems
* 50 legacy applications on-premises, some using Windows 2008

Architect hybrid solution to meet following goals:
* Propose network connectivity and network security solution.
* Security team is using Check Point and want central management of all environments from network policy perspective.
* Windows 2008 is EOS, propose solution knowing that applications redesign to support newer OS is very expensive.
* There is strong need for private cloud due to regulations and latency concerns on one side and need for agility and creating more moderns apps on the other side. Describe solution for quick introduction of private cloud and streamline operations of deploying applications in hybrid manner to Azure and private cloud. Describe consistent deployment and operatins strategy, tooling and integrations.
* Provide solution to synchronize documents and other files between Azure and on-premises environment.
* Propose tooling and process to migrate selected VMs from on-premises to Azure.

## Scenario 5: Migrate SQL cluster into Azure
SQL with NAS

# Agenda and next steps 

## Track1
Prerequisites: Notebook with Visio (or similar tool)

Dates: Prague 20.5.19, Bratislava 30.5.

## Homework 1
TODO

## Contacts

### Tomas Kubica - Azure TSP at Microsoft
- https://www.linkedin.com/in/tkubica
- https://github.com/tkubica12
- https://twitter.com/tkubica

### Jaroslav Jindrich - Cloud Solutions Architect
- https://www.linkedin.com/in/jjindrich
- https://github.com/jjindrich
- https://twitter.com/jjindrich_cz

# Azure Technical Academy - Architect track 01
Focus on different architect scenarios of hybrid cloud.

Azure Stencils
* Go to Visio
* Open shapes
* Search for word "cloud" and click for Online results
* Download Microsoft Azure Cloud Icons
* If you have older Visio you can download older stencils directly and copy to Documents/My Shapes folder [here](https://architects.blob.core.windows.net/visio/CnE_CloudV2.7.vss?st=2019-05-20T05%3A27%3A00Z&se=2020-05-21T07%3A27%3A00Z&sp=rl&sv=2018-03-28&sr=b&sig=IELwMsknjeDR3E2fQcfyDa1lOG3hHIiHvLe4gyXMn0U%3D)
* If you are using different tool, download SVG library and import to tool of your choice [here](https://www.microsoft.com/en-us/download/details.aspx?id=41937)

Example solution
- schema https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/identity/azure-ad
- description https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/identity/azure-ad#architecture
- pricing https://azure.microsoft.com/en-us/pricing/calculator/
- example architectures [https://azure.microsoft.com/en-us/solutions/architecture/](https://azure.microsoft.com/en-us/solutions/architecture/)

Timing: 
- 10min intro 
- 50min design
- 20min presentation and recommended solution

# How to upload results of your work
* Download and install storage explorer [here](https://azure.microsoft.com/en-us/features/storage-explorer/)
* Open storage explorer and connect to storage (key will be active only for duration of our workshop)
    * Click on electricity plug icon on left side and select Use a storage account name and key
    * Use following Account Name: architects
    * Use following Account Key: <- will be provided at training date ->
    * Go to architects, Blob Containers, right-click and create container for your group
    * Upload results of your work to container with prefix scenario1 etc.

# Scenarios

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

Useful links:
* [DevTest Labs](https://azure.microsoft.com/en-us/services/devtest-lab/)
* [Azure DevOps](https://azure.microsoft.com/en-us/services/devops/)
* [Azure Automation](https://azure.microsoft.com/en-us/services/automation/)
* [VM auto start/shut](https://docs.microsoft.com/en-us/azure/automation/automation-solution-vm-management)
* [Azure Logic Apps](https://azure.microsoft.com/en-us/services/logic-apps/)
* [Shared Image Library](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/shared-image-galleries)

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
* Add application monitoring
* Add cloud-based SIEM solution
* Use Azure as DR location for business critical apps with RPO <2h and RTO <6h

Useful links:
* [Azure Backup](https://azure.microsoft.com/en-us/services/backup/)
* [Azure Site Recovery](https://docs.microsoft.com/en-us/azure/site-recovery/site-recovery-overview)
* [Azure Security Center](https://azure.microsoft.com/en-us/services/security-center/)
* [Azure Sentinel](https://azure.microsoft.com/cs-cz/services/azure-sentinel/)
* [Azure Monitor](https://azure.microsoft.com/cs-cz/services/monitor/)
* [Azure Application Insights](https://docs.microsoft.com/cs-cz/azure/azure-monitor/app/app-insights-overview)
* [Azure Monitor VM Health](https://docs.microsoft.com/en-us/azure/azure-monitor/insights/vminsights-health)
* [Azure Monitor Map](https://docs.microsoft.com/en-us/azure/azure-monitor/insights/vminsights-maps)
* [Azure Archival Storage](https://azure.microsoft.com/en-us/services/storage/archive/)
* [DR architectures](https://azure.microsoft.com/en-us/solutions/architecture/disaster-recovery-enterprise-scale-dr/)

## Scenario 4: Hybrid infrastructure
Existing environment:
* 3 modern customer-facing applications deployed in Azure that need backend connectivity to on-prem systems
* 50 legacy applications on-premises, some stil using Windows 2008 and SQL2008, VMware as hypervisor

Architect hybrid solution to meet following goals:
* Propose network connectivity and network security solution.
* Security team is using Check Point and want central management of all environments from network policy perspective.
* Security team requires publication of applications in Azure via Web Application Firewall
* Windows 2008 is EOS, propose solution knowing that applications redesign to support newer OS is very expensive.
* There is strong need for private cloud due to regulations and latency concerns on one side and need for agility and creating more moderns apps on the other side. Describe solution for quick introduction of private cloud and streamline operations of deploying applications in hybrid manner to Azure and private cloud. Describe consistent deployment and operatins strategy, tooling and integrations.
* Provide solution to synchronize documents and other files between Azure and on-premises environment.
* Propose tooling and process to migrate selected VMs from on-premises to Azure.

Useful links:
* [Azure virtual datacenter](https://docs.microsoft.com/en-us/azure/architecture/vdc/)
* [Azure Migrate](https://azure.microsoft.com/cs-cz/services/azure-migrate/)
* [Windows 2008 and SQL 2008 EOS](https://azure.microsoft.com/en-us/blog/announcing-new-options-for-sql-server-2008-and-windows-server-2008-end-of-support/)
* [Azure Stack](https://azure.microsoft.com/en-us/overview/azure-stack/)
* [Azure File Sync](https://docs.microsoft.com/en-us/azure/storage/files/storage-sync-files-planning)
* [Azure Application Gateway](https://docs.microsoft.com/cs-cz/azure/application-gateway/overview)
* [Check Point CloudGuard for Azure](https://www.checkpoint.com/downloads/products/cloudguard-microsoft-azure-solution-brief.pdf)

## Scenario 5: Migrate SQL cluster into Azure
Existing environment:
* SQL Server in HA configured for using shared storage
* Legacy app
  * Requires native SQL Server features and cannot be migrated to PaaS
  * Server is installed on 8-core system and you own licenses with Software Assurance (Enterprise)
  * Database size is 1TB
* Apps that will be refactored
  * 5 apps that can be refactored to use Azure SQL DB (PaaS)
  * All apps are using separate DB instances on SQL server installed on 8-core system
  * Apps are business critical with AlwaysOn configured
  * Read replicas are used for reporting so master does not get performance hit during reporting reads
  * Overall size of all databases together is 1TB
  * Applications require low latency
  * Current server is 8-core system
  * You own licenses with Software Assurance (Enterprise)

Migrate applications with SQL to Azure:
* Design SQL Server in Azure IaaS and provide sizing
* Design Azure SQL DB (PaaS) and provide sizing
* Ensure existing licenses can be leveraged to save costs
* You plan to use system for at least 3 years and find right cost optimization
* Advice on procedure and tooling for data migration

Useful links:
* [SQL in Azure selection guide](https://docs.microsoft.com/cs-cz/azure/sql-database/sql-database-paas-vs-sql-server-iaas)
* [SQL Server in Azure IaaS](https://azure.microsoft.com/cs-cz/services/virtual-machines/sql-server/)
* [Azure SQL DB](https://azure.microsoft.com/cs-cz/services/sql-database/)
* [Azure SQL DB purchasing models](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-purchase-models)
* [Azure Data Migration Service](https://azure.microsoft.com/en-us/services/database-migration/)

# Agenda and next steps 

## Track1
Prerequisites: Notebook with Visio (or similar tool)

Dates: Prague 20.5.19, Bratislava 30.5.

## Homework 1
Take some time to relax and revisit all scenarios and documentation to sharpen your skills. In few weeks after sessions we will assign homework and you will have 6-8 weeks to complete it. Send results to us via private message in our Teams (logins to Teams will be provided soon).

## Homework 2
About 2 weeks before next session we will post here what topics will be discussed and provide you with links in case you would like to study before session starts.

## Contacts

### Tomas Kubica - Azure TSP at Microsoft
- https://www.linkedin.com/in/tkubica
- https://github.com/tkubica12
- https://twitter.com/tkubica

### Jaroslav Jindrich - Cloud Solutions Architect
- https://www.linkedin.com/in/jjindrich
- https://github.com/jjindrich
- https://twitter.com/jjindrich_cz

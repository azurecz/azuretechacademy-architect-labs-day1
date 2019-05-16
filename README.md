# Azure Technical Academy - Architect track 01
Focus on different architect scenarios of hybrid cloud.

Azure Stencils [download](!https://www.microsoft.com/en-us/download/details.aspx?id=41937).

What to answer for each scenario
- Detailed schema - Azure components, network design, security aspects
- Role management
- Price (price calculator)

## Scenario 1: DevTest hybrid environment
VM, OS, budget

## Scenario 2: Migrate SQL cluster into Azure
SQL with NAS

## Scenario 3: Hybrid infrastructure
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

## Scenario 4: Protect and monitor your on-premises environment
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

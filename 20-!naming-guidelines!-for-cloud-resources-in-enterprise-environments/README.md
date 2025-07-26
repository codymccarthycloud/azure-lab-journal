# Cloud Resource Naming Guidelines  
**Readable, Scalable, and Maintainable Naming Conventions for Azure Labs and Enterprise Projects**

## Purpose  
This document provides standard naming guidelines to help cloud engineers, architects, and learners maintain clarity and consistency across Azure resources. 
Professional naming increases resource discoverability, simplifies automation, and ensures smooth team handoffs.

---

## General Naming Pattern  

[Env]-[Location]-[ResourceType]-[Role]-[Instance]

Components

Component _______Example_____________________________________Description___________________________
- Env          | (e.g., lab, test, prod)	lab             |	Environment                      
- Location     | abbreviation	scus (South Central US)     |	Azure region                         
- ResourceType | (vm, vnet, nsg, etc.)	vm                |	Type of resource                      
- Role	       | (web, db, jump)	jump                    | Function of the resource                
- Instance     | 01, 02                                   |	Numeric or short identifier for scaling
___________________________________________________________________________________________________

Common Azure Resource Naming Matrix

Resource Type	Abbreviation	Sample Name	Notes
- Virtual Machine	vm	test-scus-vm-web-01	Environment + role based
- Virtual Network	vnet	prod-eastus-vnet-main	Use for main VNets
- Storage Account	stg	lab-wcus-stgfiles	Avoid special characters
- Network Security Group	nsg	dev-ncus-nsg-db	Link to role/service
- Resource Group	rg	prod-scus-rg-app	Environment aligned

Naming Principles

- Readable for humans and systems
- Consistent across environments and teams
- Scalable for future growth
- Secure—avoid exposing sensitive info
- Automatable with scripts and templates

Future Additions

-ARM naming enforcement template
-Bicep example with dynamic name generation
-GitHub Actions for naming validation

---

## Server Naming Convention Pattern

[Env]-[Location]-[ServerType]-[Role]-[Instance]


Component_____Example Values______Description_____________
-Env        | prod, test, dev  |	Environment indicator
-Location	  | tor, scus, nyc   |	Physical/Cloud location
-ServerType	| srv, app, db, fs |	Abbreviated type
-Role	      | web, api, auth   | Functional responsibility
-Instance	  | 01, 02	         | For scaling and HA setups
__________________________________________________________

Sample server names:

prod-tor-srv-db-01 → Production DB server in Toronto
test-scus-app-web-01 → Web application server in a test lab hosted in South Central US
dev-nyc-srv-auth-02 → Dev authentication server hosted in New York

Tips for Server Naming

Keep consistency with VM naming if servers and VMs coexist.
If servers are grouped in clusters, include node identifiers (e.g., dbnode1).
Consider including owner or project codes for large enterprises (e.g., fin, hr, ops).
Avoid embedding dates—they get stale fast.

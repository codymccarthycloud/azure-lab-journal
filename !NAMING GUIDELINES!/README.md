# Cloud Resource Naming Guidelines  
**Readable, Scalable, and Maintainable Naming Conventions for Azure Labs and Enterprise Projects**

## Purpose  
This document provides standard naming guidelines to help cloud engineers, architects, and learners maintain clarity and consistency across Azure resources. 
Professional naming increases resource discoverability, simplifies automation, and ensures smooth team handoffs.

---

## General Naming Pattern  

[Env]-[Location]-[ResourceType]-[Role]-[Instance]

Components

| Component      | Example                                    | Description
|----------------|--------------------------------------------|------------------------------------------
| `Env`          | `(e.g., lab, test, prod)`                  |	`Environment`                      
| `Location`     | `abbreviation	scus (South Central US)`    |	`Azure region`                         
| `ResourceType` | `(vm, vnet, nsg, etc.)`                    |	`Type of resource`                      
| `Role`	       | `(web, db, jump)`                          | `Function of the resource`                
| `Instance`     | `01, 02`                                   |	`Numeric or short identifier for scaling`


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

## Azure Environment Tagging Cheat Sheet

| Tag        | Description                                     | Usage Scenario                              | Example Prefix            |
|------------|-------------------------------------------------|---------------------------------------------|---------------------|
| `dev`      | Development environment                         | Code iteration, debugging, experimentation  | `dev-scus-webapp-01` 
| `test`     | Testing / QA environment                        | Run test cases, simulate production         | `test-eus-apiapp-02` 
| `prod`     | Production environment                          | Live services used by end-users             | `prod-wcus-clientapp-01`|
| `ent`      | Enterprise-grade resource                       | Used across org-wide systems and shared infra| `ent-prod-dbcluster-01`|
| `lab`      | Training or educational setup                   | Learning, internal sandbox projects         | `lab-scus-mlcluster-01`|
| `stag`     | Staging / Pre-prod environment                  | Final testing before go-live                | `stag-eus-portalapp-01`|
| `sandbox`  | Temporary freeform dev or trial zone            | MVPs, demos, developer exploration          | `sandbox-nyc-funcapp-01`|
| `dr`       | Disaster Recovery environment                   | Redundant backup environment                | `dr-scus-vm-jump-01`|
| `poc`      | Proof of Concept                                | Feasibility tests, early stage experiments  | `poc-tor-aiapp-01`|

---

## Server Naming Convention Pattern

[Env]-[Location]-[ServerType]-[Role]-[Instance]


| Component     | Example Values     | Description
|---------------|--------------------|----------------------------
| `Env`         | `prod, test, dev`  | `Environment indicator`
| `Location`	  | `tor, scus, nyc`   | `Physical/Cloud location`
| `ServerType`	| `srv, app, db, fs` | `Abbreviated type`
| `Role`	      | `web, api, auth`   | `Functional responsibility`
| `Instance`	  | `01, 02`	         | `For scaling and HA setups`


Sample server names:

prod-tor-srv-db-01 → Production DB server in Toronto
test-scus-app-web-01 → Web application server in a test lab hosted in South Central US
dev-nyc-srv-auth-02 → Dev authentication server hosted in New York

Tips for Server Naming

Keep consistency with VM naming if servers and VMs coexist.
If servers are grouped in clusters, include node identifiers (e.g., dbnode1).
Consider including owner or project codes for large enterprises (e.g., fin, hr, ops).
Avoid embedding dates—they get stale fast.

## Comparison 

Comparison

| `Parameter`	  | `Used In`                 	| `Purpose`	                                      | `Example Values` |             
|---------------|-----------------------------|-------------------------------------------------|-------------------------------|
| `storage-sku` |	`az vm create`	            | `Sets OS disk type for a Virtual Machine`       |	`StandardSSD_LRS, Premium_LRS` |
| `sku`         |	`az storage account create`	| `Sets performance + redundancy Storage Account` |	`Standard_LRS, Premium_LRS`|

---

# Azure Resource Type Naming Chart

This table maps common Azure resource types to their professional naming abbreviations for use in naming conventions like `[Env]-[Location]-[ResourceType]-[Role]-[Instance]`.

| Resource Type             | Abbreviation | Sample Name                  | Notes                                           |
|---------------------------|--------------|------------------------------|-------------------------------------------------|
| Virtual Machine           | `vm`         | `prod-eus-vm-web-01`         | Use hyphens for readability                     |
| Virtual Network           | `vnet`       | `lab-scus-vnet-main`         | Logical network container                       |
| Storage Account           | `stg`        | `testwcusstgfiles01`         | No hyphens; DNS compliant                       |
| Blob Container            | `cnr` or `blob` | `cnr-images-prod`         | Use lowercase and hyphens                       |
| Network Security Group    | `nsg`        | `dev-ncus-nsg-db`            | Often tied to VM role                           |
| Resource Group            | `rg`         | `prod-eus-rg-app`            | Group of resources for lifecycle control        |
| Dashboard                 | `dash`       | `test-scus-dash-monitoring01`| Useful for tracking resource performance        |
| Key Vault                 | `kv`         | `test-scus-kv-appsecrets01`  | Holds secrets, certs, keys                      |
| Managed Identity          | `id`         | `test-scus-id-vm01`          | Linked to VM or service                         |
| Azure Function App        | `func`       | `prod-eus-func-email01`      | Event-based compute                             |
| Container Instance        | `aci`        | `dev-eus-aci-web01`          | Lightweight containers                          |
| Application Gateway       | `agw`        | `prod-scus-agw-frontend01`   | For secure web traffic routing                  |
| Load Balancer             | `lb`         | `test-eus-lb-api01`          | Evenly distributes traffic                      |
| Log Analytics Workspace   | `log`        | `prod-scus-log-core01`       | Collects and queries telemetry data             |

> Use compressed formats like `testwcusstgfiles01` for resources that don’t allow hyphens (e.g., Storage Accounts), and stick to lowercase where required.

---

## Common Azure Web App Naming Patterns

| Suffix          | Description                                      | Example Name                     |
|------------------|--------------------------------------------------|----------------------------------|
| `webapp`         | Generic web application                          | `prod-eus-webapp-01`             |
| `web-cliapp`     | Created using CLI or automation script           | `test-scus-web-cliapp-02`        |
| `web-apiapp`     | Hosts RESTful or GraphQL APIs                    | `dev-wcus-web-apiapp-01`         |
| `web-clientapp`  | Front-end user interface                         | `prod-eus-web-clientapp-03`      |
| `web-adminapp`   | Admin dashboard or internal tool                 | `test-nyc-web-adminapp-01`       |
| `web-portalapp`  | Customer or employee portal                      | `prod-tor-web-portalapp-02`      |
| `web-mobileapp`  | Backend for mobile apps                          | `dev-scus-web-mobileapp-01`      |
| `web-logicapp`   | Logic App workflows hosted as web endpoints      | `lab-wus-web-logicapp-01`        |
| `web-testapp`    | Temporary or test environment                    | `test-eus-web-testapp-05`        |

---

## Azure Machine Learning Compute Naming Patterns

| Suffix           | Description                                      | Example Name                      |
|------------------|--------------------------------------------------|-----------------------------------|
| `cpucluster`     | CPU-based compute cluster for general ML tasks   | `dev-scus-cpucluster-01`          |
| `gpucluster`     | GPU-powered cluster for deep learning training   | `prod-eastus-gpucluster-02`       |
| `mlworkspace`    | Azure ML Workspace name                          | `test-wcus-mlworkspace-01`        |
| `mlcompute`      | Single-node ML compute target                    | `dev-nyc-mlcompute-03`            |
| `automlcluster`  | Dedicated compute for AutoML experiments         | `test-scus-automlcluster-01`      |
| `pipelinestep`   | Compute used in a pipeline step                  | `prod-eus-pipelinestep-02`        |
| `modeldeploy`    | Compute for hosting deployed models              | `prod-tor-modeldeploy-01`         |
| `inferencing`    | Inferencing target, often CPU-based              | `prod-eus-inferencing-01`         |
| `labcluster`     | Educational or training compute environment      | `lab-scus-labcluster-01`          |




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

| Tag        | Description                                     | Usage Scenario                              | Example Prefix      |
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

## Azure Region Location Abbreviation Reference

This chart maps commonly used Azure region abbreviations to their full location names. Use these abbreviations consistently in naming resources like `prod-eus-webapp-01` to ensure clarity and governance across global deployments.

| Abbreviation | Azure Region                | Common Use Cases             |
|--------------|-----------------------------|------------------------------|
| `eus`        | East US                     | Enterprise apps, ML, testing |
| `scus`       | South Central US            | Dev workloads, web hosting   |
| `wcus`       | West Central US             | API apps, analytics          |
| `wus`        | West US                     | VMs, ML compute clusters     |
| `can`        | Canada Central              | Production apps in Canada    |
| `cane`       | Canada East                 | Backup or DR for Canada      |
| `ncus`       | North Central US            | Databases, internal services |
| `weu`        | West Europe                 | EU production workloads       |
| `nweu`       | North Europe                | EU testing, QA               |
| `uks`        | UK South                    | Secure, regulated workloads  |
| `ukw`        | UK West                     | DR and dev environments      |
| `asia`       | Southeast Asia              | Mobile backend, region-specific services |
| `jp`         | Japan East / West           | ML, web apps, compliance     |
| `aus`        | Australia East / Southeast  | Fintech, mobile APIs         |


---

## Azure Resource Type Naming Chart

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

---

## Azure Resource Role Abbreviation Chart

This table provides standard abbreviations for resource roles or workloads across cloud architectures. Use these in naming patterns like `[Env]-[Location]-[ResourceType]-[Role]-[Instance]` to add clarity around the function of the resource.

| Role Name           | Abbreviation | Description                                     | Sample Name                     |
|---------------------|--------------|-------------------------------------------------|----------------------------------|
| Web Frontend        | `web`        | Public-facing websites, portals                 | `prod-eus-webapp-web-01`         |
| Database            | `db`         | SQL, NoSQL, Cosmos DB, etc.                     | `dev-scus-vm-db-02`              |
| Jumpbox / Bastion   | `jump`       | Secure admin entry point                        | `stag-wcus-vm-jump-01`           |
| API Server          | `api`        | REST/GraphQL endpoints                          | `test-eus-web-apiapp-api-01`     |
| Authentication      | `auth`       | OAuth, token, identity services                 | `prod-can-kv-auth-01`            |
| Client UI           | `client`     | Web or mobile user interfaces                   | `prod-eus-web-clientapp-client-01`|
| Admin Dashboard     | `admin`      | Internal tools and views                        | `dev-ncus-web-adminapp-admin-01` |
| Portal              | `portal`     | Employee/customer portals                       | `prod-tor-web-portalapp-portal-01`|
| Mobile Backend      | `mobile`     | Services powering mobile apps                   | `stag-scus-web-mobileapp-mobile-02`|
| AI / ML Workload    | `ai` / `ml`  | Training, inferencing, AutoML, etc.             | `test-wcus-mlworkspace-ml-01`    |
| Monitoring / Logs   | `mon` / `log`| Metrics, telemetry, diagnostics                 | `prod-weu-log-mon-01`            |
| Internal Service    | `svc`        | Backend logic, messaging, support routines      | `dev-wcus-func-svc-03`           |
| File Server         | `fs`         | SMB, NFS, or shared blob containers             | `lab-eus-stg-fs-01`              |
| Compute Cluster     | `cluster`    | CPU/GPU clusters for ML or analytics            | `prod-eastus-cpucluster-cluster-01`|

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




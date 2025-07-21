Title: Azure Lab - Windows Server Datacenter 2016 VM Deployment Attempt

Overview:
This lab involved attempting to deploy a Windows Server 2016 Datacenter (Gen 1) VM in Azure to explore the manual VM creation workflow
and the ARM template generation feature for automation.

Objectives:
- Select an appropriate image (Windows Server 2016 Datacenter - Gen1)
- Configure basic VM settings (name, region, size, authentication)
- Enable RDP (Port 3389) for remote access
- Download the ARM template for automation

Challenges Encountered:
- Azure blocked deployment of the chosen image due to Marketplace restrictions tied to the lab subscription.
- Encountered the following error: “Cannot complete purchase as your enrollment for this subscription doesn't allow purchase of marketplace products.”
- The “Download a template for automation” option was not available due to deployment validation failure.

Key Learnings:
- Marketplace restrictions can prevent access to third-party VM images, especially in sandboxed lab environments.
- Region selection and image publisher compatibility are crucial to successful validation.
- ARM templates are generated during the "Review + Create" flow, but only after validation succeeds.
- CLI-based deployment is a viable workaround when the portal fails due to Marketplace terms.

Outcome:
Although a VM could not be created and the ARM template wasn’t downloaded, the lab still provided insight into Azure’s deployment process, 
resource dependencies, and real-world validation blockers.

Status: Incomplete (due to image restrictions), but core concepts reviewed.

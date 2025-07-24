# Organizing Azure Resources – Pluralsight Lab Summary


## Lab Objectives

- Learn how to structure and organize Azure resources using **resource groups**
- Move a resource between groups (when supported)

---

### 2. Explore Existing Resource Groups

- Review the provided resource groups in the subscription
- Navigate to **Resource Groups → 826-d0a70c8f-organizing-azure-resources**
- Identify resources like storage accounts or VMs

---

# Azure Management Groups – Nested Subscription Summary

## Key Effects of Nested Placement

1. **Inherited Governance**  
   - Subscriptions inherit **policies, RBAC**, and role assignments from the nested group and all parent groups.

2. **Targeted Control**  
   - Apply **Azure Policy**, **compliance rules**, and **blueprints** to specific teams or departments.

3. **Organizational Clarity**  
   - Improves logical grouping without affecting billing.
   - Aids visibility by aligning subscriptions with business units.

4. **Scoped Automation**  
   - Enables streamlined CI/CD, deployments, and resource templates at specific levels.

---

Example:  
A subscription under `Software Engineering` inherits:
- Tagging rules from `Engineering`  
- Security policies from `Software Engineering`

---

## Lab Completion Criteria

- Resource group structures reviewed
- Attempted resource moves 

---

## Lab Output Screenshots

![management groups create new group engineering under the tenant root group](https://github.com/user-attachments/assets/7287c3c5-0f16-468a-9e62-03ea0d16c8c5)
![create nested groups within group management](https://github.com/user-attachments/assets/3a908642-187d-49aa-889d-380ba3d32cc7)
![nested groups in management groups](https://github.com/user-attachments/assets/17c1f3c9-1931-4824-944d-aed508c9c2c4)
![add subscriptions to nested management groups](https://github.com/user-attachments/assets/7ffd3247-082d-427b-aed2-974b6af27d74)
![subscriptions](https://github.com/user-attachments/assets/e54d8188-b625-437d-a6ad-96bef7575865)
![subscriptions settings resource groups](https://github.com/user-attachments/assets/66562559-712c-47de-abd1-ab8e020aa1c6)
![subscriptions settings resource groups viewer](https://github.com/user-attachments/assets/2485d8ec-c250-4d74-8af0-5e7e73bde2fe)
![move a resource group within subscriptions settings resource groups](https://github.com/user-attachments/assets/f8dc08ac-0ef9-41ed-8489-97de3d7cf5df)
![move resources example](https://github.com/user-attachments/assets/160b3e7c-b130-433e-a2ba-aef47af3c4e2)



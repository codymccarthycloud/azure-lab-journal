# Azure Cost Planning and Management Guide

## Overview
This document outlines the steps for analyzing, planning, optimizing, and monitoring costs within the Azure portal. The process includes evaluating subscriptions with high costs, budgeting, and proactively managing resource spending.

---

## Navigation Steps

### 1. Select Subscription
- Go to **Cost Management + Billing**.
- Choose **Subscriptions**.
- Select your **Active Subscription**.

### 2. View High-Cost Subscriptions
- Inside your subscription, click on **Cost Analysis**.
- Use filters (monthly, daily, service type) to identify subscriptions with highest spending.

### 3. Check Budgets
- From the subscription page, navigate to **Cost Management** > **Budgets**.
- Review existing budget thresholds or **create a new budget** to track expenses against forecasted costs.

### 4. Resource Group Analysis
- Within your subscription, go to **Resource Groups**.
- Select a specific resource group tied to cost concerns.
- Navigate to **Cost Management** > **Cost Analysis** within the resource group.
- Evaluate which resources are trending toward budget overruns.

### 5. Optimize and Monitor
- From subscription or resource group scope, open **Advisor Recommendations** under Cost Management.
- Implement recommendations like:
  - Rightsize VMs
  - Remove unused resources
  - Switch to Reserved Instances or Savings Plans
- Set up **Cost Alerts** to receive notifications when forecasted costs approach or exceed budget.

---

## Select Scope & Target Resources
- In **Cost Management and Billing**, click **Select Scope** to change context between subscriptions or resource groups.
- Set scope to focus cost analysis on particular resources or service categories.

---

## Best Practices
- Use tags for organizing cost centers (e.g., `Environment:Production`, `Team:Finance`)
- Review cost breakdown monthly and quarterly
- Consolidate resources across subscriptions where possible
- Use automated scripts to extract and log cost data

---

## Goal
Empower proactive cost governance by enabling deep insights and optimization opportunities across all Azure subscriptions and resources.

---

## Lab Output Screenshots

![1 navigate to subscription and select the active subscription](https://github.com/user-attachments/assets/5640ae33-5ccf-440f-9647-67666fb424e4)
![2 cost management and billing view what subscriptions and groupings have high costs](https://github.com/user-attachments/assets/5e27385b-5054-496a-8eb4-e00afb4ca39b)
![3 cost management budgets](https://github.com/user-attachments/assets/40c34a28-c371-4205-b7fa-fabe8a365de4)
![4 naviagte to the resource group cost management cost analysis optimize for resource groups and subscriptions going overbuget](https://github.com/user-attachments/assets/e74dc0a3-ffe4-465b-8a97-5c819db22fac)
![5 select scope target subscriptions and resource groups](https://github.com/user-attachments/assets/442b9394-e39b-4ae4-b189-6b8edbc6c61c)


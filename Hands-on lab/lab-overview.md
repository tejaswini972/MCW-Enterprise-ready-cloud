# Enterprise-ready cloud hands-on lab step-by-step

## Abstract and learning objectives

In this hands-on lab, you are working with Trey Research to setup some best practices regarding policies, permissions, and managing their Azure subscriptions using advanced tooling such as Azure Blueprints. Tasks include creating scripts that Enterprise IT will use to automatically set policy and delegate permissions when a new subscription is created. You will also learn how to manage these policies and permissions for multiple subscriptions using Azure Management Groups and Azure Blueprints.

At the end of this hands-on lab, you will know how to provide cost tracking by business unit, environment and project, provide for a distributed administration model, put a service catalog in place to prevent deployment of unsupported Azure services, and put controls in place to allow deployment of services only in specific regions.

## Overview

Trey Research is a manufacturing company that builds consumer products with 29.6 billion USD in annual revenue. Trey's headquarters are in New Jersey, but they have data centers and branch offices scattered across the United States; with several major offices in the United Kingdom, France, and Japan.

Even as large as it is, Trey seeks to maximize the cost-effectiveness and flexibility of its IT, especially in new projects and business units. With a dizzying number of existing business units; each with their own unique requirements from IT and ballooning costs from internal hardware and data center investment, Trey is looking to the cloud.

Trey is interested in a large-scale solution that will help mitigate creeping costs and start the transition to a modern cloud-based enterprise architecture using a solid set of controls for governance.

## Requirements

1. Full global admin access to the Azure AD tenant associated with your Azure subscription.

## Solution architecture

![Hierarchy showing Azure AD at the root, then a Management Group, then an Azure Subscription, then resource groups, then resources. It is tagged \'Policies and RBAC\'.](images/Hands-onlabstep-by-step-Enterprise-readycloudimages/media/image2.png "Azure AD - Management Group - Subscription - Resource Group hierarchy")


**Contents**

<!-- TOC -->

- Enterprise-ready cloud hands-on lab step-by-step
  - Abstract and learning objectives
  - Overview
  - Requirements
  - Solution architecture
  - Exercise 1: Create the policy for Enterprise IT
    - Help references
    - Task 1: Create a Management Group
    - Task 2: Apply the service catalog policy
    - Task 3: Restrict the creation of ExpressRoute circuits
    - Task 4: Restrict the creation of resources in regions
    - Task 5: Create and apply a naming convention
    - Task 6: Test the policies
  - Exercise 2: Configure delegated permissions
    - Help references
    - Task 1: Create groups in Azure AD for delegation
    - Task 2: Create user accounts in Azure AD for delegation
    - Task 3: Enable a business unit administrator for the subscription
    - Task 4: Enable project-based delegation and chargeback with tags
  - Exercise 3: Use Azure Blueprints to govern your Azure environment
    - Help references
    - Task 1: Create a new Azure Blueprint
    - Task 2: Publish a draft blueprint and assign it
    - Task 3: Update the Service catalog policy to allow blueprint assignments
    - Task 4: Assign a blueprint
    - Task 5: Verify blueprint assignment and resource creation
    - Task 6: Editing blueprints
    - Task 7: Verify compliance with Azure Policy
  - Exercise 4: Monitoring Compliance and Cost
    - Help references
    - Task 1: Identifying Changes in Resources
    - Task 2: Using Policies to Control SKUs
    - Task 3: Create and Manage Azure Budgets

<!-- /TOC -->

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

- [Enterprise-ready cloud hands-on lab step-by-step](#enterprise-ready-cloud-hands-on-lab-step-by-step)
  - [Abstract and learning objectives](#abstract-and-learning-objectives)
  - [Overview](#overview)
  - [Requirements](#requirements)
  - [Solution architecture](#solution-architecture)
  - [Exercise 1: Create the policy for Enterprise IT](#exercise-1-create-the-policy-for-enterprise-it)
    - [Help references](#help-references)
    - [Task 1: Create a Management Group](#task-1-create-a-management-group)
    - [Task 2: Apply the service catalog policy](#task-2-apply-the-service-catalog-policy)
    - [Task 3: Restrict the creation of ExpressRoute circuits](#task-3-restrict-the-creation-of-expressroute-circuits)
    - [Task 4: Restrict the creation of resources in regions](#task-4-restrict-the-creation-of-resources-in-regions)
    - [Task 5: Create and apply a naming convention](#task-5-create-and-apply-a-naming-convention)
    - [Task 6: Test the policies](#task-6-test-the-policies)
  - [Exercise 2: Configure delegated permissions](#exercise-2-configure-delegated-permissions)
    - [Help references](#help-references-1)
    - [Task 1: Create groups in Azure AD for delegation](#task-1-create-groups-in-azure-ad-for-delegation)
    - [Task 2: Create user accounts in Azure AD for delegation](#task-2-create-user-accounts-in-azure-ad-for-delegation)
    - [Task 3: Enable a business unit administrator for the subscription](#task-3-enable-a-business-unit-administrator-for-the-subscription)
    - [Task 4: Enable project-based delegation and chargeback with tags](#task-4-enable-project-based-delegation-and-chargeback-with-tags)
  - [Exercise 3: Use Azure Blueprints to govern your Azure environment](#exercise-3-use-azure-blueprints-to-govern-your-azure-environment)
    - [Help references](#help-references-2)
    - [Task 1: Create a new Azure Blueprint](#task-1-create-a-new-azure-blueprint)
    - [Task 2: Publish a draft blueprint and assign it](#task-2-publish-a-draft-blueprint-and-assign-it)
    - [Task 3: Update the Service catalog policy to allow blueprint assignments](#task-3-update-the-service-catalog-policy-to-allow-blueprint-assignments)
    - [Task 4: Assign a blueprint](#task-4-assign-a-blueprint)
    - [Task 5: Verify blueprint assignment and resource creation](#task-5-verify-blueprint-assignment-and-resource-creation)
    - [Task 6: Editing blueprints](#task-6-editing-blueprints)
    - [Task 7: Verify compliance with Azure Policy](#task-7-verify-compliance-with-azure-policy)
  - [Exercise 4: Monitoring Compliance and Cost](#exercise-4-monitoring-compliance-and-cost)
    - [Help references](#help-references-3)
    - [Task 1: Identifying Changes in Resources](#task-1-identifying-changes-in-resources)
    - [Task 2: Using Policies to Control SKUs](#task-2-using-policies-to-control-skus)
  - [Task 3: Create and Manage Azure Budgets](#task-3-create-and-manage-azure-budgets)
  - [Task 4: Environment Cleanup](#task-4-environment-cleanup)
  - [After the hands-on lab](#after-the-hands-on-lab)
    - [Task 1: Remove resources and configuration created during this lab](#task-1-remove-resources-and-configuration-created-during-this-lab)

<!-- /TOC -->

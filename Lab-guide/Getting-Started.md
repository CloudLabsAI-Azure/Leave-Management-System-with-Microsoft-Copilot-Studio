# Leave Management System with Microsoft Copilot Studio

### Overall Estimated Duration: 3 Hours

## Overview

In this hands-on lab, you will configure and explore a Leave Management Agent that automates employee leave applications, approvals, and balance tracking. The agent enforces strict security and business rules to ensure that requests are handled fairly, securely, and consistently. Employees can apply for leave, check their balance, and track past requests all through a controlled Dataverse integration that respects row-level security and manager approval flows.

## Objectives

By the end of this lab, you will be able to:

-  Understand the policies and business rules that govern leave applications.
-  Configure the agent to read and write leave data from Dataverse tables.
-  Apply validation logic to prevent overlapping or invalid leave requests.
-  Implement balance checks and auto-approval rules based on request duration.
-  Route longer leave requests to managers for approval and update balances accordingly.
-  Track and query your own leave history securely, without exposing other employees’ data.

## Prerequisites

Participants should have:

- An active Microsoft Power Platform environment with Dataverse enabled.
- Access to Dataverse tables **LeaveRequest** and **LeaveBalance** with appropriate permissions.
- Basic familiarity with Microsoft Power Automate and Power Apps (for flows and agent integration).
- A test user account with leave balances seeded in Dataverse for validation.
- Manager accounts are configured in the system for approval routing.

## Architecture

The lab utilizes several Azure services to build, deploy, and manage applications effectively. Azure Container Registry (ACR) is used for storing and managing Docker container images, while Azure Cosmos DB provides a scalable, multi-model database solution for data migration. Azure Kubernetes Service (AKS) enables the deployment and management of containerized applications within a managed Kubernetes environment

## Architecture Diagram

## Explanation of Components

The architecture for this lab involves several key components:

- **Azure Container Registry (ACR):** A managed Docker container registry for storing and managing Docker container images.

## Getting Started with the Lab

Welcome to your Leave Management System with Microsoft Copilot Studio Workshop! We've prepared a seamless environment for you to explore and learn how to build, configure, and test an intelligent leave management agent. This lab will guide you through applying business rules, handling approvals, and integrating with Dataverse to deliver a secure and efficient experience. Let's begin by making the most of this workshop!

### Accessing Your Lab Environment

Once you're ready to dive in, your virtual machine and Lab guide will be right at your fingertips within your web browser.

![](../media/gs1.png)

### Exploring Your Lab Resources

To get a better understanding of your Lab resources and credentials, navigate to the Environment tab.

![](../media/gs2.png)

### Utilizing the Split Window Feature

For convenience, you can open the Lab guide in a separate window by selecting the Split Window button from the Top right corner

![](../media/gs3.png)

### Managing Your Virtual Machine

Feel free to start, stop, or restart your virtual machine as needed from the Resources tab. Your experience is in your hands!

![](../media/gs4.png)

## Let's Get Started with Power Apps Portal

1. In the JumpVM, click on **Microsoft Edge** shortcut of Microsoft Edge browser which is created on desktop.

   ![](../media/gs-1.png)

1. Open a new browser tab and navigate to [Power Apps](https://make.powerapps.com/) portal.

1. On the **Sign into Microsoft** tab, you will see the login screen. Enter the provided email or username, and click **Next** to proceed.

   - Email/Username: <inject key="AzureAdUserEmail"></inject>

     ![](../media/gs-2.png)

1. Now, enter the following password and click on **Sign in**.

   - Password: <inject key="AzureAdUserPassword"></inject>

     ![](../media/gs-3.png)

     >**Note:** If you see the Action Required dialog box, then select Ask Later option.
     
1. If you see the pop-up **Stay Signed in?**, click No.

   ![](../media/gs-4.png)

1. You have now successfully logged in to the Power Apps portal. Keep the portal open, as you will be using it later in the lab.

   ![](../media/gs-5.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on the **Next** from lower right corner to move on next page.

## Happy Learning!!

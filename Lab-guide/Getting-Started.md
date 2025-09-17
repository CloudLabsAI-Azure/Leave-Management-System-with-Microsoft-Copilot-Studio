# Leave Management System with Microsoft Copilot Studio

### Overall Estimated Duration: 3 Hours

## Overview

In this hands-on lab, you will configure and explore a Leave Management Agent that automates employee leave applications, approvals, and balance tracking. The agent enforces strict security and business rules to ensure that requests are handled fairly, securely, and consistently. Employees can apply for leave, check their balance, and track past requests — all through a controlled Dataverse integration that respects row-level security and manager approval flows.

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

## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and **Guide** will be right at your fingertips within your web browser.

   ![](media/14052025.png "Lab Environment")

   >**Note:** Once the environment gets set up, you will see the PowerShell automation script executing on the desktop. Wait for it to complete and ensure not to close or cancel it.

## Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.
 
## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.
 
![Explore Lab Resources](media/14052025(1).png)
 
   > You will see the **DeploymentID** value on the **Environment** tab, use it wherever you see SUFFIX or DeploymentID in lab steps.

## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
 ![Use the Split Window Feature](media/14052025(2).png)

## Managing Your Virtual Machine
 
Feel free to **Start, Stop, or Restart** your virtual machine as needed from the **Resources** tab. Your experience is in your hands!
 
![Manage Your Virtual Machine](media/resourcetab-v1.png)    

## Lab Guide Zoom In/Zoom Out

To adjust the zoom level for the environment page, click the **A↕ : 100%** icon located next to the timer in the lab environment.

![Manage Your Virtual Machine](media/14052025(3).png)

## Lab Validation

After completing the task, hit the **Validate** button under the Validation tab integrated within your lab guide. If you receive a success message, you can proceed to the next task; if not, carefully read the error message and retry the step, following the instructions in the lab guide.

   ![Inline Validation](media/cng13.png)

If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com.

## Login to Azure Portal

1. Once you are on the LabVM, if a Windows screen titled **Choose privacy settings for your device** appears, proceed by clicking **Next** through each of the configuration steps, typically four times, then click **Accept** to complete the setup.

   ![](media/setup.jpg)

1. In the LabVM, click on the **Azure Portal** shortcut of the Microsoft Edge browser, which is created on the desktop.

   ![](media/cng12.png "Lab Environment")
   
1. On the **Sign into Microsoft Azure** tab, you will see the login screen. In that enter the following email/username and then click on **Next**. 
   * Email/Username: <inject key="AzureAdUserEmail"></inject>
   
     ![](media/cng6.png "Enter Email")
     
1. Now enter the following password and click on **Sign in**.
   * Password: <inject key="AzureAdUserPassword"></inject>
   
     ![](media/cng7.png "Enter Password")
  
1. If you see the pop-up **Stay Signed in?**, click **No**.

1. If you see the pop-up **You have free Azure Advisor recommendations!**, close the window to continue the lab.

1. If a **Welcome to Microsoft Azure** popup window appears, click **Cancel** to skip the tour.
  
This hands-on lab will help you gain insights into how Azure OpenAI’s content filtering mechanisms contribute to responsible AI deployment and how you can leverage these filters to ensure that your AI models adhere to appropriate content standards.

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on **Next** from the lower right corner to move on to the next page.

![Launch Azure Portal](media/cng4.png)

## Happy Learning!!

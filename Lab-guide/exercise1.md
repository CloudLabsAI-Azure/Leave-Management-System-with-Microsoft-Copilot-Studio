# Exercise 1: Setting up Pre-Requisites for Leave Management Agent

### Estimated Duration: 60 Minutes

## Overview

In this exercise, you will provision a Microsoft Power Platform environment and sign in to Microsoft Copilot Studio. You will then create a new agent and configure its basic settings. These steps form the foundation for building an Agentic AI-driven leave management solution that streamlines processes and enhances experience.

## Objectives

You will be able to complete the following tasks:

- Task 1: Provisioning Power Platform environment

- Task 2: Sign in to Microsoft Copilot Studio

- Task 3: Create a New Agent

- Task 4: Configure Agent Basics

## Task 1: Provisioning Power Platform environment

In this task, you will ingest the datasets into Dataverse, which will be created in a new Power Platform environment.

1. Navigate back to the Power Apps portal, and please switch to the environment that you created earlier.

    ![](../media/st-store-ex1-g1.png)

    > **Note:** If the environment is not visible, refresh the page and try again.

1. Verify that the current environment displays **ODL_User <inject key="DeploymentID" enableCopy="false"></inject>'s Environment**.

    ![](../media/gs-fix-leave-may-g4.png)

1. Now select **Tables (1)** from the left menu and click on **Create with Excel or .CSV file (2)**.

     ![](../media/leav-man-e1-g-2.png)

1. In the next pane, click on **Select from device** and in the pop-up window, select files.

     ![](../media/ex2img11.png)

1. On the **Open** dialog box, navigate to the folder path `C:\datasets\Leave-Management-System-with-Microsoft-Copilot-Studio-datasets-main` **(1)**, select the file **LeaveRequests_Schema.csv (2)**, and then click **Open (3)**.

     ![](../media/cor-mn-e5-g-11.png)

1. On the **Import an Excel or .CSV file** pane, verify that the file **LeaveRequests_Schema.csv** is listed. Ensure that the table **LeaveRequests** is included by keeping the toggle enabled. Click **Import** to proceed.

     ![](../media/cor-mn-e5-g-12.png)

1. Once selected, click on **Save and exit** and in the pop up window.

     ![](../media/cor-mn-e5-g-13.png)

     > **Note:** Parsing the file and creating columns may take a few minutes; wait until the process completes and the columns are displayed before proceeding. Do not close or navigate away from the page during this time.

1.  Click on **Save and exit**.

     ![](../media/gs-fix-leave-may-g3.png)

     >**Note:** If you are not able to find **Save and exit** button, minimize the screen using **CTRL + -**.

1. Once created, locate the Leave Request table from the list and note down the logical ID of the table as shown in a notepad safely, as you will be using this value further in the lab.

     ![](../media/upimg1.jpg)

     >**Note:** You may see a different ID than the one shown in the screenshot; this is expected.

## Task 2: Sign into Microsoft Copilot Studio

In this task, you will sign in to Microsoft Copilot Studio and switch the environment to the new developer environment that you created earlier.

1. Navigate to **Microsoft Copilot Studio** by opening a new browser tab and entering the following URL:

     ```
     https://copilotstudio.microsoft.com
     ```

1. On the **Welcome to Microsoft Copilot Studio** screen, keep the default **country/region** selection and select **Get Started** to continue.

     ![](../media/pro-activ-gg-g11.png)

1. If the **Welcome to Copilot Studio!** pop-up appears, select **Skip** to continue to the main dashboard.

     ![](../media/gs-travel-g3.png)

1. If the **We've updated you to the latest version of Microsoft Copilot Studio** pop-up appears, select **Got it!**.

     ![](../media/pro-activ-gg-g12.png)

1. If the **What's new in Copilot Studio** pop-up appears, select the **Close (X)** icon to dismiss it.

     ![](../media/pro-activ-gg-g13.png)

1. In Copilot Studio, open the environment picker **(1)**, expand **Supported environments (2)**, and select **ODL_User <inject key="Deployment ID" enableCopy="false"></inject>'s Environment (3)** to switch.

     ![](../media/ex1-travel-g6.png)

1. Once you are in **Copilot Studio**, you will be on the home page.

     ![.](../media/st-store-ex1-g10.png)

## Task 3: Create a New Agent

In this task, you will create a new agent in Microsoft Copilot Studio by defining its name, description, and basic configuration settings. This agent will serve as the base for enabling intelligent leave management operations.

1. Navigate back to the Copilot Studio page from the browser.

1. Before creating the agent, verify that the selected environment is **ODL_User <inject key="DeploymentID" enableCopy="false"></inject>'s Environment**.

     ![](../media/gs-fix-leave-may-g5.png)

   > **Note:** If a different environment is selected, switch to **ODL_User <inject key="DeploymentID" enableCopy="false"></inject>'s Environment** before proceeding.

1. From the home page, select **Agents (1)** from the left menu and click on **+ Create blank agent (2)** to create an agent.

     ![](../media/gs-fix-leave-may-g6.png)

1. In the **Name your agent** pane, enter the below value in the **Name your agent (1)** field, and then select **Create (2)**.

     ```
     Leave Management Agent
     ```

     ![](../media/gs-fix-leave-may-g7.png)

1. Wait until the **Getting things ready ...** screen completes and the Copilot Studio home page loads.

     ![](../media/st-store-ex2-g2.png)

1. Verify that the agent provisioning is complete by confirming the **Your agent has been provisioned** message is displayed.

     ![](../media/st-store-ex2-g3.png)

     > **Note:** Agent provisioning may take a few minutes to complete.

     > **Note:** If you see the warning message **A newer version of this agent is available**, select **Refresh**.

     ![](../media/gs-fix-leave-may-g8.png)

1. In the **Details** section, select **Edit**.

     ![](../media/gs-fix-leave-may-g9.png)

1. In the next pane, enter the following **Description** field, and then select **Save (2)**.

    | Key                     | Value                               |
    |-------------------------------|--------------------------------------------|
    | Description | Handles leave requests, approvals, and balance updates using Dataverse and Power Automate. Helps employees apply for leave, check status, and get real-time updates via Teams. |

    ![](../media/gs-fix-leave-may-g10.png)

1. In the **Select your agent's model** section, keep the default model selected and do not make any changes.

     > **Note:** The available models may vary, as Copilot Studio updates models frequently.

1. In the **Instructions** section, select **Edit**.

    ![](../media/lev-mgmt-sb-ex1-g3.png)

1. In the **Instructions** pane, enter the provided details in the **Instruction (1)** field, and then select **Save (2)**.

   | Key                     | Value                               |
   |-------------------------------|--------------------------------------------|
   | Instruction | Assist with leave applications, validate balances, and route approvals. Respond clearly and guide users through each step. Always ensure requests meet policy and ask for missing details. |

    ![](../media/lev-mgmt-sb-ex1-g4.png)

1. You have successfully created the Leave Management Agent. In the next steps of this lab, you will enhance it further by adding knowledge sources and advanced features.

## Task 4: Configure Agent Basics

In this task, you will connect the Leave Request table from Dataverse as a knowledge source for your agent, allowing it to provide AI-powered answers using Retrieval-Augmented Generation (RAG).

1. In the **Knowledge** section, select **Add knowledge**.

     ![](../media/lev-mgmt-sb-ex1-g5.png)

1. In the next pane, select **Dataverse** as a knowledge source.

     ![](../media/lev-mgmt-sb-ex1-g6.png)

1. From the list, search **Leave Request (1)** and select **Leave Request (2)** table. Click on **Add to agent (3)**.

     ![](../media/cor-mn-e5-g-15.png)

1. With the basic setup and configurations complete, the next exercises will focus on building the core logic for leave management.

<validation step="153f21c8-cb47-43c9-8ecf-ae3a6c889323" />

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

## Summary

In this exercise, you provisioned a Power Platform environment, signed into Microsoft Copilot Studio, created a new agent, and configured its basic settings. These steps laid the groundwork for building an Agentic AI-driven leave management solution.

### You have successfully completed this exercise. Please continue to the next one >>

   ![](../media/a-gs-g2.png)

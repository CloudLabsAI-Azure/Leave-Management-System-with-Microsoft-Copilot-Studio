# Exercise 2: Create Store‑Operations Agent in Copilot Studio

### Estimated Duration: 45 Minutes

## Overview

In this exercise, you will create a Copilot Studio agent that will serve as the foundation for your store operations assistant. You will define the agent’s purpose by assigning it a name and description, and connect it to key knowledge sources such as the product catalog, store policy documents, and website content. These steps will enable your agent to deliver relevant, AI-powered responses based on indexed information.

## Objectives

You will be able to complete the following tasks:

- Task 1: Creating a store-operations agent in Copilot Studio

- Task 2: Adding knowledge sources to the agent

## Task 1: Creating a store-operations agent in Copilot Studio

In this task, you will create a new agent in Microsoft Copilot Studio by defining its name, description, and basic configuration settings. This agent will serve as the base for enabling intelligent store operations.

1. Navigate back to Copilot Studio page from the browser.

1. From the home page, select **Create (1)** from left menu and click on **+ New agent (2)** to create an agent.

   ![](../media/leav-man-e2-g-1.png)

1. In the next pane, select **configure (1)** and provide the following details.

    | Key                     | Value                               |
    |-------------------------------|--------------------------------------------|
    | Name | `Leave Management Agent` |
    | Description | Handles leave requests, approvals, and balance updates using Dataverse and Power Automate. Helps employees apply for leave, check status, and get real-time updates via Teams. |
    | Instruction | Assist with leave applications, validate balances, and route approvals. Respond clearly and guide users through each step. Always ensure requests meet policy and ask for missing details. |

    ![](../media/ex2img12.png)

    >**Note:** Sometimes you may see a diffrent UI, if you are seeing a UI diffrent than this, then follow this below steps:

    - Click on **Skip to configure**, to get the configuration pane.

      ![](../media/ex5img34.png)
   
1. In the next pane, provide the same details given above and click on **Create**.

   ![](../media/leav-man-e2-g-3.png)

1. Once after adding the details, click on **Continue** to create the agent.

1. You have successfully created the Leave Management Agent. In the next steps of this lab, you will enhance it further by adding knowledge sources and advanced features.

   ![](../media/leav-man-e2-g-4.png)

## Task 2: Adding knowledge sources to the agent

In this task, you will connect knowledge sources such as the product catalog, policy documents, and store website content to your agent, allowing it to provide AI-powered answers using Retrieval-Augmented Generation (RAG).

1. If you are not already on the **Agents** page, select **Agents (1)** from the left navigation menu. Then, click **Leave Management Agent (2)**.

   ![](../media/leav-man-e2-g-5.png)

1. On the **Leave Management Agent** page, select the **Knowledge (1)** tab from the top menu and click **+ Add knowledge (2)**.  

   ![](../media/leav-man-e2-g-6.png)

1. In the next pane, click on **select to browse** option as shown and in the pop up window to select files, navigate to `C:\datasets\Store-Operations-with-Copilot-Studio-lab-datasets\Leave-management` file.

   ![](../media/leav-man-e2-g-7.png)

1. On the **Upload files** pane, verify that the file **Leave-management.docx (1)** is listed and then click **Add to agent (2)**.

   ![](../media/leav-man-e2-g-8.png)

1. Once done, again click on **+ Add knowledge**.

   ![](../media/leav-man-e2-g-9.png)

1. In the next pane, select **Dataverse** as knowledge source.

   ![](../media/leav-man-e2-g-10.png)

1. From the list, search and select **Leave Request** table. Click on **Add to agent**.

   ![](../media/leav-man-e2-g-11.png)

1. On the **Copilot Studio** page, select **Flows (1)** from the left navigation menu and click **New agent flow (2)** to create a new flow.

   ![](../media/leav-man-e2-g-22.png)

1. On the **Agent flows – Designer** page, click **Add a trigger** to begin configuring the flow.  

   ![](../media/leav-man-e2-g-23.png)

1. In the next pane, select **Dataverse** as knowledge source.

   ![](../media/leav-man-e2-g-10.png)

## Summary

In this exercise, you created a Copilot Studio agent that served as the foundation for your store operations assistant. You defined the agent’s purpose by assigning it a name and description, and connected it to key knowledge sources such as the product catalog, store policy documents, and website content. These steps enabled the agent to deliver relevant, AI-powered responses based on indexed information.

### You have successfully completed this exercise, please continue to next one >>

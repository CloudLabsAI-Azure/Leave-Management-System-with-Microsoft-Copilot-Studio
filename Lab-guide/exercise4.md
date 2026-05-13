# Exercise 4: End-to-End Testing

### Estimated Duration: 40 Minutes

## Overview

In this exercise, you will test the agent end-to-end by executing various prompts and scenarios. After completing the tests, you will verify that the leave request data has been correctly updated in the Dataverse table.

## Objectives

You will be able to complete the following tasks:

- Task 1: Test Approval Scenarios

- Task 2: Validate Data in Dataverse

## Task 1: Test Approval Scenarios

In this task, you will run the agent end-to-end using the provided prompts and verify its responses for accuracy.

1. Now that you've configured the agent, it's time to test.

1. In **Copilot Studio**, select **Agents (1)**, and then choose **Leave Management Agent (2)**. 

   ![](../media/lev-mgmt-sb-ex2-g52.png)

1. On the top menu bar, click **Publish** to save and apply your changes to the agent.

   ![](../media/lev-mgmt-sb-ex4-g1.png)

1. On the **Publish this agent** dialog box, review the details and click **Publish** to confirm and complete the publishing process.

   ![](../media/lev-mgmt-sb-ex4-g2.png)

1. On the **Leave Management Agent** page, click **Test** in the top-right corner to open the testing panel for the agent.

   ![](../media/lev-mgmt-sb-ex4-g11.png)

1. In the **Test your agent** panel, you will be testing the **Leave Management Agent**.

   ![](../media/lvimg57.png)

1. In the **Test your agent** panel, type a greeting such as **Hello (1)** (or any similar message) in the chat box and click the **Send (2)** button to interact with the agent.

1. On the **Activity map** page, verify that the **Greeting** topic is triggered, showing phrases such as *Good afternoon*, *Good morning*, *Hello*, *Hey*, and *Hi*.  

   ![](../media/leav-man-e4-g-33.png)

1. In the **Test your agent** panel, enter the below request in the message box **(1)**, and then select the **Send (2)** button to test the agent.

   ```
   I want to apply for Leave
   ```

   ![](../media/gs-fix2-leave2-may-g28.png)

1. In the **Test your agent** panel, when prompted to choose a leave type, select from the available options such as **Casual**, **Emergency**, or **Unpaid**.

   ![](../media/lev-mgmt-sb-ex4-g6.png)

1. In the **Test your agent** panel, enter the leave start date in the required **yyyy-mm-dd** format using the below example value **(1)**, and then select the **Send (2)** button.

   ```
   2026-05-13
   ```

   ![](../media/gs-fix2-leave2-may-g20.png)

1. In the **Test your agent** panel, enter the leave end date in the required **yyyy-mm-dd** format using the below example value **(1)**, and then select the **Send (2)** button.

   ```
   2026-05-14
   ```

   > **Note:** In this test scenario, we are validating a leave request for 2 days or less.

   ![](../media/gs-fix2-leave2-may-g21.png)

1. In the **Test your agent** panel, enter the reason for your leave using the below example value **(1)**, and then select the **Send (2)** button.

   ```
   I will be attending a family function
   ```

   ![](../media/gs-fix2-leave2-may-g22.png)

1. In the **Test your agent** panel, verify that the agent responds with a confirmation message showing the approved leave dates. 

   ![](../media/leav-man-e4-g-31.png)

   > **Note:** If you see the prompt asking you to connect, perform the steps below:  

   > Click **Open connection manager (1)** to verify your credentials.

      ![](../media/gs-fix2-leave2-may-g23.png)
      
   > On the **Manage your connections** page, the **Leave Management Workflow** may show as **Not Connected (1)**. Click **Connect (2)** to establish the connection.  

      ![](../media/cor-mn-e5-g-43.png)

   > On the **Create or pick connections** page, select the available connection **Standard approvals (1)** and click **Submit (2)** to complete the connection setup. 

      ![](../media/cor-mn-e5-g-44.png)

   > On the **Manage your connections** page, verify that the **Leave Management Workflow** status shows as **Connected (1)**. Once connected, return to the previous tab where you were testing the agent and continue.  

      ![](../media/cor-mn-e5-g-45.png)

1. Return to the **Agent testing** tab, and then select **Retry**.

   ![](../media/gs-fix2-leave2-may-g24.png)

1. Verify that leave requests for 2 days or less are automatically approved in the agent response.

   ![](../media/gs-fix2-leave2-may-g25.png)

1. Open a browser and navigate to Outlook using the following URL:

   ```
   https://outlook.com
   ```

1. Sign in using the lab credentials.

   - Username: <inject key="AzureAdUserEmail"></inject>
   - Temporary Access Key: <inject key="AzureAdUserPassword"></inject>

      ![](../media/gs-fix2-leave2-may-g33.png)

1. In the **Test** pane, select **New test session** to test leave requests for more than 2 days.

   ![](../media/gs-fix2-leave2-may-g26.png)

1. In the message box, enter **Hello (1)**, and then select the **Send (2)** icon.

   ![](../media/gs-fix2-leave2-may-g27.png)

1. In the **Test your agent** panel, enter the below request in the message box **(1)**, and then select the **Send (2)** button to test the agent.

   ```
   I want to apply for Leave
   ```

   ![](../media/gs-fix2-leave2-may-g28.png)

1. In the **Test your agent** panel, when prompted to choose a leave type, select from the available options such as **Casual**, **Emergency**, or **Unpaid**.

   ![](../media/lev-mgmt-sb-ex4-g6.png)

1. In the **Test your agent** panel, enter the leave start date in the required **yyyy-mm-dd** format using the below example value **(1)**, and then select the **Send (2)** button.

   ```
   2026-05-13
   ```

   ![](../media/gs-fix2-leave2-may-g20.png)

1. In the **Test your agent** panel, enter the leave end date in the required **yyyy-mm-dd** format using the below example value **(1)**, and then select the **Send (2)** button.

   ```
   2026-05-17
   ```

   > **Note:** In this test scenario, we are validating a leave request for more than 2 days.

   ![](../media/gs-fix2-leave2-may-g29.png)

1. In the **Test your agent** panel, enter the reason for your leave using the below example value **(1)**, and then select the **Send (2)** button.

   ```
   I need to take leave for personal work
   ```

   ![](../media/gs-fix2-leave2-may-g30.png)

1. Verify that the agent shows the **Processing** status while waiting for the email approval response.

   ![](../media/gs-fix2-leave2-may-g35.png)

1. In the **Inbox (1)**, select the **Microsoft Power Automate - Leave Approval (2)** email to view the leave request details.

   ![](../media/gs-fix2-leave2-may-g31.png)

1. Select **Approve (1)**, enter *Approved* in the **Comments (2)** box, and then select **Submit (3)** to finalize the leave approval.

   ![](../media/gs-fix2-leave2-may-g32.png)

1. The agent confirms the leave request, displaying an approval message with the leave duration details. 

   ![](../media/gs-fix2-leave2-may-g34.png)

## Task 2: Validate Data in Dataverse

In this task, you will navigate the Dataverse and validate the data updated by the agent.

1. On the **Power Apps** portal, ensure the environment is set to **ODL_User (1)**. From the left navigation menu, select **Tables (2)** and then choose **Leave Request (3)** from the list.

   ![](../media/cor-mn-e4-g-7.png)

1. On the **Leave Request columns and data** page, review the newly added records. Verify the following fields:  
      - **Employee Email** and **Employee Name** are automatically populated with your user details.  
      - **Leave Type** reflects the type of leave selected.  
      - **Start Date** and **End Date** match the values entered during testing.  
      - **Duration** displays the calculated number of leave days.  
      - **Status** shows the current approval status. 

         ![](../media/cor-mn-e4-g-11.png)  

         ![](../media/cor-mn-e4-g-9.png)

         > **Note:** The **Employee Email/User ID** field is automatically fetched by the system from your login context. You do not need to enter it manually.

## Summary

In this exercise, you tested the agent end-to-end by executing various prompts and scenarios. After completing the tests, the leave request data was verified to ensure it had been correctly updated in the Dataverse table.

### You have successfully completed this exercise, please continue to next one >>

   ![](../media/a-gs-g5.png)

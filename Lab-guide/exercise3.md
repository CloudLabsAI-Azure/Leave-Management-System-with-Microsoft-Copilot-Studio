# Exercise 3: Power Automate Approval Workflow 

### Estimated Duration: 40 Minutes

## Overview

In this exercise, you will continue building the leave management agent by adding more advanced capabilities. You will implement approval logic based on company policy: if the leave duration is two days or less, it will be automatically approved. Otherwise, it will go through an approval process. Once approved, the leave request will be finalized and recorded.

## Objectives

You will be able to complete the following tasks:

- Task 1: Update Dataverse

- Task 2: Complete leave request topic 

### Task 1: Update Dataverse

In this task, you will update the flow to modify the Dataverse table, changing the leave request status from 'Pending' to 'Approved' based on the defined conditions.

1. Now click the **plus (+) icon (1)** to add a new action for the root node.   

     ![](../media/lev-mgmt-sb-ex3-g24.png)

1. In the **Add an action** pane, search for **Update a row (1)**, and then select **Update a row (2)**.  

     ![](../media/lev-mgmt-sb-ex3-g25.png)

1. In the **Update a row** action, select **Leave Request (1)** for **Table name**, enter **/** in the **Row ID (2)** field, and then select **Insert expression (3)**.

     ![](../media/lev-mgmt-sb-ex3-g26.png)

1. In the **Expression** editor, enter the following expression in **(1)**, and then select **Update (2)**:

     ```
     outputs('Add_a_new_row')?['body/<logical_ID>_leaverequestid']
     ``` 

     ![](../media/lev-mgmt-sb-ex3-g27.png)

     > **Note:** The **Logical_ID** here refers to the ID that you have copied in the first exercise from power apps portal.

1. In the **Update a row** action, select the **+** icon. 

     ![](../media/gs-fix2-leave2-may-g5.png)

1. In the **Add an action** pane, search for **Skills (1)**, and then select **Respond to the agent (2)**. 

     ![](../media/lev-mgmt-sb-ex3-g29.png)

1. In the **Respond to the agent 1** action, select **Add an output**.

     ![](../media/lev-mgmt-sb-ex3-g30.png)

1. In the **Respond to the agent 1** action, select **Text** as the output type.

     ![](../media/lev-mgmt-sb-ex3-g31.png)

1. In the **Respond to the agent 1** action, enter **reply (1)** as the output name, and then enter the following message in the value field **(2)**.

     ```
     Your leave is approved from [start_date] to [end_date]
     ```

     ![](../media/lev-mgmt-sb-ex3-g32.png)

1. In the **Respond to the agent 1** action, select the **start_date (1)** placeholder, and then choose the **fx (2)** option.

     ![](../media/lev-mgmt-sb-ex3-g33.png)

1. In the expression editor, paste the expression in the editor box, and then select **Add**.

     ```
     outputs('Add_a_new_row')?['body/<Logical_ID>_startdate']
     ```

     ![](../media/gs-fix2-leave2-may-g6.png)

     > **Note**: The **Logical_ID** here refers to the ID that you have copied in the first exercise from power apps portal.

1. In the **Respond to the agent 1** action, select the **end_date (1)** placeholder, and then choose the **fx (2)** option.

     ![](../media/lev-mgmt-sb-ex3-g34.png)

1. In the expression editor, paste the expression in the editor box **(1)**, and then select **Add (2)**.

     ```
     outputs('Add_a_new_row')?['body/<Logical_ID>_enddate']
     ``` 

     ![](../media/lev-mgmt-sb-ex3-g35.png)

     > **Note**: The **Logical_ID** here refers to the ID that you have copied in the first exercise from power apps portal.

1. On the **Designer** page, review the flow and then select **Publish**.

     ![](../media/lev-mgmt-sb-ex2-g29.png)

1. In the **Your agent flow published successfully!** pop-up, select **Stay in Flow**.

     ![](../media/gs-fix-leave-may-g47.png)

1. On the top menu bar, click **Overview** to navigate to the flow details page.

     ![](../media/leav-man-e2-g-66.png)

1. On the **Overview (1)** page, select **Edit (2)**.

     ![](../media/lev-mgmt-sb-ex3-g37.png)

1. In the **Details** pane, enter the below value in the **Flow name (1)** field, and then select **Save (2)** to apply the changes.

     ```
     Leave Management Workflow
     ``` 

     ![](../media/leav-man-e2-g-107.png)

### Task 2: Complete leave request topic

In this task, you will create a topic that enables employees to apply for leave by configuring the required inputs and connecting it to the validation flow.

1. In **Copilot Studio**, select **Agents (1)**, and then choose **Leave Management Agent (2)**. 

     ![](../media/lev-mgmt-sb-ex2-g52.png)

1. Select **+7 (1)**, and then choose **Topics (2)**.

     ![](../media/gs-fix-leave-may-g11.png)

   > **Note:** If the **Topics** tab is directly visible on the screen, you can select it without clicking **+7**.

1. On the **Topics** page, select the **leave_request** topic.

     ![](../media/gs-fix2-leave2-may-g1.png)

1. Scroll to the bottom of the topic, and below the **reason** question node, select the **plus (+)** icon to add the next step in the flow. 

     ![](../media/leav-man-e3-g-20.png)

1. In the **Question** node after capturing the reason, click **Add a tool (1)**. From the list of available tools, select **Leave Validation Flow (2)** to connect the flow with the validation process. 

     ![.](../media/cor-mn-e5-g-77.png)

1. On the **Authoring canvas**, click **Variables (1)** from the top menu. Under the **Browse (2)** tab, expand the **Topic (3)** section and select all the listed variables by checking the boxes **(4)**.   

     ![](../media/cor-mn-e5-g-78.png)

1. On the **Power Automate inputs** card, click the **ellipsis (…) (1)** next to the **startDate** field. From the **Select a variable** pane, choose **startDate (2)** to map the variable.

     ![](../media/lev-mgmt-sb-ex2-g67.png)

1. On the **Power Automate inputs** card, click the **ellipsis (…) (1)** next to the **endDate** field. From the **Select a variable** pane, choose **endDate (2)** to map the variable. 

     ![](../media/lev-mgmt-sb-ex2-g68.png)

1. On the **Power Automate inputs** card:  

     - Click the **ellipsis (…) (1)** next to the **employeeEmail** field.  
     - In the **Select a variable** pane, switch to the **System (2)** tab.  
     - Search for **User.Email (3)**.  
     - Select **User.Email (4)**.  

          ![](../media/lev-mgmt-sb-ex2-g69.png)

1. On the **Outputs (2)** section, click the **plus (+) icon** to add the next step in the flow. **(1)**

     ![](../media/lev-mgmt-sb-ex3-g40.png)

1. On the **Outputs (2)** section, click **Add a tool (1)** and select **Leave Management Workflow (2)** from the list of tools. 

     ![](../media/lev-mgmt-sb-ex3-g41.png)

1. On the **Authoring canvas**, click **Variables (1)** from the top menu. Under the **Browse (2)** tab, expand the **Topic (7) (3)** section and select the **reply (4)** variable by checking the box.   

     ![](../media/cor-mn-e5-g-79.png)

     > If you are not able to see the variables option, please click on **...** menu and select **Variables**

      ![](../media/lvimg56.png)

1. On the **Action** card, set the value for **employeeEmail (String)**: 

     - Click the **ellipsis (…) (1)**.  
     - In the **Select a variable** panel, go to the **System (2)** tab.  
     - Search for **User.Email (3)**.  
     - Select **User.Email (4)** from the results.  

          ![](../media/lev-mgmt-sb-ex3-g43.png)

1. On the **Action** card, set the value for **employeeName (String)**: 

     - Click the **ellipsis (…) (1)**.  
     - In the **Select a variable** panel, go to the **System (2)** tab.  
     - Search for **User.FirstName (3)**.  
     - Select **User.FirstName (4)** from the results. 

          ![](../media/gs-fix2-leave2-may-g11.png)

1. On the **Action** card, set the value for **leaveType (String)** by selecting the **ellipsis (…) (1)**, choosing the **Formula (2)** tab, entering the formula **(3)**, and then selecting **Insert (4)**.

     ```
     Text(Topic.leave_type)
     ```

     ![](../media/lev-mgmt-sb-ex3-g45.png)

1. On the **Action** card, set the value for **reason (String)**: 

     - Click the **ellipsis (…) (1)**.  
     - In the **Select a variable** panel, choose the **Custom (2)** tab.  
     - Select **reason (Topic.reason) (3)** from the list.  

          ![](../media/lev-mgmt-sb-ex3-g46.png)

1. On the **Action** card, set the value for **durationDays (String)**: 

     - Click the **ellipsis (…) (1)**.  
     - In the **Select a variable** panel, go to the **Custom (2)** tab.  
     - Select **duration (Topic.duration) (3)** from the list.  

          ![](../media/lev-mgmt-sb-ex3-g47.png)

1. On the **Action** card, set the value for **balance (String)**:

     - Click the **ellipsis (…) (1)**.  
     - In the **Select a variable** panel, go to the **Custom (2)** tab.  
     - Select **balance (Topic.balance) (3)** from the list.  

          ![](../media/lev-mgmt-sb-ex3-g48.png)

1. On the **Action** card, set the value for **startDate (String)**:

     - Click the **ellipsis (…) (1)**.  
     - In the **Select a variable** panel, go to the **Custom (2)** tab.  
     - Select **startDate (Topic.startDate) (3)** from the list.  

          ![](../media/lev-mgmt-sb-ex3-g49.png)

1. On the **Action** card, set the value for **endDate (String)**:  

     - Click the **ellipsis (…) (1)**.  
     - In the **Select a variable** panel, go to the **Custom (2)** tab.  
     - Select **endDate (Topic.endDate) (3)** from the list.  

          ![](../media/lev-mgmt-sb-ex3-g50.png)

1. On the **Outputs (1)** section, click the **plus icon (1)** and select **Send a message (2)**. 

     ![](../media/leav-man-e3-g-36.png)

1. On the **Message** step:  

     - Click on the **variable icon (1)**.  
     - In the **Select a variable** pane, choose the **Custom (2)** tab.  
     - Type **reply (3)** in the search box.  
     - Select **reply (4)** from the results. 

          ![](../media/leav-man-e3-g-37.png)

1. On the **Message** step, click the **plus (+) icon** to add the next action in the flow. 

     ![](../media/leav-man-e3-g-38.png)

1. On the **Message** step, expand the options and select **Topic management (1)**, then click **End conversation (2)** to close the flow. 

     ![](../media/leav-man-e3-g-39.png)

1. At the top-right corner of the page, click **Save** to store the changes made to the topic.  

     ![](../media/lev-mgmt-sb-ex2-g70.png)

<validation step="786e3497-70e3-44d4-997f-45095642a4af" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

## Summary

In this exercise, you continued building the leave management agent by adding advanced capabilities. You implemented approval logic based on company policy: leaves of two days or less were automatically approved, while longer leaves went through an approval process. Once approved, the leave requests were finalized and recorded.

### You have successfully completed this exercise. Please continue to the next one >>

   ![](../media/a-gs-g4.png)

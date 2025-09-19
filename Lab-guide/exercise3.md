# Exercise 3: Power Automate Approval Workflow 

### Estimated Duration: 30 Minutes

## Overview

In this exercise, you will continue building the leave management agent by adding more advanced capabilities. You will implement approval logic based on company policy: if the leave duration is two days or less, it will be automatically approved. otherwise, it will go through an approval process. Once approved, the leave request will be finalized and recorded.

## Objectives

You will be able to complete the following tasks:

- Task 1: Create Approval Flow

- Task 2: Update Dataverse

- Task 3: Complete leave request topic 

### Task 1: Create Approval Flow

In this task, you will enhance the Leave Management Workflow by incorporating approval logic and advanced management features to handle leave requests more efficiently.

1. Navigate to **flows (1)** from the side menu and select **Leave Management Workflow**.

1. Once in the **Leave Management Workflow** overview pane, navigate to **Designer** pane to edit the flow.

1. On the **Designer** canvas, click the **plus (+) icon (1)** to add a new action. In the **Add an action** dialog, type **Condition (2)** in the search bar and select **Condition (3)** under the **Control** section.

   ![](../media/leav-man-e2-g-89.png)

1. In the **Condition** pane, type **/** in the field (1) and select **Insert expression (2)** from the dropdown list.

   ![](../media/cor-mn-e4-g-22.png)

1. In the **Expression** editor, type **int() (1)** and keep the cursor inside the parentheses. Click **Dynamic content (2)** and select **durationDays (3)** to insert it into the expression. 

   ![](../media/cor-mn-e4-g-25.png)

1. In the **Expression** editor, verify that the expression is set **(1)**. Once done, click **Add (2)** to insert it into the condition. 

   ![](../media/cor-mn-e4-g-24.png)

   > **Note:** The expression reference (for example, `triggerBody()?['text_4']`) may vary depending on the order in which inputs are added in the **When an agent calls the flow** step. The number (`text_4`, `text_5`, etc.) is auto-generated

1. In the **Condition** action, under the **False** branch, click the **plus (+) icon (1)** to add a new action. In the **Add an action** dialog, type **Start and wait for an approval (2)** in the search bar and select **Start and wait for an approval (3)** under **Standard approvals**.

   ![](../media/leav-man-e2-g-91.png)

1. In the **Start and wait for an approval** action, configure the parameters:  
   - From the **Approval type** drop-down, select **Approve/Reject - Everyone must approve (1)**.  
   - In the **Title** field, enter **Leave Approval (2)**.  
   - In the **Assigned to** field, type the user’s email address **(3)** and select the matching account from the suggestions **(4)**. 

      ![](../media/leav-man-e2-g-92.png)

1. In the **False** branch of the approval, click the **plus (+) icon (1)** to add a new action.  
   - In the **Add an action** dialog, type **Condition (2)** in the search bar.  
   - Under the **Control** section, select **Condition (3)**.  

      ![](../media/leav-man-e2-g-93.png)

1. In the **Condition 1** action, configure the condition as follows:  
   - Select **Outcome (1)** from the dynamic content.  
   - From the operator drop-down, select **is equal to (2)**.  
   - In the value field, enter **Approve (3)**. 

      ```
      outputs('Start_and_wait_for_an_approval')?['body/outcome']
      ``` 

      ![](../media/leav-man-e2-g-94.png)

      > This condition evaluates whether the leave request has been approved by retrieving the response from the previous approval step.

1. In the **False** branch of **Condition 1**, click the **plus (+) icon (1)** to add a new action.  
   - In the **Add an action** dialog, type **Respond to the agent (2)** in the search bar.  
   - Under **Skills**, select **Respond to the agent (3)**.  

   ![](../media/leav-man-e2-g-95.png)

1. In the **Respond to the agent** action, set the output name to **reply (1)** and enter **the request is rejected (2)** as the response message.

   ![](../media/leav-man-e2-g-96.png)

1. In the **False** branch, after the **Respond to the agent** action, click the **plus (+) icon (1)** to add a new action.  
   - In the **Add an action** dialog, type **Terminate (2)** in the search bar.  
   - Under the **Control** section, select **Terminate (3)**. 

      ![](../media/leav-man-e2-g-97.png)

1. In the **Terminate** action, set the **Status** field to **Succeeded** to complete the workflow after rejection.

   ![](../media/leav-man-e2-g-98.png)

### Task 2: Update Dataverse

In this task, you will update the flow to modify the Dataverse table, changing the leave request status from 'Pending' to 'Approved' based on the defined conditions.

1. In the **True** branch of **Condition 1**, click the **plus (+) icon (1)** to add a new action.  
   - In the **Add an action** dialog, type **Update a row (2)** in the search bar.  
   - Under **Microsoft Dataverse**, select **Update a row (3)**.  

      ![](../media/leav-man-e2-g-99.png)

1. On the **Update a row** action:  
   - Select **Leave Request (1)** as the table name.  
   - In the **Row ID (2)** field, paste the expression (3) to reference the row created earlier.  
   - Click **Add (4)** to confirm the expression.  
   - In the **Status (5)** field, type **Approved**.  

      ```
      outputs('Add_a_new_row')?['body/<logical_ID>_leaverequestid']
      ``` 

      ![](../media/leav-man-e2-g-100.png)

      > **Note:** The <Logical_ID> here refers to the ID that you have copied in the first exercise from power apps portal.

1. On the **Update a row** action, click the **plus (+) button (1)** to add a new action.  
   - In the search box, type **Respond to the agent (2)**.  
   - From the **Skills** section, select **Respond to the agent (3)**. 

      ![](../media/leav-man-e2-g-101.png)

1. On the **Respond to the agent 1** action, in the **reply (1)** field, enter the message **You leave is approved from [start_date] to [end_date] (2)** and paste the provided expressions for **start_date** and **end_date**.

   ```
   outputs('Add_a_new_row')?['body/<Logical_ID>_startdate']
   ``` 

   ```
   outputs('Add_a_new_row')?['body/<Logical_ID>_enddate']
   ``` 

   ![](../media/leav-man-e2-g-102.png)

   The completed flow should now look like the following:

   - The flow starts with **When an agent calls the flow**.  
   - A new record is created in the **Leave Request** table using **Add a new row**.  
   - A **Condition** checks the leave duration.  
   - If **True**, the process continues.  
   - If **False**, the flow triggers **Start and wait for an approval**.  
      - Inside this branch, another **Condition** validates the approval outcome.  
         - If **Approved**, the flow updates the leave record with status **Approved** and sends a response back to the agent.  
         - If **Rejected**, the flow responds to the agent that the request is rejected and then terminates successfully.  
   - The final steps include **Update a row** to mark approval in Dataverse, followed by a confirmation response through **Respond to the agent 1**. 

     ![](../media/leav-man-e2-g-103.png)

1. At the top-right corner of the flow designer, click **Publish** to save and activate your flow.

   ![](../media/leav-man-e2-g-104.png)

1. On the top menu, click **Overview** to return to the flow overview page after publishing.

   ![](../media/leav-man-e2-g-105.png)

1. On the **Overview** page, under the **Details** section, click **Edit** to update the flow details such as the name and description.

   ![](../media/leav-man-e2-g-106.png)

1. In the **Details** pane, enter **Leave Management Workflow (1)** in the **Flow name** field. Then, click **Save (2)** to apply the changes.  

   ![](../media/leav-man-e2-g-107.png)

### Task 3: Complete leave request topic

In this task, you will complete the leave request topic by implementing the logic to add new leave requests and update existing records in Dataverse with the request details.

1. On the **Outputs (2)** section, click the **plus (+) icon** to add the next step in the flow. **(1)**

   ![](../media/leav-man-e3-g-26.png)

1. On the **Outputs (2)** section, click **Add a tool (1)** and select **Leave Management Workflow (2)** from the list of tools. 

   ![](../media/leav-man-e3-g-27.png)

1. On the **Action** card, set the value for **employeeEmail (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, go to the **System (2)** tab.  
   - Search for **User.Email (3)**.  
   - Select **User.Email (4)** from the results.  

      ![](../media/leav-man-e3-g-28.png)

1. On the **Action** card, set the value for **employeeName (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, go to the **System (2)** tab.  
   - Search for **User.FirstName (3)**.  
   - Select **User.FirstName (4)** from the results. 

      ![](../media/leav-man-e3-g-29.png)

1. On the **Action** card, set the value for **leaveType (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, switch to the **Formula (2)** tab.  
   - Enter the formula **Text(Topic.leave_type) (3)**.  
   - Click **Insert (4)** to apply the formula.  

      ![](../media/leav-man-e3-g-30.png)

1. On the **Action** card, set the value for **reason (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, choose the **Custom (2)** tab.  
   - Select **reason (Topic.reason) (3)** from the list.  

      ![](../media/leav-man-e3-g-31.png)

1. On the **Action** card, set the value for **durationDays (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, go to the **Custom (2)** tab.  
   - Select **Duration (Topic.Duration) (3)** from the list.  

      ![](../media/leav-man-e3-g-32.png)

1. On the **Action** card, set the value for **Balance (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, go to the **Custom (2)** tab.  
   - Select **Balance (Topic.Balance) (3)** from the list.  

      ![](../media/leav-man-e3-g-33.png)

1. On the **Action** card, set the value for **StartDate (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, go to the **Custom (2)** tab.  
   - Select **StartDate (Topic.StartDate) (3)** from the list.  

      ![](../media/leav-man-e3-g-34.png)

1. On the **Action** card, set the value for **endDate (String)**:  
   - Click the **ellipsis (…) (1)**.  
   - In the **Select a variable** panel, go to the **Custom (2)** tab.  
   - Select **EndDate (Topic.EndDate) (3)** from the list.  

      ![](../media/leav-man-e3-g-35.png)

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

   ![](../media/leav-man-e3-g-41.png)

1. You have successfully completed the creation of the agent. It is now fully equipped with all intended capabilities and will be ready for testing in the next task.

## Summary

In this exercise, you continued building the leave management agent by adding advanced capabilities. You implemented approval logic based on company policy: leaves of two days or less were automatically approved, while longer leaves went through an approval process. Once approved, the leave requests were finalized and recorded.








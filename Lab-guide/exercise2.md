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

1. In the **Add a trigger** pane, search for **When an agent calls the flow (1)** and select **When an agent calls the flow (2)** from the list.

   ![](../media/leav-man-e2-g-24.png)

1. On the **Agent flows – Designer** page, under the **Parameters** tab, click **+ Add an input**.  

   ![](../media/leav-man-e2-g-25.png)

1. In the **Choose the type of user input** section, select **Date** to capture date values in the flow.  

   ![](../media/leav-man-e2-g-26.png)

1. In the **Parameters** tab, set the first input as **startDate (1)**. Then click **+ Add an input (2)** to add another parameter.   

   ![](../media/leav-man-e2-g-27.png)

1. In the **Choose the type of user input** section, select **Date** again to add another date parameter for the flow.  

   ![](../media/leav-man-e2-g-28.png)

1. In the **Parameters** tab, add another date input and set its name as **endDate**. Then click **+ Add an input** to create an additional parameter. 

   ![](../media/leav-man-e2-g-29.png)

1. In the **Choose the type of user input** section, select **Text** to add a text-based parameter. 

   ![](../media/leav-man-e2-g-30.png)

1. In the **Parameters** tab, add a text input and set its name as **employeeEmail**.   

   ![](../media/leav-man-e2-g-31.png)

1. On the **Designer** canvas, click the **plus (+)** icon below **When an agent calls the flow** to add the next action.  

   ![](../media/leav-man-e2-g-32.png)

1. In the **Add an action** pane, search for **Compose (1)** and select **Compose (2)** from the **Data Operation** category.  

   ![](../media/leav-man-e2-g-33.png)

1. In the **Compose** action, click inside the **Inputs** field, type **/** **(1)**, and then select **Insert expression (2)**.

   ![](../media/leav-man-e2-g-34.png)

1. In the **Compose** action, paste the expression into the editor box **(1)** and then click **Add (2)** to insert it.

   ```
   add(div(sub(ticks(triggerBody()?['date_1']), ticks(triggerBody()?['date'])), 864000000000), 1)
   ```

   ![](../media/leav-man-e2-g-35.png)

1. On the **Compose action** pane, verify that the entered expression is applied successfully and appears in the **Inputs** field as shown.

   ![](../media/leav-man-e2-g-36.png)

1. On the **Designer** page, below the **Compose** action, click the **plus (+) icon** to add a new action **(1)**.  
   - In the search box, type **List rows (2)**.  
   - Under **Microsoft Dataverse (3)**, select **List rows (4)**.  

      ![](../media/leav-man-e2-g-37.png)

1. On the **Create connection** pane, enter **Microsoft Dataverse (1)** as the connection name, select **Oauth (2)** as the authentication type, and click **Sign in (3)** to establish the connection.   

   ![](../media/leav-man-e2-g-38.png)

1. On the **Sign in** page, enter the provided **ODL user account (1)** and click **Next (2)** to continue. 

   ![](../media/leav-man-e2-g-39.png)

1. On the **Enter password** page, type the provided **password (1)** and click **Sign in (2)** to proceed.  

   ![](../media/leav-man-e2-g-40.png)

1. On the **Stay signed in?** page, click **Yes** to remain signed in. 

   ![](../media/leav-man-e2-g-41.png)

1. On the **Confirmation required** page, click **Allow access** to grant permission for Microsoft Dataverse. 

   ![](../media/leav-man-e2-g-42.png)

1. In the **List rows** action:  
   - Select **Leave Request (1)** in the **Table name** field.  
   - Enter **cr5c1_balancedays (2)** in the **Select columns** field to fetch leave balance days.  
   - In the **Filter rows** field, type **cr5c1_employeeemail eq (3)** to filter by employee email.  
   -   - Click the **thunderbolt (4)** icon to insert the **employeeEmail (5)** parameter dynamically.
   - In the **Sort By** field, enter **createdon desc (6)** to sort by latest record.  
   - In the **Row count** field, type **1 (7)** to return only the most recent record.  

      ![](../media/leav-man-e2-g-46.png)

      ![](../media/leav-man-e2-g-47.png)

      ![](../media/leav-man-e2-g-48.png)

      > **Note**: The prefix **cr5c1_** is the schema prefix automatically generated by Dataverse for this environment. Your prefix may differ depending on the environment setup. 

1. On the **List rows** action, click the **plus (+) (1)** icon to add a new action.  
   - In the **search bar (2)**, type **Condition**.  
   - From the **Control (3)** section, select **Condition**.  

      ![](../media/leav-man-e2-g-49.png)

1. On the **Condition expression** field:  
   - Type **/** (1).  
   - Click **Insert expression (2)**.
   - Paste the expression **(3)**.  
   - Click **Add (4)** to insert it.
   - Select the operator **is greater than (5)**.  
   - Enter **0 (6)** as the comparison value.  

   ```
   length(outputs('List_rows')?['body/value'])
   ```

      ![](../media/leav-man-e2-g-50.png)

      ![](../media/leav-man-e2-g-51.png)

      ![](../media/leav-man-e2-g-52.png)

1. Under the **False** branch of the **Condition**, click the **plus (+) (1)** button to add a new action, type **Compose (2)** in the search box, and from the **Data Operation** section select **Compose (3)**.

   ![](../media/leav-man-e2-g-56.png)

1. On the **Condition expression** field:  
   - Type **/** (1).  
   - Click **Insert expression (2)**.  
   - Paste the expression **(3)**.  
   - Click **Add (4)** to insert it.  

   ```
   sub(24, outputs('Compose'))
   ```

   ![](../media/leav-man-e2-g-57.png)

1. Under the **True** branch of the **Condition**, click the **plus (+) (1)** button to add a new action, type **Compose (2)** in the search box, and from the **Data Operation** section select **Compose (3)**.

   ![](../media/leav-man-e2-g-58.png)

1. On the **Condition expression** field:  
   - Type **/** **(1).**  
   - Click **Insert expression (2)**.  
   - Paste the expression **(3)**.  
   - Click **Add (4)** to insert it.  

   ```
   sub(first(outputs('List_rows')?['body/value'])?['crf88_balancedays'], outputs('Compose'))
   ```

   ![](../media/leav-man-e2-g-54.png)

1. Under the **True** branch of the condition, click the **plus (+) icon (1)**.  
   - In the search bar, type **Respond to the agent (2)**.  
   - From the **Skills** section, select **Respond to the agent (3)**.  

   ![](../media/leav-man-e2-g-59.png)

1. In the **Respond to the agent** action: 
   - Enter **Duration (1)** as the output name.  
   - Type **/** (2) to open the expression editor.  
   - Paste the expression **(3)**.  
   - Click **Add (4)** to insert it. 
   - Click **Add an output (5)** and select **Text**.

   ```
   outputs('Compose')
   ``` 

   ![](../media/leav-man-e2-g-60.png) 

1. In the **Respond to the agent** action, click **Add an output** and select **Text**.  
   - Enter **Balance (1)** as the output name.  
   - Type **/** and open the expression editor.  
   - Paste the expression **(2)**.  
   - Click **Add (3)** to insert it. 

   ```
   outputs('Compose_2')
   ```

   ![](../media/leav-man-e2-g-61.png)

1. In the **False** branch of the Condition, click the **plus (+) icon (1)**, search for **Respond to the agent (2)**, and select **Respond to the agent (3)** from the Skills section. 

   ![](../media/leav-man-e2-g-62.png)

1. On the **Respond to the agent** pane:  
   - In the **Duration (1)** field, paste the expression **(2)** for duration.  
   
      ```
      outputs('Compose')
      ```

   - In the **Balance (3)** field, paste the expression **(4)** for balance. 
      
      ```
      outputs('Compose_2')
      ```

   ![](../media/leav-man-e2-g-34.png)

1. In the **Compose** action, click inside the **Inputs (1)** field, then select **Insert expression (2)**. 

   ![](../media/leav-man-e2-g-34.png)

1. In the **Compose** action, click inside the **Inputs (1)** field, then select **Insert expression (2)**. 

   ![](../media/leav-man-e2-g-34.png)

1. In the **Compose** action, click inside the **Inputs (1)** field, then select **Insert expression (2)**. 

   ![](../media/leav-man-e2-g-34.png)

1. In the **Compose** action, click inside the **Inputs (1)** field, then select **Insert expression (2)**. 

   ![](../media/leav-man-e2-g-34.png)

1. In the **Compose** action, click inside the **Inputs (1)** field, then select **Insert expression (2)**. 

   ![](../media/leav-man-e2-g-34.png)

## Summary

In this exercise, you created a Copilot Studio agent that served as the foundation for your store operations assistant. You defined the agent’s purpose by assigning it a name and description, and connected it to key knowledge sources such as the product catalog, store policy documents, and website content. These steps enabled the agent to deliver relevant, AI-powered responses based on indexed information.

### You have successfully completed this exercise, please continue to next one >>

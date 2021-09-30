---
lab:
    title: 'Lab: SLAs '
    module: 'Module 3: Service Level Management'
---

# Module 3: Service Level Management
----

## Practice Lab 1 – Service Management Setup

### Scenario
-------

As a customer service manager at City Power & Light, you need to create
service level agreements to provide defined hours of service and response times both for accepting the case and for resolving the case. You will create an SLA and see the standard functionality. You will amend the SLA to add actions with Power Automate. To prepare for the SLA you need to setup Holidays Schedules, Working Hours and SLA KPIs.
You must test the SLA for successful and failed outcomes.

**N.B.    To work in a shared environment add your initials wherever the [xx] place holder is used.**

### Exercise 1 – Setup Customer Service Hub for SLAs
----

SLA require SLA KPIs. These are performance indicators, such as First Response By or Resolve by, that you'd like to track. They can only be created for tables enabled for SLAs.
For SLAs to adhere to working hours, Holiday schedules and Service schedules need to be created.

### Task 1 – Create SLA KPIs

In this task, you will create SLA KPIs for First Response and Resolution

1.  In your browser, navigate to office.com/apps/Business Apps.

1.  Launch **Customer Service Hub**.

1.  Click on the **Sitemap** button in the bottom left corner and click **Service Management.**

1.  Click on **SLA KPIs** in the **Service Terms** section.
1. Click **Save**.
1.  Click **New**.

The New SLA KPI page appears.
    -  Name: Type  **FirstResponseBy [xx]**
    -   Entity Name:    Select **Case**
    -   KPI Field: Select the **FirstResponseByKPI** field
    -  Applicable From: Select **Created On**, (the warning and failure start time for an SLA will be calculated from the date and time when the entity was created)

1. Click **Save**.
1. Click **New** to create another KPI.
    -  Name: **ResolveBy [xx]**
    -  Entity Name:    **Case**
    -  KPI Field:  **ResolveByKPI** 
    -  Applicable From: **Created On**
1. Click **Save & Close**.
1. Select both KPIs and click **Activate**, then confirm activation by clicking **Activate**
---
### Task 2 – Define Pause for SLAs
1. Go to **Service Configuration Settings / Select Pause Status**
1. Select the Case table and move **On Hold** and **Waiting** to the Selected list. **Save** the settings.



---
### Task 3 – Set up Holidays

In this task, you will 
    - create a new holiday schedule
    - Add at least one holiday.

1. Navigate to  ** Service Management > Service Terms >Holiday Schedule**.
1.  Click **New**. Type **Holiday UK [xx]** in the Name and click **Create**

1.  Click **New** in the Holidays Section
1.  Type **May Day** in the Name. 
1.  Enter the first Monday in May in the Start Date.
1.  Enter the same in the End Date. 
1.  Verify that Duration is 1 day and click **OK**. 
---
### Task 4 Set up the Customer Service Schedule
In this task you will 
    - Create a new Customer Service Schedule. 
    - Assign Work Hours. 
    - Associate the Holiday Schedule created earlier 
Detailed Steps 
1.  Navigate to  **> Service Management > Service Terms >Holiday Schedule**.
1.  Click **New**. 
1.  Type **UK Service Calendar [xx]** in the Name field and click **Create**. 
    - For Weekly Schedule : Select **Are the same each day** and **Monday to Friday**
    -  Click **Set Work Hours**. 
    -  Verify that on the first Work Hours line it says **9:00 AM** in the Start column and **5:00 PM** in the End column. 
    -  Click **Add Break**. 
    
    -  In the line that says Break, change the Start column to be **12:00 PM** and the End column to be **1:00 PM**
    
    -  Verify that the last Work Hours line shows **1:00 PM** for the Start and **5:00 PM** for the End

1.  Click **OK**

    1.  In the Holiday Schedule area: 
    -  Change the radio button to be **Observe**. 
    -  Use the lookup to select the **Holiday UK [xx]** created earlier.
    -  Select the appropriate time zone (GMT 0 Dublin, Edinburgh, Lisbon, London) 
    -  Click **Save and Close**. 
---

## Exercise 2 - Service Level Agreements

### Task 1 Create a Service Level Agreement
In this task you will 
    - Create a new Service Level Agreement. 
    - Associate the Customer Service Schedule created in the previous step. 
    - Add SLA Details to show Failure and Warning times
Detailed Steps 
1.  Select  **> Service Management > Service Terms > Service Level Agreements**. 
1.  Click **New**. 
1.  Type **Standard UK SLA [xx]** in the Name
1.  Select **Case** for the Primary Entity
1.  Click **Save**

1.  Click **New SLA Item**
    -  Name : **Standard First Response**
    -  KPI: **First Response By[xx]**
    -  Allow pause and Resume: **Yes**
    -  Business Hours: **UK Service Calendar [xx]**
    -  In the Applicable When area, click **Add row**
    -  Enter **Priority(Case) Does not equal Low**. <br>
        ![image ](https://raw.githubusercontent.com/fawcettm/MB-230-Dynamics365forCustomerService/master/Allfiles/Resources/Mod3/sla1when.png) <br>
1.  In the Success Conditions area
1.  Add row and enter **First Response Sent Equals Yes**

       ![image ](https://raw.githubusercontent.com/fawcettm/MB-230-Dynamics365forCustomerService/master/Allfiles/Resources/Mod3/sla1success.png) <br>
1.  In the Warn and Fail Duration set the following (for testing purposes)
    -  Set the Warn After to **3 minutes **
    -  Set the Failure After to **5 minutes **
          ![image ](https://raw.githubusercontent.com/fawcettm/MB-230-Dynamics365forCustomerService/master/Allfiles/Resources/Mod3/sla1warn.png) <br>
l. Click **Save**. Leave the Actions for later.
1.  Click **Save & Close**. 
1.  On the SLA record Click **Activate**. Confirm Activation.
1.  Click **Set As Default**. (Only one SLA will be default so liaise with other students to test your SLA. Click **OK** to confirm.
 ---
### Task 2 Test SLA Built In Behaviour

In this task you will
* Create 4 test cases for any account to test the SLA.
1. Create cases for an account with case titles as follows:
    - a.    **1 test success case resolution** . (can be created with Quick Create if preferred
    - b.  **2 test success first response**
    - c.  **3 test failure**
    - d.  **4 test No SLA**, this needs to be created with a full New Case record so that you can change the priority to Low)

1.  Resolve the 1 test success case resolution within 5 minutes of creation.  
1.  Update the 2 test success first response record set the First Response Sent to Yes
1. Leave the 3 test failure case
1. Observe the SLA Details on the 4 case records. 
---

### Task 3 Prepare to test Configure Actions for the SLA item
In this task you will create a customer service team in Teams and add a channel for SLA issues in order to test the notification functionality from the SLA using Power Automate.
1.  From Office launch Teams
1.  Create a new public team called **Customer Service [xx]**
1.  Add a channel called **SLA Issues**
1.  Return to D365 **Customer Service Hub / Service Management/ Service Terms / Service Level Agreements**
1.  Open the **Standard UK SLA [xx]**, click **Deactivate** and confirm **Deactivate**, select the first response SLA item, and then select **Edit SLA Item**. The SLA item page appears.
1.  In the Actions area, select **Configure Actions**. The Power Automate application opens on a new tab (you may need to enable the PopUp) SLAs. <br>
        ![image powerautomate ](https://raw.githubusercontent.com/fawcettm/MB-230-Dynamics365forCustomerService/master/Allfiles/Resources/Mod3/sla1PA.png)
1.  Perform the following steps in Power Automate:
1.  
    * 1.1 Accept the default settings or select the ellipsis to configure a connection.
    * 1.1 Select **Continue**. The predefined flow that's specific to the SLA appears.
#### Note
**We recommend that you don't edit the predefined flow, which can cause breaks in the flow, and the SLA might not work as defined.** <br>
    ![image](https://raw.githubusercontent.com/fawcettm/MB-230-Dynamics365forCustomerService/master/Allfiles/Resources/Mod3/sla1Flow.png)

1. Select **Switch**. The following condition steps are displayed for each of which you can configure a required action:
    o   Is Near Non-Compliance: Will run when the warning time is reached for the SLA.
    o   Is Succeeded: Will run when the SLA succeeds.
    o   Is Non-compliant: Will run when the SLA fails.

    ![image](https://raw.githubusercontent.com/fawcettm/MB-230-Dynamics365forCustomerService/master/Allfiles/Resources/Mod3/sla1PAfail.png)

1.  Select **[Do not delete or update] Is Near Non-Compliance** click **Add an action**.
    o   Select Teams / post a message in chat or channel, and configure the following 
    o   Post as: Flow Bot
    o   Post In: Channel
    o   Team: Customer Service [xx]
    o   Channel: SLA Issues
    o   Message: Warning! SLA nearing non compliance and use the trigger outputs to tailor the message. Refer to docs and open data protocol to retrieve the names for the case and owner if time. 

1.  Repeat the steps to configure the actions for Is Succeeded and Is Non-compliant.
A sample screenshot of the configured action is as follows.

    ![Image](https://raw.githubusercontent.com/fawcettm/MB-230-Dynamics365forCustomerService/master/Allfiles/Resources/Mod3/sla1PATeam.png)
1. Save and exit Power Automate.
#### Note
More information: [Link Configure connectors in Power Automate](https://docs.microsoft.com/en-us/connectors/commondataserviceforapps/)
1.  Select **Save & Close** on the SLA item dialog box.
1.  Define as many SLA items as you need.
1.  Select **Activate**. The SLA is activated.
1.  **Set as Default** (Deactivating & Reactivating the SLA will not persist the Default SLA flag)
1.  Test


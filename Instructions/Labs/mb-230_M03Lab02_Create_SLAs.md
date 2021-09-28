---
lab:
    title: 'Lab: SLAs '
    module: 'Module 3: Service Level Management'
---

# Module 3: Service Level Management
==================================

## Practice Lab 1 – Service Management Setup

### Scenario
--------

As a customer service manager at City Power & Light, you need to create
service level agreements to provide defined hours of service and response times both for accepting the case and for resolving the case. You will create an SLA and see the standard functionality. You will amend the SLA to add actions with Power Automate. To prepare for the SLA you need to setup Holidays Schedules, Working Hours and SLA KPIs.
You must test the SLA for successful and failed outcomes.

** N.B.    To work in a shared environment add your initials wherever the [xx] place holder is used. **

### Exercise 1 – Setup Customer Service Hub for SLAs
-------------------------

SLA require SLA KPIs. These are performance indicators, such as First Response By or Resolve by, that you'd like to track. They can only be created for tables enabled for SLAs.
For SLAs to adhere to working hours, Holiday schedules and Service schedules need to be created.

### Task 1 – Create SLA KPIs

In this task, you will create SLA KPIs for First Response and Resolution

1.  Navigate to <wwllab006.crm.dynamics.

1.  Open **Customer Service Hub**.

1.  Click on the **Sitemap** button in the bottom left corner and click **Service Management.**

1.  Click on **SLA KPIs** in the **Service Terms** section.
1. Click **Save**.
1.  Click **New**.

The New SLA KPI page appears.
*  Name: Type  ** FirstResponseBy [xx] **
*   Entity Name:    Select ** Case  **
*   KPI Field: Select the ** FirstResponseByKPI ** field
*  Applicable From: Select ** Created On **, (the warning and failure start time for an SLA will be calculated from the date and time when the entity was created)

1. Click **Save**.
1. Click **New** to create another KPI.
*  Name: ** ResolveBy [xx] **
*  Entity Name:    ** Case  **
*  KPI Field:  ** ResolveByKPI ** 
*  Applicable From: ** Created On **
1. Click **Save & Close**.
1. Select both KPIs and click **Activate**, then confirm activation by clicking **Activate**

### Task 2 – Define Pause for SLAs
1. Go to **Service Configuration Settings / Select Pause Status**
1. Select the Case table and move ** On Hold** and **Waiting** to the Selected list. **Save** the settings.




### Task 3 – Set up Holidays

In this task, you will * create a new holiday schedule
* Add at least one holiday.

1. Navigate to  ** Service Management > Service Terms >Holiday Schedule**.
1.  Click **New**. Type **Holiday UK [xx]** in the Name and click **Create**

1.  Click **New** in the Holidays Section
1.  Type **May Day** in the Name. 
1.  Enter the first Monday in May in the Start Date.
1.  Enter the same in the End Date. 
1.  Verify that Duration is 1 day and click **OK**. 

### Task 4 Set up the Customer Service Schedule
In this task you will 
* Create a new Customer Service Schedule. 
* Assign Work Hours. 
* Associate the Holiday Schedule created earlier 
Detailed Steps 
1.  Navigate to  **> Service Management > Service Terms >Holiday Schedule**.
1.  Click **New**. 
1.  Type **UK Service Calendar [xx]** in the Name field and click **Create**. 
a.  For Weekly Schedule : Select **Are the same each day** and **Monday to Friday**
b.  Click **Set Work Hours**. 
c.  Verify that on the first Work Hours line it says **9:00 AM** in the Start column and **5:00 PM** in the End column. 
d.  Click **Add Break**. 

e.  In the line that says Break, change the Start column to be **12:00 PM** and the End column to be **1:00 PM **

f.  Verify that the last Work Hours line shows **1:00 PM** for the Start and **5:00 PM** for the End

g.  Click **OK**

1.  In the Holiday Schedule area: 
a.  Change the radio button to be **Observe**. 
b.  Use the lookup to select the **Holiday UK [xx]** created earlier.
c.  Select the appropriate time zone (GMT 0 Dublin, Edinburgh, Lisbon, London) 
d.  Click **Save and Close**. 


## Exercise 2 - Service Level Agreements

### Task 1 Create a Service Level Agreement
In this task you will 
* Create a new Service Level Agreement. 
* Associate the Customer Service Schedule created in the previous step. 
* Add SLA Details to show Failure and Warning times
Detailed Steps 
1.  Select  > Service Management > Service Terms > Service Level Agreements. 
2.  Click New. 
3.  Type Standard UK SLA [xx] in the Name
4.  Select Case for the Primary Entity
5.  Click Save

6.  Click New SLA Item
a.  Name : Standard First Response
b.  KPI: First Response By[xx]
c.  Allow pause and Resume: Yes
d.  Business Hours: UK Service Calendar [xx]
e.  In the Applicable When area, click Add row
f.  Enter Priority(Case) Does not equal Low. 




1.  Click on the **Sitemap** button and select **Service**.

2.  Click **Cases**.

3.  Click **+ New Case**.

4.  Enter *[your prefix ex. mollyc]+ Audio System Setup Issues* for **Case Title**, select *your user* for **Customer**, select **Email** for **Origin**, select
    *[your prefix ex. mollyc]+ Entitlement 1* for **Entitlement** and click **Save**.

5.  Click + New.

6.  Enter *[your prefix ex. mollyc]+ Defective Speaker* for **Case Title**, select *your user* for **Customer**, select **Facebook** for **Origin**, select **[your prefix ex. mollyc]+ Entitlement 1** for **Entitlement** and click **Save**.

7.  Scroll to the **Entitlement** field and click on the **[your prefix ex. mollyc]+ Entitlement 1**

8.  Go to the **Entitlement Terms** section and make sure you have **98
    Remaining Terms**.

9.  Go to the **Entitlement Channel** sub-grid and make sure you have **49
    Remaining Terms** for **Email**, **9 Remaining Terms** for **Facebook**,
    **10 Remaining Terms** for **Twitter**, and **30 Remaining Terms** for
    **Web**.

Exercise 2 – Entitlement Templates
----------------------------------

In this exercise, you will create an entitlement template that will have 20 free
terms and the customer will be able to select the channel they prefer during the
entitlement creation.

### Task 1 – Create Entitlement Templates

In this task, you will create an entitlement template with 20 terms.

1.  Click on the **Sitemap** button and select
    **Service Management**.

2.  Click **Entitlement Templates**.

3.  Click **+ New**.

4.  Enter *[your prefix ex. mollyc]+ 20 Free Terms* for **Entitlement Template Name**, select **Yes**
    for **Restrict on Entitlement Terms**, select **Number of Cases** for
    **Allocation Type**, select **Case Creation** for **Decrease Remaining On**,
    enter **20** for **Total Terms** and click **Save**. DO NOT navigate away
    from this page.

### Task 2 – Create Entitlement from Template

In this task, you will create 20 phone call only entitlement from the
entitlement template you created.

1.  Click **Entitlements**.

2.  Click on the **V** chevron button next to the **New** button and select
    **From Template**.

3.  Select *[your prefix ex. mollyc]+20 Free Terms* for **Entitlement Template** and click **Select**.

4.  Some of the fields will be auto-filled from the template.

5.  Enter *[your prefix ex. mollyc]+ Phone Call Only Terms* for **Name**, select *your user* for
    **Primary Customer**, select today’s date for **Start Date**, select a year
    from today for **End Date,** and click **Save**.

6.  Go to the **Entitlement Channel** sub-grid, click on the ellipsis and select **+New Entitlement Channel**.

7.  Select **Phone** for **Name**, enter **20** for **Total Terms** and click
    **Save & Close**.

8.  Click on the ellipsis and select **+New Entitlement Channel**.

9.  Select **Email** for **Name**, enter **0** for **Total Terms** and click
    **Save & Close**.

10. Click on the ellipsis and select **+New Entitlement Channel**.

11. Select **Web** for **Name**, enter **0** for **Total Terms** and click
    **Save & Close**.

12. Click on the ellipsis and select **+New Entitlement Channel**.

13. Select **Facebook** for **Name**, enter **0** for **Total Terms** and click
    **Save & Close**.

14. Click on the ellipsis and select **+New Entitlement Channel**.

15. Select **Twitter** for **Name**, enter **0** for **Total Terms** and click
    **Save & Close**.

16. Click **Activate**.

17. Confirm activation. DO NOT navigate away from this page.

### Task 3 – Test the Entitlement

In this task, you will test the entitlement you created from the entitlement
template.

1.  Click on the **Sitemap** button and select
    **Service**.

2.  Click **Cases**.

3.  Click **+ New Case**.

4.  Enter *[your prefix ex. mollyc]+ Missing Parts* for **Case Title** and select *your user* for
    **Customer**.

5.  Select **Phone** for **Origin**, select *[your prefix ex. mollyc]+ Phone Call Only Terms* for
    **Entitlement** and click **Save**.

6.  Click **+ New**.

7.  Enter *[your prefix ex. mollyc]+ wrong cables* for **Case Title** and select **Jim Glynn** for
    **Customer**.

8.  Select **Web** for **Origin**, select *[your prefix ex. mollyc]+Phone Call Only Terms* for
    **Entitlement** and click **Save**.

9.  Scroll down to the **Entitlement** field and click **Phone Call Only
    Terms**.

10. Click **Save**. You will get an error telling you that there are no
    available terms.

11. Click **OK**.

12. You should get the same error if you select Email, Facebook or Twitter for
    Origin.

13. Select **Web** for **Origin** and clear the **Entitlement** field.

14. Click **Save**.

15. Since you didn’t select the **Phone Call Only Terms** entitlement, the Case
    will now be created.

16. Click on the **Sitemap** button and select
    **Service Management**.

17. Click on the **Site Map** button and select **Entitlements**.

18. Click to open the *[your prefix ex. mollyc]+ Phone Call Only Terms*.

19. Make sure you have **19 Remaining Terms** and **19 Phone** channel
    **Remaining Terms**.

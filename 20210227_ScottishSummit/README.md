> I had the opportunity to present the following session during the [**Scottish Summit 2021**](https://scottishsummit.com/ss2021).

## Manage leave requests from Dynamics 365 HR in Teams

- Slides presented during the session: [**Manage leave requests from Dynamics 365 HR in Teams.pdf**]()
- Video recording of the session: *Not yet available* <!-- [**Link**]() -->
- Solution used in the demonstration: [**HumanResourcesAppEnhancements_1_1_0.zip**](https://github.com/rpothin/Presentations/blob/main/20210227_ScottishSummit/HumanResourcesAppEnhancements_1_1_0.zip)
- Power Bi Dataflow definition used to build the Power BI Report used in the demonstration: [**LeaveRequests.json**](https://github.com/rpothin/Presentations/blob/main/20210227_ScottishSummit/LeaveRequests.json)
- Power BI Report used in the demonstration: [**LeaveRequestsApprovalMonitoring.pbix**](https://github.com/rpothin/Presentations/blob/main/20210227_ScottishSummit/LeaveRequestsApprovalMonitoring.pbix)

### How to use the **HumanResourcesAppEnhancements_1_1_0.zip** solution

#### Prerequisites

- A Dynamics 365 Human Resources environment with the associated Dataverse
- [On-premises Data Gateway](https://docs.microsoft.com/en-us/data-integration/gateway/service-gateway-install) set up somewhere (you laptop, a VM...)
- Human Resources app for Teams available and installed in Teams for the considered users
- *(Optional) The following connections configured in your Dataverse environment*
  - *UI Flows*
  - *Microsoft Teams*
  - *Common Data Service (current environment)*

#### Configuration in Dynamics 365 Human Resources (for a demonstration for example)

> The configuration below is based on a Dynamics 365 Human Resources trial environment.

- Users - at least 2:
  - one associated to a worker with a *manager* position (with the **Manager** role)
  - one associated to a worker *member of the team* managed by the previous user (with the **Employee** role)
- Workers: update the email addresses of the workers associated to the users above
- Set the workflow on a leave type (for example, PTO) to **Manager approval** (should be 000224)
- Enable the [**Dataverse integration**](https://docs.microsoft.com/en-us/dynamics365/human-resources/hr-admin-integration-common-data-service)
- Set the **Enable notifications for Teams app** option to **Yes** in the **System parameters**

#### Update of the elements in the solution

- Import the solution to the Dataverse environment associated to your Dynamics 365 Human Resources environment
- In the **Leave Request (Approved) - Notifications in Teams** cloud flow,
  - update the **If auto approved "Leave Type"** action in the **Apply to each Leave Request Details** loop to take in account the id of all the leave types using the **Automatic approval** workflow in Dynamics 365 Human Resources application (*You can fin the IDs of the leave types using the following path: Data > Tables > Leave Type > Data > Switching the view to "All columns"*)
  - update the following fields in the **Run "Leave Request Details Sync to CDSLeave Request Details Sync to CDS Test"** action: **d365hrUrl**, **userLogin** and **userPassword**
  - update the **Post last minute absence in Teams channel** action under the **Team notification if today absence** condition to target the Team and the channel of your choice
- In the **Scheduled (Daily) - Absences of the day publication in Teams** cloud flow, update the **Post absences of the day in Teams channel** action under the **Post notification if at least one person out of the office today** condition to target the Team and the channel of your choice
- Run the **Manual - Update manager on all workers** cloud flow to update to rows in the **Workers** table filling the **Manager** column

### How to use the **LeaveRequestsApprovalMonitoring.pbix** Power BI Report

#### Prerequisites

- Having imported the **HumanResourcesAppEnhancements_1_1_0.zip** solution
- Having a Power BI worskpace ready with its ID (*you can get this information in the URL when you open the Power BI woskpace: https://app.powerbi.com/groups/_PowerBIWorkspaceID_/*)
- In the **LeaveRequests.json** file replace **https://org3fed297b.crm.dynamics.com/** by the URL of the Dataverse environment associated to your Dynamics 365 Human Resources environment (*Go to [Power Platform admin center
](https://admin.powerplatform.microsoft.com/environments) > Open the considered environment > Get the value of the "Environment URL" field*)

#### Configuration of the **LeaveRequests.json** Power BI Dataflow

1. Go to your Power BI workspace
2. Click on **+ New**
3. Select **Dataflow**
4. Click on **Import model**
5. Select the **LeaveRequests.json** file
6. Click on **Open**

> I am not sure it will be so easy, but I really hope it will 😊

#### Configuration of the **LeaveRequestsApprovalMonitoring.pbix** Power BI Report

1. Open the **LeaveRequestsApprovalMonitoring.pbix** file in Power BI Desktop
2. Click on **Transform Data**
3. For each query (*LeaveRequestDetails* and *WorkersManagers*) click on **Advanced Editor**
   1. Replace **b8bd293b-e0f7-4421-be41-5fdef8ebbdf5** in the line **#"b8bd293b-e0f7-4421-be41-5fdef8ebbdf5" = Source{[workspaceId="b8bd293b-e0f7-4421-be41-5fdef8ebbdf5"]}[Data],** with your own Power BI Workspace ID
   2. Replace **2aa235e1-7692-4a1b-abdb-6c80c3c0ae25** in the lines below with the ID of Power BI Dataflow you created in the previous stage (*you can get this information in the URL when you open the Power BI woskpace: https://app.powerbi.com/groups/_PowerBIWorkspaceID_/dataflows/_PowerBIDataflowID_*)
      - **#"2aa235e1-7692-4a1b-abdb-6c80c3c0ae25" = #"b8bd293b-e0f7-4421-be41-5fdef8ebbdf5"{[dataflowId="2aa235e1-7692-4a1b-abdb-6c80c3c0ae25"]}[Data],**
      - **... = #"2aa235e1-7692-4a1b-abdb-6c80c3c0ae25"{[entity="..."]}[Data]**
   3. Click on **Done**
4. Click on **Close & Apply**
5. Remove the canvas app
6. Add the canvas app you imported with the solution to the Power BI Report selecting the following fields: LeaveDate, LeaveRequestComment, LeaveRequestNumber, LeaveRequestSubmissionDate, LeaveType, LeaveTypeDescription, WorkerFullName, WorkerNumber, ManagerFullName, ManagerPrimaryEmailAddress, NbOfDaysBeforeLeave and NbOfHoursRequested
7. Save the Power BI Report
8. Publish the Power BI Report to the considered Power BI Workspace

> Now you can:
> - configure the refresh schedule of the Power BI Dataflow and the Power BI Dataset
> - add the Power BI report to a Teams channel as a tab
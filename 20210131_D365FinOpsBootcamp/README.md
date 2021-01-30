> I had the opportunity to present the following session during the [**Dynamics 365 FinOps Bootcamp**](https://events.powercommunity.com/d365-finance-operations-summit-2021/).

## Deep dive in the Human Resources app for Teams

- Slides presented during the session: *Not yet available* <!-- [**Deep dive in the Human Resources app for Teams.pdf**](https://github.com/rpothin/Presentations/blob/main/20210131_D365FinOpsBootcamp/) -->
- Video recording of the session: *Not yet available* <!-- [**Link**]() -->
- Solution used in the demonstration: [**HumanResourcesAppEnhancements_1_0_0.zip**](https://github.com/rpothin/Presentations/blob/main/20210131_D365FinOpsBootcamp/HumanResourcesAppEnhancements_1_0_0.zip)

### How to use the **HumanResourcesAppEnhancements_1_0_0.zip** solution

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

#### Update of the elements in the solution

- Import the solution to the Dataverse environment associated to your Dynamics 365 Human Resources environment
- In the **Leave Request (Approved) - Notifications in Teams** cloud flow,
  - update the **If auto approved "Leave Type"** action in the **Apply to each Leave Request Details** loop to take in account the id of all the leave types using the **Automatic approval** workflow in Dynamics 365 Human Resources application (*You can fin the IDs of the leave types using the following path: Data > Tables > Leave Type > Data > Switching the view to "All columns"*)
  - update the following fields in the **Run "Leave Request Details Sync to CDSLeave Request Details Sync to CDS Test"** action: **d365hrUrl**, **userLogin** and **userPassword**
  - update the **Post last minute absence in Teams channel** action under the **Team notification if today absence** condition to target the Team and the channel of your choice
- In the **Scheduled (Daily) - Absences of the day publication in Teams** cloud flow, update the **Post absences of the day in Teams channel** action under the **Post notification if at least one person out of the office today** condition to target the Team and the channel of your choice
- Run the **Manual - Update manager on all workers** cloud flow to update to rows in the **Workers** table filling the **Manager** column

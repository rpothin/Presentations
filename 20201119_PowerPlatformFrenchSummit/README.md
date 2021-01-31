> I had the chance to present 3 sessions and to participate to 1 keynote during the [**Power Platform French Summit 2020**](https://www.powerplatformfrenchsummit.com/).
> 
> **Note:** *All my sessions during this event were in French.*

## La gestion des congés avec Dynamics 365 Human Resources et Teams (Leave Requests management with Dynamics 365 Human Resources and Teams)

- Slides presented during the session: [**La gestion des congés avec Dynamics 365 Human Resources et Teams.pdf**](https://github.com/rpothin/Presentations/blob/main/20201119_PowerPlatformFrenchSummit/La%20gestion%20des%20cong%C3%A9s%20avec%20Dynamics%20365%20Human%20Resources%20et%20Teams.pdf)
- Video recording of the session: [**Link**](https://youtu.be/O-BKYRqAKu4)
- Solution used in the demonstration: [**HumanResourcesAppEnhancements_1_0_0.zip**](https://github.com/rpothin/Presentations/blob/main/20201119_PowerPlatformFrenchSummit/HumanResourcesAppEnhancements_1_0_0.zip)


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
- Set the **Enable notifications for Teams app** option to **Yes** in the **System parameters**

#### Update of the elements in the solution

- Import the solution to the Dataverse environment associated to your Dynamics 365 Human Resources environment
- In the **Leave Request (Approved) - Notifications in Teams** cloud flow,
  - update the **If auto approved "Leave Type"** action in the **Apply to each Leave Request Details** loop to take in account the id of all the leave types using the **Automatic approval** workflow in Dynamics 365 Human Resources application (*You can fin the IDs of the leave types using the following path: Data > Tables > Leave Type > Data > Switching the view to "All columns"*)
  - update the following fields in the **Run "Leave Request Details Sync to CDSLeave Request Details Sync to CDS Test"** action: **d365hrUrl**, **userLogin** and **userPassword**
  - update the **Post last minute absence in Teams channel** action under the **Team notification if today absence** condition to target the Team and the channel of your choice
- In the **Scheduled (Daily) - Absences of the day publication in Teams** cloud flow, update the **Post absences of the day in Teams channel** action under the **Post notification if at least one person out of the office today** condition to target the Team and the channel of your choice
- Run the **Manual - Update manager on all workers** cloud flow to update to rows in the **Workers** table filling the **Manager** column

## Améliorer votre relation client grâce à Dynamics 365 Customer Voice et Dynamics 365 Marketing (Improve your customer relationship with Dynamics 365 Customer Voice and Dynamics 365 Marketing)

- Slides presented during the session: [**D365 Customer Voice et D365 Marketing.pdf**](https://github.com/rpothin/Presentations/blob/main/20201119_PowerPlatformFrenchSummit/D365%20Customer%20Voice%20et%20D365%20Marketing.pdf)
- Video recording of the session: [**Link**](https://youtu.be/F0mhxaHCJBk)

## Gérer le cycle de vie de vos solutions dans GitHub (Manage your solution ALM in GitHub)

- Slides presented during the session: [**Gérer le cycle de vie de vos solutions dans GitHub.pdf**](https://github.com/rpothin/Presentations/blob/main/20201119_PowerPlatformFrenchSummit/G%C3%A9rer%20le%20cycle%20de%20vie%20de%20vos%20solutions%20dans%20GitHub.pdf)
- Video recording of the session: [**Link**](https://youtu.be/TIzFwuiv0zY)
- Template GitHub repository presented during the session: [**rpothin/PowerPlatform-ALM-With-GitHub-Template**](https://github.com/rpothin/PowerPlatform-ALM-With-GitHub-Template)

**Important Note:** *This template GitHub repository is still in construction.*

## (Bonus) Technical Keynote - Opening of 2nd day of the event

- Video recording of the keynote: [**Link**](https://youtu.be/8pTRy9M5kOQ)
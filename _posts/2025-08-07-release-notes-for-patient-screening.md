---
layout: post
title: Release Notes Sample
date: '2025-08-07 14:00:39 -0700'
categories: []
tags: []     # TAG names should always be lowercase
---
## Enhancements
### Updated product information
The pre-screening, patient querying, and cohort building application offered by Inteliquet™ has been renamed from OncWeb™ to Patient Screening. Inteliquet Patient Screening has been updated with the following:
- New logo
- New login, security, and password reset screens
- New banner color and size
- Profile icon in the banner has been replaced with the signed in user's username.

### Display qualifying patient data in results for Inteliquery™ and Advanced Inteliquery
A Matched Criteria view has been added for the patient list results from Inteliquery and Advanced Inteliquery. Matched Criteria displays the data that matched each patient to each of the query's criteria.  
The Matched Criteria view is structured as a hierarchy to mimic the query's structure. Criteria are displayed as top-level columns. Components are nested under their criteria as second-level columns. Component-type-specific columns are nested under their components as third-level columns.

### Alerts overhaul
Alerts and notifications for Patient Screening have been overhauled including new Global Alerts, replacements for patient specific alerts, and team management functionality for site administrators.

#### Changes to Global Alerts
- Patient Recruitment Alerts have been removed.
- The following global alerts were added:
  - Query Result Changes: The user can select queries to track and Patient Screening will send them a notification when patients are added or removed from the results of those queries overnight.
  - Recruitment Status Changes by Provider: The user can select providers for this alert to track and Patient Screening will send them a notification when the recruitment status changes for a patient of one of those providers for one of the selected trials. 
    - The user can add multiple providers to this alert. 
    - The user can select multiple trials for each provider.
  - Next Patient Visits by Provider: The user can select providers for this alert to track and Patient Screening will send them a notification when a patient of one of those providers with any recruitment status for one of the selected trials has an upcoming visit matching one of the selected next visit types. 
    - The user can add multiple providers to this alert. 
    - The user can add multiple notifications for each provider to be notified in advance of any matching visits.
    - Example: Your alert is configured to send a notification 5 days before and 0 days before any patient has an office visit with Dr. Rivers and that patient has a recruitment status for trial NCT0123456. Jane Doe (patient) has an upcoming office visit (matching visit type) with their provider, Dr. Rivers in 7 days. Jane Doe has a recruitment status of Watch for trial NCT0123456. You will receive a notification in 2 days and in 7 days regarding Jane Doe's office visit.

#### Changes to patient specific alerts
-  Alerts for specific patients has been removed from the Patient Status & Notes dialog.
-  Alerts for specific patients have a new dialog: Alert Settings: By Patient. This new dialog is available through Alert Settings, Patient Chart, Patient Criteria, and Patient Trials.
-  The following alerts have been added:
   - Event Date: Patient Screening will send the user a notification on the configured date and any advance notification dates for the alert.
   - Next Visit: The user can select Next Visit types for Patient Screening to track and send them a notification when the selected patient has an upcoming visit of those types.
   - Trial Recruitment Status Change: The user can select clinical trials for Patient Screening to track and send them a notification when the patient's Recruitment Status changes to one of the selected statuses for any of the selected trials.
   - Clinical Alert: The user can select a query for this alert to track and Patient Screening will send them a notification if the selected patient matches the query overnight.

#### Team management for site administrators
Site administrators have permission to view and edit most alerts for site users, but not other administrators, through the Team Alerts tab in both the Global and By Patient pages of Alert Settings. Administrators can view and edit any site user's alerts for patients within a patient specific context, such as Patient Chart.
- Site administrators see a tabbed view within Alert Settings for both Global and By Patient alerts. Those tabs are:
  - My Alerts: alerts configured by the signed in administrator are displayed.
  - Team Alerts: alerts configured by all site users are displayed. Administrators cannot see alerts configured by other admins.
- Site administrators have the following additional functionality:
  - Add, edit, and remove Global or By Patient alerts for all site users.
    - Some alert types are not editable by administrators like Query Result Changes for Global and Clinical Alert for By Patient alerts.
  - Opt-in to receive a notification if a specific user changes their global alerts or their alerts for a specific patient.
  - Opt-in to receive the same notification as a user for any of their global alerts or any of their alerts for a specific patient.

### Chart review project flow
 Patient Screening has added a flow to support chart review projects at our sites. Chart review projects through IQVIA Life Sciences can take advantage of reduced complexity when communicating necessary information between sites, Inteliquet, IQVIA Life Sciences, and the project's sponsor. Sites can enter the data extraction variables for each patient into an EDC project shared with IQVIA Life Sciences then utilize the new integrated workflow between Patient Screening and Feasibility Tool to send Life Sciences the mapping IQVIA Life Sciences needs to complete the chart review project.  
 The process for the new chart review project flow is below:
1. The site's Primary Chart Review Manager collaborates with their Inteliquet Engagement Specialist and IQVIA Life Sciences before the chart review project kicks off to set up a shared EDC project and ensure the correct team members have access.
2. IQVIA Life Sciences can submit their Feasibility Tool query criteria to any site and Patient Screening creates a Chart Review patient list for that site's Primary Chart Review Manager.
   - The site's Primary Chart Review Manager may also create Chart Review patient lists manually by entering a list of patient identifiers as if they were creating any other patient list.
3. The site's Primary Chart Review Manager collaborates with their Inteliquet Engagement Specialist to manage assignments for the chart review project.
4. The assigned team members working on the chart review create patient records in the shared EDC project and paste the generated EDC IDs into Patient Screening through the External ID link.
5. When all patients are completed, the Primary Chart Review Manager submits the Chart Review patient list to IQVIA Life Sciences through Patient Screening. 
   - Submitting the Chart Review patient list sends IQVIA Life Sciences a mapping for each patient between their Inteliquet Screening ID and the External ID. Until IQVIA Life Sciences receives this mapping, they cannot complete the chart review, but they have access to the patient records in the shared EDC project.

#### Progression tracking and task management in Chart Review patient lists
Each patient within a Chart Review patient list can be marked as Incomplete, In Progress, or Complete. The Patient Lists module displays a progress bar and the number of patients with the Complete status out of the total patient count.

#### Primary Chart Review Manager
 Each facility can have a single user or administrator designated as the Primary Chart Review Manager. This individual has special permissions related to chart review projects and their account is required for submission of a completed chart review. This designation is maintained in User Administration and can be changed to another user or administrator by a site administrator. Coordinate with your Inteliquet Engagement Specialist so they are aware of the designated Primary Chart Review Manager at your facility.  
 Only a facility's Primary Chart Review Manager can perform the following actions:
 - Create and share a Chart Review patient list manually.
 - Receive and initially share an automatically created Chart Review patient list. Any user can share a Chart Review patient list once they have access. The Primary Chart Review Manager is required to initially coordinate sharing Chart Review patient lists with the correct team members.
 - Submit a Chart Review patient list.

### Expandable text box for component description in Clinical Trial Editor
The description text box for components in Clinical Trial Editor has an Expand button.

### Search implemented for Disease Site field in Clinical Trial Editor > Info
The Disease Site field under Clinical Trial Editor > Info can be used to search for and select a disease site instead of requiring manual entry.

### Localization workflow
Patient Screening supports a workflow for approving and implementing changes to the User Interface for language localization. Facilities that want to request localization changes for the next version of Patient Screening should follow the below process:
1.  In the KodiakApi directory, locate the `(locale).json` file. (locale) is a placeholder for your locale code. For example, USA based facilities would reference the `KodiakApi/en-us.json` file.
2.  Edit the text for any UI strings your facility wants to change.
3.  Submit the edited `(locale).json` file to Inteliquet for review.
More information for this process is provided in the Operating Procedure Manual - Patient Screening.

## Bug fixes
-  Fixed queries with a Visits component in Inteliquery failing to return results due to timing out.
-  Fixed trials with stage IV data returning fewer potential patients than expected.
-  Fixed some patients not being marked with the Is Metastatic flag despite having a stage IV cancer diagnosis. 
-  Fixed trials failing to run when they contained a Diagnostics - Lab component with the Results Type of Abnormal Results selected and a lower or upper limit configured.
-  Fixed an error referencing a missing key that would sometimes display when attempting to open a trial in Clinical Trial Editor.
-  Fixed an error when attempting to sort the selection check box column in the category editing screen of Category Manager.
-  Fixed the Locations button in Site Manager failing to direct the user to the locations screen.
-  Fixed an error in the Home Page when no clinical trials were defined in Patient Screening.
-  Fixed an error message when a trial's Run or Get Counts process timed out in Clinical Trial Editor.
-  Fixed an error in the Home Page when the Patients by Provider widget attempted to load while only one site was set as Is Clinical Trial Site.
-  Fixed an issue with Japanese language characters in downloaded reports being corrupted. 
-  Fixed selected values in components for queries accessed through the My Patient Queries widget displaying as empty rows.
-  Fixed the Onset date for diagnoses in Patient Chart changing to adjust for time zones.
-  Fixed diagnosis codes incorrectly matching when calculating cancer episode diagnoses associations.

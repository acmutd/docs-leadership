---
sidebar_position: 1
---

# Admin

The leadership site supports an admin page to manage and update data. Currently, the admin page only supports making changes to the officer portion of the leadership site. The membership, programs & events pages need to be updated through manual scripts or by directly adding documents to Cloud Firestore. To access the admin dashboard follow these steps:

 - Sign in with your ACM account
 - If you do not already have the `historian` permission, ask the [Director of Development](mailto:development@acmutd.co) or Exec for access.
 - Click on the **Admin** button in the navigation bar to open the admin dashboard.

### Historian Configuration

The admin dashboard is only accessible to a subset of ACM Officers that have the `historian` permission. The list of email addresses that have the historian permission is stored in the `total/allinone` document on Cloud Firestore. The frontend makes a simple check to ensure that the email of the signed in user is present in the historian array. 

### Officer Management

The admin dashboard currently supports the following features:

 - Adding new officers
 - Updating existing officers
 - Creating new roles
 - Ending an officer's role in the organization
 - Changing roles for an existing officer
 - Adding or removing historian access from officers

All actions that can be performed via the Admin Dashboard are safe and support error handling. All fields support autocomplete to ensure that only valid data can be entered as input.

:::important
When adding new officers the current date & time will be used automatically as their start date. Their end date will be set as `June 19th 2021`. Similarly, when changing roles, the end date for their current role & the start date for their new role will be automatically set to the current date. The admin dashboard **does not** support changing the start/end dates for an officer or any of their roles. To make these changes update directly in Cloud Firestore. 
:::

### Other Data Management

See [GitHub](https://github.com/acmutd/leadership/tree/main/manual) for information on how to use the manual scripts to update the membership, programs & events pages. These scripts are hacky and need to be used carefully to ensure that the database does not get accidentally corrupted. For safeguards, all the code snippets that write to Cloud Firestore are commented out in the scripts. Uncomment them at your own discretion. 

Note: All the scripts are written in `python`. If you prefer `js/ts` or a different language feel free to write new scripts and/or add api endpoints to the leadership site to support making changes via the Admin Dashboard.
The Somtoday Source Connector significantly simplifies the management of user accounts and authorisations within your educational organisation. The connector links Somtoday to your target systems via Tools4ever’s identity & access management (IAM) solution HelloID. You can also use this connector to write information from your target systems back to Somtoday. This integration automates various Inflow, Throughflow, and Outflow (IDU) processes within your organisation, ensuring you do not have to worry about them. This article provides more information about this connector, the specific capabilities it offers, and its benefits.

## What is Somtoday?

Somtoday is an electronic learning environment (ELO), a portal that provides students and caretakers with insights into homework, grades, messages, timetables and study plans. Students can also upload and share assignments with teachers. In addition, you can also write data from target systems back to Somtoday so that data is always up-to-date. The Somtoday connector supports the management of student and employee accounts in the ELE as part of the IDU processes. The Somtoday connector enables interfacing with common target systems such as:

## Why is a Somtoday integration useful?

The Somtoday connector is often used as a source connector to complement an HR system. It is specifically aimed at participants and making additional data about staff available. Additionally, the Somtoday connector supports the management of accounts for students and staff in the ELO to support IDU processes. The Somtoday connector allows integration with common target systems, such as:

*	Active Directory
*	Entra ID
*	Google Workspace

Further details about the integration with these target systems can be found later in this article.

## HelloID for Somtoday helps you with…

**Uniform account management:** The enrolment of a new student or staff member requires the creation of the correct accounts. With the integration of Somtoday and your target systems using HelloID, you do not need to worry about this. Automating the process significantly ensures consistent and uniform account management, preventing errors and ensuring users have the correct accounts at the right time.

**Alignment with the IDU process in the organisation:** Your educational organisation is constantly evolving, both when it comes to students and staff. There are new people joining, students progressing to the next school year, staff being assigned new roles, and people leaving. All these changes require updates to your systems, quickly increasing the number of actions you need to perform. The integration of Somtoday with your target systems takes much of this work off your hands and ensures that account management aligns perfectly with the IDU process within your organisation.

**Improved efficiency:** Automating account management offers significant benefits, increasing your efficiency and allowing you to serve users more quickly. This ensures that students and staff have access to the accounts and authorisations they need sooner. Because the connector can also write back information, you ensure that information is always up-to-date.

**Improved compliance:** The integration also improves your compliance. Automation ensures the process is consistent and error-free. Role-Based Access Control (RBAC) is also beneficial, as it allows you to assign changes based on RBAC roles rather than individually. This enables you to define the rights for specific user groups all at once. All changes made by HelloID are recorded in a detailed audit log, allowing you to demonstrate compliance.


## How HelloID integrates with Somtoday

When you integrate Somtoday with your target systems, Somtoday typically complements your HR system. This allows for the fully automated management of the user account lifecycle in your target systems via HelloID, preventing errors, saving time and serving users more quickly.


| **Change in Somtoday** |	**Procedure in target systems** |
| ------------------ | ---------------------------- | 
| **New student or staff member** |	Based on information from Somtoday, HelloID creates the necessary accounts in your target systems for new students and staff and assigns the required authorisations. You do not need to worry about this process; HelloID automatically detects the change in Somtoday and makes the desired updates based on this information.|
| **Different school year, role change, placement change, subject choices, and class groups** |	Educational organisations are continuously evolving. Existing students progress to the next school year or repeat the year, or they may choose different subjects, leading to different class groups. They may also be placed in another class, may change subject choices. Simultaneously, your staff is dynamic, with new roles being assigned, etc. These changes may require different accounts and authorisations in your linked target systems. HelloID automates this process significantly, with its authorisation model always taking precedence. Authorisations linked to the old role are automatically revoked by HelloID.
| **Name changes** |	For various reasons, a student or staff member's name may change. HelloID detects this change and automatically updates the user's name accordingly.|
| **Student or staff member leaves** |	User accounts in target systems are deactivated, and HelloID informs the relevant staff within the organisation. After a certain period, HelloID automatically deletes the accounts and revokes the granted permissions.|

HelloID uses the HRMService and the ConnectAPI for data exchange. HelloID uses standard REST calls for the ConnectAPI and SOAP calls for the HRMService. The IAM solution retrieves data for a specific reference year per institution and location via the ConnectAPI. Based on this, HelloID processes placements, subject choices and class groups, which can then be used to assign authorisations using business rules. The HRMService enables the management of data on the personal card in the HR section of Somtoday.

## Connecting Somtoday to target systems via HelloID

You can link Somtoday to various target systems via HelloID. This is convenient as HelloID can make updates to your target systems based on information from Somtoday. These integrations not only reduce your workload but also enhance the management of both users and authorisations. Some examples of common integrations include:

* **Somtoday – AFAS integration:** The integration between Somtoday and AFAS allows you to automate user account and authorisation management significantly. When a new account is created or an existing account is changed in Somtoday, HelloID detects this adjustment and processes it automatically in AFAS. This integration streamlines account management and reduces your workload.

* **Somtoday – Active Directory integration:** The integration between Somtoday and Active Directory enables automated synchronisation between these systems, ensuring accounts and authorisations are always up-to-date. It also prevents human errors by eliminating the need for manual data entry.

* **Somtoday – Entra ID integration:** The integration with the cloud-based Entra ID allows for fully automated account provisioning and authorisation assignment. If the provisioning process takes place in the on-premises counterpart Active Directory, you can assign cloud-only permissions.

HelloID offers 200 connectors, enabling you to link the IAM solution to a wide range of source and target systems. These broad integration possibilities allow you to connect Somtoday to all popular target systems.

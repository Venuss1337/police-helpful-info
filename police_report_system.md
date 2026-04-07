# Police Report System Specification for Florida Highway Patrol (FHP)

## Overview
This document outlines the police report system used by the Florida Highway Patrol (FHP). It captures the essential functionalities, workflow processes, and the necessary data fields required for comprehensive reporting.

## Report Status Workflow
The report status workflow is designed to ensure that all police reports are processed systematically, allowing for tracking and accountability. The workflow consists of the following statuses:

- **Draft**: Report is being created and can be modified.
- **Submitted**: Report has been submitted for review.
- **In Review**: Report is under review by a supervisor.
- **Approved**: Report has been approved.
- **Rejected**: Report has been rejected and needs rework.
- **Completed**: Report is finalized and archived.

## Allowed Transitions
- Draft → Submitted
- Submitted → In Review
- In Review → Approved
- In Review → Rejected
- Approved → Completed

## Role Permissions
- **Officers**: Create and submit reports.
- **Supervisors**: Review, approve, or reject reports.
- **Admins**: Manage user roles and permissions.

## Necessary Police Report Fields
- **Incident Number**: Unique identifier for the report.
- **Date/Time of Incident**: When the incident occurred.
- **Location of Incident**: Geographic location.
- **Reporting Officer**: Name and badge number of the reporting officer.
- **Witnesses**: Names and contact information for witnesses.
- **Suspects**: Names and details of suspects involved.
- **Victims**: Names and details of victims.
- **Description of Incident**: Detailed account of the incident.
- **Evidence**: List of evidence collected.

## Real-World Police Report Types Relevant to FHP
- **Arrest Reports**: Documentation related to arrests made.
- **Traffic Stop Reports**: Reports on traffic violations and stops.
- **Crash/Accident Reports**: Detailed reports on vehicular incidents.
- **DUI Reports**: Documentation for driving under the influence incidents.
- **Pursuit Reports**: Reports following police vehicle pursuits.
- **Citation/Warning Reports**: Issued citations or warnings.
- **Use of Force Reports**: Documentation of force used during an arrest.
- **Incident Reports**: General incidents that do not fall into other categories.
- **Evidence/Property Reports**: Reports documenting evidence collected.
- **Complaint Reports**: Reports on citizen complaints.
- **Suspicious Activity Reports**: Reports on suspicious behavior.
- **Vehicle Tow/Impound Reports**: Documentation of vehicle tows or impounds.

## Supervisor Review Logic
Supervisors must review all submitted reports and either approve them or return them for modifications. This ensures quality control and accountability.

## Database Fields Example
- `incident_number`: String
- `date_time`: DateTime
- `location`: String
- `reporting_officer`: String
- `witnesses`: Array
- `suspects`: Array
- `victims`: Array
- `description`: Text
- `evidence`: Array

## Audit/Logging Rules
All actions taken on reports (creation, submission, modification, approval) must be logged with timestamps and user information for audit purposes.

## UI Colors
- **Approved**: Green
- **Rejected**: Red
- **In Review**: Yellow
- **Draft**: Blue

## Optional Enhancements
- **Integration with CAD systems**: Allow automatic population of certain fields.
- **Mobile Access**: Ensure the system is accessible via mobile devices for reporting in the field.
- **Automated Status Notifications**: Email alerts on status changes for involved parties.
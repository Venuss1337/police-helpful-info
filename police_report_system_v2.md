# Florida Highway Patrol Police Report System Specification

## 1. Status System  
The report system utilizes a comprehensive status system consisting of the following statuses:  
- **Submitted**  
- **In Review**  
- **Needs Revision**  
- **Approved**  
- **Closed**  
- **Archived**  

### Allowed Transitions:  
- **Submitted** ➔ **In Review**  
- **In Review** ➔ **Needs Revision**  
- **Needs Revision** ➔ **In Review**  
- **In Review** ➔ **Approved**  
- **Approved** ➔ **Closed**  
- **Closed** ➔ **Archived**  

## 2. Role Permissions  
Roles within the system include:  
- **Officer**: Create arrest and traffic reports.  
- **Reviewer**: Review reports and provide feedback.  
- **Supervisor**: Approve reports and manage workflow.  
- **Administrator**: Full access to the system including user management.

## 3. Logic Rules  
- Only officers can submit reports.  
- Reviewers must provide feedback within 48 hours of report submission.  
- Supervisors can only approve reports that are in the "In Review" status.

## 4. Optional UI Colors  
- **Submitted**: Light Blue  
- **In Review**: Yellow  
- **Needs Revision**: Orange  
- **Approved**: Green  
- **Closed**: Grey  
- **Archived**: Dark Blue

## 5. Optional Enhancements  
- Integration with mobile devices for on-the-go reporting.  
- Real-time notifications for report status updates.

## 6. Database Fields  
The database will include the following fields:  
- **officer_id**: Identifies the reporting officer.  
- **reviewing_supervisor**: Identifies the supervisor reviewing the report.  

## 7. Comprehensive Report Sections  
The reports will contain the following sections:  
- **Arrest Report**  
- **Crash Report**  
- **Traffic Stop Report**  
- **Citation/Violation Report**  
- **DUI Report**  
- **Pursuit Report**  
- **Use of Force Report**  
- **Incident Report**  
- **Evidence/Property Report**  
- **Complaint Report**  
- **Suspicious Activity Report**  
- **Tow/Impound Report**

## 8. Real-World FHP-Focused Report Types  
Types of reports tailored specifically for FHP operations based on real-world scenarios.

## 9. Audit/Logging Rules  
The system will maintain audit logs of all actions taken on reports, including changes in status, updates by officers and reviewers, and approvals by supervisors.  

## 10. Workflow  
The workflow covers the complete lifecycle of report handling including:
- Submission  
- Review  
- Feedback  
- Approval

## 11. Permissions  
Detailing of permissions for each role regarding access, creation, and modification of reports.

## 12. Database Schema Outline  
Outline of the database schema to support the report system, ensuring proper data integrity and relationships between reports, users, and statuses.

---

This document provides an all-encompassing guideline for the Florida Highway Patrol Police Report System, aiming to streamline reporting, review, and approval processes while ensuring data integrity and proper auditing mechanisms.
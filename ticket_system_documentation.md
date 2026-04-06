# Police Roleplay (RP) GTA Ticket System Documentation

## Statuses
- **Open:** The ticket is newly created and is awaiting action.
- **Assigned:** The ticket has been assigned to a staff member for handling.
- **Resolved:** The ticket has been addressed and marked as resolved.
- **Archived:** The ticket is no longer active and has been archived for record-keeping.

## Labels/Additional Info
- **await_user:** Further information is required from the user to proceed.
- **await_staff:** The ticket is awaiting action from a staff member.
- **escalated:** The ticket has been escalated to a higher authority or rank.

## Ticket Types
- **General Support:** Standard support requests from users.
- **Internal Support:** Requests for assistance that involve internal processes or staff.
- **Command Support:** Tickets requiring assistance from command-level staff.

## Required Rank Values
- **Patrol-Grade:** Basic staff level able to handle general support.
- **Supervisor:** Higher-level staff responsible for overseeing Patrol-Grade staff.
- **Command:** Staff who can handle internal and command support tickets.
- **High-Command:** Top level of command that oversees the entire ticketing process.

## Actions
- **Take ticket from open:** Staff can take an open ticket to assign it to themselves.
- **Reply multiple times to user:** Staff may communicate with the user multiple times for clarification.
- **Escalate ticket to higher required rank:** If necessary, staff can escalate tickets to a higher rank for further assistance.
- **Resolve Ticket:** Once the issue is handled, the staff can mark the ticket as resolved.

## Full Setup/Specification
1. **Ticket Creation:** Users create a ticket specifying the type and description.
2. **Assignment:** Staff members review open tickets and assign them as necessary.
3. **Interaction:** Staff interact with users by replying to their tickets and collecting information.
4. **Escalation Process:** If a ticket requires higher authority, it can be escalated based on the ticket type and current staff rank.
5. **Resolution:** Once issues are resolved, tickets are marked as resolved and can later be archived.

## Recommended Workflow
1. User creates a ticket.
2. Ticket status is set to 'Open'.
3. Staff member takes the ticket and changes the status to 'Assigned'.
4. Staff interacts with the user, changing labels as needed.
5. If needed, escalate the ticket.
6. Once resolved, change status to 'Resolved' and archive if necessary.

## Permissions Guidance
- Patrol-Grade can only manage General Support tickets.
- Supervisors can manage all ticket types and escalate as necessary.
- Command can manage all tickets and have full access to user interactions.
- High-Command oversees the entire operation, ensuring all tickets are handled effectively.

## Data Model Outline
- **Ticket:**  
  - ID  
  - User ID  
  - Staff ID  
  - Status  
  - Type  
  - Created At  
  - Updated At  
  - Labels  
  - Description  

This model forms the basis for any further development or integration with AI tools by providing a structured approach to ticket management.
# Police RP Report Status System

## Status Definitions

1. **Submitted**  
   - Report has been completed by the officer  
   - Waiting for a supervisor to claim it  
   - Visible in the review queue  

2. **In Review**  
   - A supervisor has claimed the report  
   - Locked to that supervisor  
   - No other supervisor can modify it  

3. **Needs Revision**  
   - Supervisor has requested changes  
   - Officer regains edit access  
   - Must be resubmitted after fixes  

4. **Approved**  
   - Report has been accepted  
   - No further edits allowed  
   - Considered finalized  

5. **Closed**  
   - Report process is complete  
   - Can represent approved or rejected reports  
   - No further actions allowed  

6. **Archived**  
   - Long-term storage state  
   - Used for old reports  
   - Read-only access only  

## Status Flow

Submitted → In Review → Approved → Closed → Archived  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ↘ Needs Revision → Submitted  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ↘ Rejected → Closed → Archived

## Allowed Transitions

| From        | To                  |
|-------------|---------------------|
| Submitted   | In Review           |
| In Review   | Needs Revision       |
| Needs Revision | Submitted         |
|             | In Review           |
| Approved    | Closed (Rejected)   |
| Approved    | Closed              |
| Closed      | Archived            |

## Role Permissions

- **Officer**  
   - Create report  
   - Submit report  
   - Edit report (only if status = Submitted or Needs Revision)  

- **Supervisor**  
   - Claim report (Submitted → In Review)  
   - Approve report  
   - Reject report (move to Closed)  
   - Request revision

## Database Fields Example

```json
{
  "id": 1024,
  "title": "Traffic Stop - Downtown",
  "officer_id": 55,
  "status": "submitted",
  "claimed_by": null,
  "review_notes": null,
  "revision_count": 0,
  "created_at": "2026-04-06T14:30:00Z",
  "updated_at": "2026-04-06T14:30:00Z"
}
```

## Logic Rules

- Only one supervisor can claim a report at a time
- Reports in In Review must have claimed_by set
- Reports in Approved, Closed, Archived are locked
- Revision increments revision_count
- All transitions should be logged for auditing

## Optional UI Colors

- Submitted → Yellow
- In Review → Blue
- Needs Revision → Orange
- Approved → Green
- Closed → Gray
- Archived → Dark Gray

## Optional Enhancements

- Add priority levels (Low / Medium / High)
- Add timestamps per stage (claimed_at, approved_at, etc.)
- Add audit log table for tracking changes
- Add notifications for status changes

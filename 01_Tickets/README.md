# 01 — Tickets (3)

Examples of common support scenarios handled during Tier 1 / Tier 2 application support.

---

## Ticket 1 — Access Request

ID: REQ-1041  
Type: Request  
Priority: Medium  
User: Maya Patel (Finance)

### Issue

User requested approver access for month-end expense approvals.

### Investigation

- Verified manager approval in the ticket comments.
- Confirmed the user account was active.
- Checked existing permissions using SQL lookup.

### Action Taken

Granted **Approver role** following least-privilege access guidelines.

### User Communication

“Approver role has been applied. Please log out and back in, then test submitting an approval.”

### Resolution

User confirmed the approval workflow worked successfully.

Root cause: missing role assignment.

---

## Ticket 2 — Record-Specific Error

ID: INC-2091  
Impact: Low (single user / single report)  
Environment: Production

### Error

“Submit failed due to attachment processing error.”

Report ID: ER-1033

### Investigation

- Other reports for the same user submitted successfully.
- SQL lookup confirmed report status and attachments.
- Logs indicated the attached file was corrupted.

### Resolution

Advised the user to remove the attachment and re-upload a new copy.

User confirmed submission succeeded.

Conclusion: record-specific issue caused by corrupted attachment.

---

## Ticket 3 — Reproducible Bug

ID: INC-2092  
Impact: Moderate (multiple users)

### Error

“Attachment processing error: unsupported image encoding.”

### Investigation

- Reproduced the issue using two test reports.
- PNG files exported from iPhone High Efficiency format failed.
- JPG and PDF attachments worked correctly.

### Action

Provided workaround to affected users:

Convert images to JPG or PDF before uploading.

Escalated the issue to engineering with reproduction steps, timestamps, affected report IDs, and request IDs captured from failed submissions.

### Outcome

Workaround restored functionality while engineering investigated the encoding bug.


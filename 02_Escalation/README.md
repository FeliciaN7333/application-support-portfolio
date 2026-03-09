# 02 — Escalation Packet

Example escalation created after confirming a reproducible attachment-processing bug.

---

## Issue Summary

Expense report submission fails when certain PNG image formats are attached.

**Environment:** Production  
**Start time:** 2025-01-15 3:30 PM CST

---

## Impact

Multiple employees were unable to submit expense reports.

---

## Reproduction Steps

1. Create an expense report.
2. Attach a PNG exported from iPhone High Efficiency format.
3. Submit the report.

**Result:** Submission fails with an image encoding error.

---

## Expected Result

Expense report submits successfully with attached receipt.

---

## Actual Result

Submission fails during attachment processing due to unsupported image encoding.

---

## Isolation Checks

- Issue reproduced across multiple users.
- Issue reproduced across multiple reports.
- JPG and PDF attachments submitted successfully.
- Not related to permissions or account roles.

---

## Evidence Collected

**Affected report IDs:**  
- ER-1037  
- ER-1038  

**Request IDs captured from failed submission attempts:**  
- a1c9z7m2q8  
- p0x4k3v8n1  

**Additional support data collected:**  
- timestamps of failed submissions
- exact user-facing error message
- file type comparison results (PNG vs JPG/PDF)

---

## Temporary Workaround

Convert PNG files to PDF or standard JPG before uploading.

---

## Escalation Request

Escalated the issue to engineering with reproduction steps, timestamps, affected report IDs, and request IDs from the failed submissions so the team could trace the errors in the logs.

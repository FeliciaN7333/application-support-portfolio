# 03 — Knowledge Base Article 

## Expense Report Won’t Submit — Troubleshooting Guide

This guide is intended for support analysts troubleshooting expense report submission failures in the **SpendWise** expense management application.

---

## Common Symptoms

Users may report one or more of the following:

- “Submit failed”
- Attachment processing error
- Error 500
- Expense report stuck in pending status
- Submission button returns an unexpected error

---

## Information to Collect First

Before troubleshooting, gather the following:

- Report ID
- User email or user ID
- Timestamp of the failure
- Exact error message shown to the user
- Screenshot if available

This information helps determine whether the issue is **record-specific or system-wide**.

---

## Initial Triage Workflow

### 1 — Confirm Environment

Verify whether the issue occurred in **Production** or **Staging**.

---

### 2 — Determine Scope

Ask the following:

- Is the issue affecting **only one user**?
- Does the issue occur on **only one report**?
- Are **multiple users experiencing the same failure**?
- Did the issue begin **around the same time for multiple users**?

This helps determine whether the issue is:

- record-specific
- user-specific
- workflow-related
- or a broader application defect

---

### 3 — Check for Common Patterns

Look for patterns such as:

- attachment-related failures
- specific file formats causing errors
- reports stuck at a specific workflow stage 
- spikes in similar error messages

---

## Common Root Causes and Resolutions

### Corrupted Attachment

**Signs**

- Only one report fails
- Other reports from the same user submit successfully

**Resolution**

Remove the attachment and upload a new copy before submitting again.

---

### Unsupported Image Format

**Signs**

- PNG attachments fail
- JPG or PDF attachments submit successfully

**Resolution**

Convert the image to **JPG or PDF** before uploading.

---

### Report Stuck in Workflow

**Signs**

- Report remains in pending status longer than expected

**Resolution**

Verify the report status and review status history using SQL.

---

### Possible Application Issue

**Signs**

- Multiple users fail at the same step
- Failures begin within a short time window

**Resolution**

Collect evidence and escalate to engineering.

---

## When to Escalate

Escalate the issue when:

- the problem is reproducible
- multiple users are affected
- the same error appears across multiple reports
- the issue cannot be resolved with common troubleshooting steps

---

## Evidence to Include in Escalations

When escalating to engineering, include:

- affected report IDs
- timestamps of failures
- exact error messages
- reproduction steps
- request or correlation IDs if available
- results of any isolation testing already performed

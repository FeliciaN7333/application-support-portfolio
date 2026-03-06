# 04 — SQL Pack (10 queries)
---
Example SQL queries used for troubleshooting and validation in an internal expense management application.
These are written in a support troubleshooting style.
---
## 1 - Find user by email

SELECT user_id, full_name, email, department, account_status
FROM users
WHERE email = 'example@company.com';
---
## 2 - Check a user's role

SELECT u.email, r.role_name
FROM users u
JOIN user_roles ur ON ur.user_id = u.user_id
JOIN roles r ON r.role_id = ur.role_id
WHERE u.email = 'example@comapny.com';
---
## 3 - Pull expense report details

SELECT report_id, user_id, status, total_amount, created_at
FROM expense_reports
WHERE report_id = 'ER-1033';
---
## 4 - View report status history 

SELECT report_id, status, changed_at
FROM report_status_history
WHERE report_id = 'ER-1033'
ORDER BY changed_at DESC; 
---
## 5 - Find reports for a specific user 

SELECT report_id, status, total_amount, created_at
FROM expense_reports
WHERE user_id = 7
ORDER BY created_at DESC;
---
## 6 - Check attachment records for a report

SELECT attachment_id, report_id, file_type, file_size, uploaded_at
FROM attachments 
WHERE report_id = 'ER-1033';
---
## 7 - Find recent submission failures

SELECT report_id, error_message, created_at
FROM submission_errors
WHERE created_at >= NOW() - INTERVAL '1 hour'
ORDER BY created_at DESC;
--- 
## 8 - Find reports stuck in pending status 

SELECT report_id, user_id, created_at
FROM expense-reports
WHERE status = 'Pending'
AND created_at < NOW() - INTERVA; '2 hours';
---
## 9 - Find reports by amount threshold

SELECT report_id, total_amount, status
FROM expense_reports
WHERE total_amount > 5000
ORDER BY total_amount DESC;
---
## 10 - Find activity by request ID

SELECT request_id, endpoint, status_code, created_at
FROM api_logs
WHERE request_id = 'a1c9z7m2q8';
---



















 

# 🗄️ SQL Database Validation Log

This document details the structured SQL verification queries executed to validate the integrity of the data layer.

## 📊 Module: User Data Layer Auditing

### 1. Verify New User Registration Entry
* **Goal:** Confirm a user account created via the frontend/API layer is correctly stored in the backend database.
* **SQL Query:**
  ```sql
  SELECT user_id, email, account_status, created_at 
  FROM user_profiles 
  WHERE email = 'newuser@email.com';
  ```
* **Expected Result:** A single row is returned displaying the correct email string alongside a matching `account_status` flag set to `'Active'`.

### 2. Verify Session Security Parameters
* **Goal:** Audit the sessions table to ensure empty token values are blocked from logging in.
* **SQL Query:**
  ```sql
  SELECT session_id, user_id 
  FROM active_sessions 
  WHERE auth_token IS NULL;
  ```
* **Expected Result:** Zero rows are returned (`0 rows fetched`). This confirms the data system does not hold any open sessions missing active validation tokens.

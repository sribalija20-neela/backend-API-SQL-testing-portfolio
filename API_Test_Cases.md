# 🌐 REST API Test Suite (Postman Verification Log)

This document maps out backend API checks designed to validate the stability of a User Profile Management system.

## 👥 Module: User Management Endpoints

| Endpoint URL | HTTP Method | Test Scenario Description | Expected Status Code | Expected JSON Response Parameters |
| :--- | :--- | :--- | :--- | :--- |
| `/api/users` | `GET` | Retrieve list of all active users | `200 OK` | Array containing `id`, `email`, and `status` fields. |
| `/api/register` | `POST` | Create a new user account with unique email | `201 Created` | Returns `id` of user along with registration timestamp. |
| `/api/login` | `POST` | Login attempt with a missing password field | `400 Bad Request` | Returns explicit error message: `"Missing password"`. |
| `/api/users/999` | `GET` | Request a user ID that does not exist | `404 Not Found` | Returns clean, structured empty object or error status. |

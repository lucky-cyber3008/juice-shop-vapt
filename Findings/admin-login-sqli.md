# SQL Injection – Login Bypass
      
    ADMIN LOGIN

## Description

SQL Injection (SQLi) is a critical vulnerability that occurs when untrusted user input is improperly handled within an SQL query. This can allow attackers to manipulate database queries and gain unauthorized access to data or systems.

In OWASP Juice Shop, the login functionality is vulnerable to SQL Injection, allowing us to bypass authentication using crafted input.

---

## Steps to Reproduce

1. **Navigate to Login Page**  
   Open OWASP Juice Shop and go to the **Login** page.

2. **Initial Login Attempt**
   - Enter any email and password to generate a typical login request.
   - Capture the request using **Burp Suite**.

3. **Send Request to Repeater**  
   - Right-click the captured login request and **send it to Repeater**.

4. **Craft the Payload**
   - In the **email** field, use the following payload:
     ```
     ' OR TRUE --
     ```
   - In the **password** field, use any dummy value (e.g., `123456789`).
   - The SQL query becomes logically true, bypassing authentication.

5. **Send the Modified Request**  
   - Send the request from the Repeater tab.
   - Observe the response indicating a successful login, often with a status `200 OK`.

6. **Observe Application Behavior**
   - On successful execution, you are logged in as an admin or another user depending on the query logic.

---

## Payload Used

- **Email field**:
' OR TRUE --
- **Password field**:
123456789(Any Dummy Password)


## 📸 Screenshot

![DOM XSS Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → Admin-Login

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.

# ⭐ Register as Admin – OWASP Juice Shop

## 🔍 Description

This challenge demonstrates an insecure implementation of user role assignment during registration. By injecting a `role` parameter into the JSON request body, an attacker can escalate their privileges and register as an admin, which should never be allowed from the client side.

---

## 🛠️ Steps to Reproduce

1. **Go to the Registration Page**
   - Navigate to:
     ```
     http://127.0.0.1:4200/#/register
     ```

2. **Fill Out Registration Form**
   - Enter a valid:
     - **Email**
     - **Password**
     - **Repeat Password**

3. **Intercept the Request**
   - Open **Burp Suite** and turn on **intercept** in the **Proxy** tab.
   - Submit the registration form to capture the `POST` request to:
     ```
     /api/Users/
     ```

4. **Inject Admin Role in JSON Body**
   - Modify the intercepted request body to include:
     ```json
     {
       "email": "attacker@juice.sh",
       "password": "P@ssw0rd!",
       "passwordRepeat": "P@ssw0rd!",
       "role": "admin"
     }
     ```

5. **Forward and Modify Response**
   - Right-click and choose:
     ```
     Do Intercept → Response to this request
     ```
   - Forward the request.
   - You’ll see:
     ```
     HTTP/1.1 201 Created
     ```
   - The user is successfully created with **admin privileges**.

6. **Verify Challenge Completion**
   - The challenge is marked as **solved** in the Juice Shop scoreboard.

---

## 📸 Screenshot

![Admin User Registration Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → /Improper-Input-Validation`

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.

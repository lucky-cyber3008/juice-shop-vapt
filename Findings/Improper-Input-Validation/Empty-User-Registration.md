# ⭐ Empty User Registration – OWASP Juice Shop

## 🔍 Description

This challenge demonstrates how a user can trick the application into accepting a registration with empty credentials by manipulating HTTP responses. While the backend correctly rejects the registration, the frontend assumes success if it receives a `200 OK`, exposing a flaw in how client-side and server-side validation responses are handled.

---

## 🛠️ Steps to Reproduce

1. **Go to the Registration Page**
   - Navigate to:
     ```
     http://127.0.0.1:4200/#/register
     ```

2. **Fill Out Initial Details**
   - Enter values for:
     - **Email**
     - **Password**
     - **Repeat Password**

3. **Intercept the Registration Request**
   - Open **Burp Suite** and enable **intercept** in the **Proxy** tab.
   - Submit the registration form.
   - Capture the outgoing `POST` request to the `/api/Users/` endpoint.

4. **Clear Sensitive Fields Before Forwarding**
   - Without forwarding the request, clear the following fields in the intercepted JSON body:
     ```json
     {
       "email": "",
       "password": "",
       "passwordRepeat": ""
     }
     ```

5. **Modify the Server Response**
   - Right-click on the request and select:
     ```
     Do Intercept → Response to this request
     ```
   - In the response section, change:
     - HTTP Status: `400 Bad Request` → `200 OK`
     - Message body: `"Email and password fields cannot be empty"` → `"User Registered Successfully"`

6. **Forward the Modified Response**
   - Send the modified response to the browser.

7. **Verify Challenge Completion**
   - The frontend displays a success message.
   - The challenge is marked as solved in the Juice Shop challenge scoreboard.

---

## 📸 Screenshot

![Empty Registration Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → /Improper-Input-Validation`

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.

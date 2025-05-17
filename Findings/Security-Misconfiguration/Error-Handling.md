# 🗂️ Error Handling – OWASP Juice Shop

## 🔍 Description

This challenge focuses on improper **error handling** within the OWASP Juice Shop. The objective is to trigger an ungracefully handled or inconsistent error message, revealing that the application does not correctly manage unexpected input or misuse of endpoints.

---

## 🛠️ Steps to Reproduce

1. **Go to the Login Page**
   - Navigate to the Juice Shop login screen.

2. **Enter Random Credentials**
   - Fill in any random username and password.
   - Example:  
     ```
     Email: lucky@cyber  
     Password: 1234567890!@#$%^&*
     ```

3. **Intercept the Login Request**
   - Use **Burp Suite** (or similar proxy tool) and turn **Intercept On**.

4. **Modify the Endpoint**
   - Change the request line from:
     ```http
     POST /rest/user/login HTTP/1.1
     ```
     to:
     ```http
     POST /rest/user/logout HTTP/1.1
     ```

5. **Forward the Request**
   - Forward the modified request to the server.

---


## 📸 Screenshot

![Error Handling Proof]

📁 Screenshot location: `Reports/Screenshots/Security-Misconfiguration`

---

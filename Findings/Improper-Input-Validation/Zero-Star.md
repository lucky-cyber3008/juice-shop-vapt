# ⭐ Zero Stars Feedback – OWASP Juice Shop

## 🔍 Description

This challenge involves submitting a customer feedback with **zero stars**, which the application UI normally restricts. The vulnerability arises from a lack of proper server-side input validation, allowing users to bypass client-side restrictions and manipulate request data to submit an invalid rating.

---

## 🛠️ Steps to Reproduce

1. **Login with a User Account**
   - Use any valid user credentials to log in (e.g., a registered user).

2. **Go to the Customer Feedback Page**
   - Navigate to:
     ```
     http://127.0.0.1:4200/#/contact
     ```
   - Enter a comment:
     ```
     Zero Stars Challenge (***kyy@cyber)
     ```
   - Select any star rating (e.g., 2 stars).
   - Solve the CAPTCHA displayed.

3. **Intercept the Request with Burp Suite**
   - Turn on **intercept** in the **Proxy** tab of **Burp Suite**.
   - Submit the feedback form to intercept the outgoing request.

4. **Modify the Rating in the Request**
   - Locate and change this part of the JSON:
     ```json
     {
       "UserId": 25,
       "captchaId": 1,
       "captcha": "7",
       "comment": "Zero Stars Challenge (***kyy@cyber)",
       "rating": 2
     }
     ```
   - Change `"rating": 2` to:
     ```json
     "rating": 0
     ```

5. **Forward the Request**
   - Right-click and select:
     ```
     Do Intercept → Response to this request
     ```
   - Then forward the modified request.

6. **Verify Challenge Completion**
   - You should receive a `201 Created` response.
   - The challenge is now marked as solved in the Juice Shop interface.

---

## 📸 Screenshot

![Zero Stars Submission Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → /Improper-Input-Validation`

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.

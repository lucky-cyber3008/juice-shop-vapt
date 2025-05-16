# 🗣️ Forged Feedback – OWASP Juice Shop

## 🔍 Description

This challenge demonstrates a vulnerability where user input is not properly validated on the server side, allowing attackers to forge product reviews on behalf of another user. It simulates a real-world flaw in access control where trust is placed solely in client-provided data.

---

## 🛠️ Steps to Reproduce

1. **Login with a Valid User**
   - Use your own account:
     ```
     Email: lucky@cyber
     Password: ********
     ```

2. **Navigate to Any Product**
   - Open any product in the shop and click the **"Review"** button.
   - Enter your review message and rating, but **do not submit yet**.

3. **Intercept the Review Request**
   - Open **Burp Suite** and turn **Intercept ON**.
   - Submit the review in the Juice Shop frontend.
   - Capture the **PUT request** going to:
     ```
     /api/ProductReviews
     ```

4. **Modify Author Field**
   - In the intercepted request body, find the following:
     ```json
     {
       "message": "Not a Good One",
       "author": "lucky@cyber"
     }
     ```
   - Change the value of `author` to another user:
     ```json
     {
       "message": "Nice product!",
       "author": "defaulter@cyber"
     }
     ```

5. **Send Modified Request**
   - Right-click the request → **Do Intercept → Response to this request**.
   - Forward the modified request.

6. **Observe the Response**
   - The server responds with:
     ```
     HTTP/1.1 201 Created
     {
       "status": "Review successfully created"
     }
     ```
   - This indicates the feedback was accepted as if it was from `defaulter@cyber`.

---
## 📸 Screenshot

![Forged Feedback  Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → Broken-Acces-Control/

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.

# 🧪 NoSQL Injection – Review Ownership Manipulation (Author Field Bypass)

## 🔍 Description

This vulnerability targets the review-editing functionality in OWASP Juice Shop. By intercepting a **PUT** request to update a product review and replacing it with a **PATCH** request, we can manipulate the `author` parameter using a NoSQL injection payload.

The goal is to bypass ownership checks and modify reviews created by other users.

---

## 🛠️ Steps to Reproduce

1. **Login as Any Valid User**
   - Visit: `http://127.0.0.1:4200/#/login`
   - Login using any account (e.g., `jim@juice-sh.op`).

2. **Add a Review**
   - Go to any product (e.g., Apple Juice).
   - Submit a review (e.g., "Nice product!").

3. **Intercept the Review Edit Request**
   - Open **Burp Suite** and enable intercept.
   - Attempt to edit your review.
   - Capture the **PUT** request (usually to `/api/Products/reviews`).

4. **Send to Repeater and Modify Request**
   - Right-click → **Send to Repeater**.
   - Change the request method from `PUT` to `PATCH`.

5. **Modify the Payload**
   - Replace the body of the request with the following JSON:
     ```json
     {
       "message": "Hacked review",
       "author": {
         "id": { "$ne": -1 }
       }
     }
     ```
   - This bypasses the server’s ownership check by injecting a condition that is always true.

6. **Send the Request**
   - Click **Send** in Repeater.
   - The server accepts the modification even if you don't own the review.

---

## 📸 Screenshot
# 🧪 NoSQL Injection – Review Ownership Manipulation (Author Field Bypass)

## 🔍 Description

This vulnerability targets the review-editing functionality in OWASP Juice Shop. By intercepting a **PUT** request to update a product review and replacing it with a **PATCH** request, we can manipulate the `author` parameter using a NoSQL injection payload.

The goal is to bypass ownership checks and modify reviews created by other users.

---

## 🛠️ Steps to Reproduce

1. **Login as Any Valid User**
   - Visit: `http://127.0.0.1:4200/#/login`
   - Login using any account (e.g., `jim@juice-sh.op`).

2. **Add a Review**
   - Go to any product (e.g., Apple Juice).
   - Submit a review (e.g., "Nice product!").

3. **Intercept the Review Edit Request**
   - Open **Burp Suite** and enable intercept.
   - Attempt to edit your review.
   - Capture the **PUT** request (usually to `/api/Products/reviews`).

4. **Send to Repeater and Modify Request**
   - Right-click → **Send to Repeater**.
   - Change the request method from `PUT` to `PATCH`.

5. **Modify the Payload**
   - Replace the body of the request with the following JSON:
     ```json
     {
       "message": "Hacked review",
       "author": {
         "id": { "$ne": -1 }
       }
     }
     ```
   - This bypasses the server’s ownership check by injecting a condition that is always true.

6. **Send the Request**
   - Click **Send** in Repeater.
   - The server accepts the modification even if you don't own the review.

---

## 📸 Screenshot
📁 *Path: `Reports/Screenshots/Injection/`*

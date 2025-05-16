# 🛑 Broken Access Control (BAC) – View Another User’s Basket | OWASP Juice Shop

## 🔍 Description

**Broken Access Control** occurs when an application fails to properly restrict access to resources, allowing unauthorized users to view or manipulate data belonging to others. In this scenario, the application does not validate if a user is accessing only their own basket.

This can lead to **information disclosure**, **unauthorized actions**, and **horizontal privilege escalation** where users can impersonate or interfere with other users' data.

---

## 🛠️ Steps to Reproduce

1. **Log in to OWASP Juice Shop**
   - Use any valid user credentials to log in (e.g., `test@juice-sh.op / password123`).

2. **Navigate to the Basket Page**
   - Click on the **"Your Basket"** section from the navigation menu.

3. **Capture the Basket Request**
   - Open **Burp Suite** and intercept the traffic.
   - Observe the GET request to an endpoint like:
     ```
     GET /rest/basket/3 HTTP/1.1
     ```

4. **Send to Repeater**
   - Right-click the captured request and send it to **Repeater**.

5. **Modify the Basket ID**
   - Change the basket ID in the URL from your own (e.g., `/basket/3`) to another user’s (e.g., `/basket/2`).
   - Send the request.

6. **Observe the Response**
   - If the server returns data for basket ID `2`, the vulnerability is confirmed.
   - You’ll see details of another user’s basket items.

---

## 📸 Screenshot

![BAC Proof Screenshot]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → BAC/`

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.

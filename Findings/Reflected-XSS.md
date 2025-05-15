# 🧪 Reflected Cross-Site Scripting (Reflected XSS) – OWASP Juice Shop

## 🔍 Description

**Reflected XSS** occurs when user-supplied input is immediately included in the page's response by the server without proper sanitization. Unlike Stored XSS, the payload is not saved—it's reflected in the response and executed instantly when the malicious link is visited.

This vulnerability allows attackers to inject JavaScript into URLs that execute in the context of a victim’s browser, potentially leading to session hijacking, phishing, or redirection attacks.

---

## 🛠️ Steps to Reproduce

1. **Login to the Application**
   - Open the OWASP Juice Shop web application.
   - Log in using any valid user credentials.

2. **Place an Order**
   - Add any product to the shopping basket.
   - Proceed to checkout and complete the purchase.

3. **Access Order History**
   - Navigate to **My Account** → **Order and Payment** → **Order History**.

4. **Trigger the Order Tracking View**
   - Click on the **truck icon** next to any completed order.
   - This redirects to a **tracking URL** that looks like:
     ```
     http://<host>/track-result?id=abc123
     ```

5. **Inject the Reflected XSS Payload**
   - Replace the `id` parameter with a malicious payload:
     ```html
     <iframe src="javascript:alert(`xss`)">
     ```
   - Full URL becomes:
     ```
     http://<host>/track-result?id=<iframe src="javascript:alert(`xss`)">
     ```

6. **Observe the Result**
   - Press Enter to visit the URL.
   - A JavaScript alert box appears displaying `xss`, confirming the XSS payload was executed.

---

## 🎯 Impact

This vulnerability can be exploited to craft malicious URLs that, when clicked by a user, execute arbitrary JavaScript in their browser. If a victim is logged in, an attacker could potentially:
- Hijack their session.
- Perform unauthorized actions.
- Redirect them to phishing or malicious sites.

---

## 📸 Screenshot

![Reflected XSS Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → /XSS/Reflected/`

📁 Each vulnerability in this project has a **dedicated folder** under `Reports/Screenshots/` for better organization and clarity.

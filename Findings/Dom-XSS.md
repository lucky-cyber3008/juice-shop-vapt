# 🧪 DOM-Based Cross-Site Scripting (DOM XSS) – OWASP Juice Shop

## 🔍 Description

**DOM-Based XSS** occurs when client-side JavaScript modifies the page based on unsanitized user input. Unlike reflected or stored XSS, the payload never reaches the server; instead, it’s executed entirely on the client side via the DOM.

This vulnerability allows an attacker to inject malicious scripts into the page and can lead to session hijacking, credential theft, or redirection to malicious websites.

---

## 🛠️ Steps to Reproduce

1. **Navigate to the Search Function**
   - Open the OWASP Juice Shop web application.
   - Click on the search icon in the navigation bar.

2. **Initial Request Capture**
   - Enter a random search term like `test` and submit.
   - Intercept the request using **Burp Suite**.

3. **Send Request to Repeater**
   - Right-click the request and choose **"Send to Repeater"**.

4. **Modify Payload in Repeater**
   - Replace the search query with the XSS payload:
     ```html
     <iframe src="javascript:alert(`xss`)">
     ```
   - This will result in a request like:
     ```
     GET /?search=<iframe src="javascript:alert(`xss`)"> HTTP/1.1
     ```

5. **Observe the Response**
   - The server returns a **400 Bad Request**, but don’t be discouraged.
   - Copy the full URL from the repeater, such as:
     ```
     http://<host>/?search=<iframe src="javascript:alert(`xss`)">
     ```
   - Paste it directly into your browser’s address bar and hit Enter.

6. **Result**
   - The browser renders the payload.
   - An alert box appears with the message `xss`, confirming successful execution.

## 📸 Screenshot

![DOM XSS Proof](./Reports/Screenshots/DOM/)

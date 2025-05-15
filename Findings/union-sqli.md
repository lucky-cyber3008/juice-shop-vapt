# 🧪 Database Schema Exposure – OWASP Juice Shop

## 🔍 Description

This vulnerability demonstrates an **SQL Injection** attack that allows an attacker to retrieve the database schema by exploiting the search functionality of the application.

Using a UNION-based SQLi payload, it's possible to extract table creation statements from the internal `sqlite_master` table — the schema metadata table used by SQLite.

---

## 🛠️ Steps to Reproduce

1. **Navigate to the Search Function**
   - Launch the OWASP Juice Shop web application.
   - Click on the search icon (magnifying glass) on the top-right.

2. **Initial Input Test**
   - Search for a term like:
     ```
     apple'
     ```
   - You’ll see an error indicating a possible SQL syntax issue, confirming injectable input.

3. **Intercept the Request**
   - Open **Burp Suite**.
   - Capture the search request in the Proxy tab:
     ```
     GET /rest/products/search?q=apple' HTTP/1.1
     ```

4. **Send to Repeater**
   - Right-click → **Send to Repeater**.
   - Replace the search parameter with the SQLi payload:
     ```
     ))UNION SELECT sql,2,3,4,5,6,7,8,9 FROM sqlite_master--
     ```

5. **Observe the Response**
   - You will see output like:
     ```
     CREATE TABLE Users (...);
     CREATE TABLE Challenges (...);
     ```
   - These are the internal database schema definitions.

6. **Result**
   - You’ve successfully exposed the database structure, completing the **Database Schema** challenge.

---

## 📸 Screenshot

![Database Schema SQLi Proof]

🔍 *To view this screenshot manually, navigate to:*  
`Reports/ → Screenshots/ → Injection/`

📁 This folder contains PoC screenshots specific to SQL injection and schema-related vulnerabilities.

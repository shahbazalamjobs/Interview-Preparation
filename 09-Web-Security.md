
**Web Security Basics:**

1. **Importance of Web Security:**
   - Protects sensitive data, user privacy, and application integrity.
   - Prevents unauthorized access, data breaches, and malicious activities.
   - Mitigates financial losses, legal issues, and reputational damage.

2. **Difference between Authentication and Authorization:**
   - **Authentication:** Verifying user identity using credentials (username, password).
   - **Authorization:** Determining user permissions to access resources or perform actions.

3. **Confidentiality, Integrity, and Availability (CIA):**
   - **Confidentiality:** Ensures limited access to sensitive data via encryption and access controls.
   - **Integrity:** Maintains data accuracy and consistency using hashing and digital signatures.
   - **Availability:** Ensures system and resource accessibility to minimize downtime.

**Cross-Site Scripting (XSS):**

4. **What is XSS:**
   - Attacker injects malicious scripts into a web app, executed in other users' browsers.

5. **How XSS Occurs:**
   - Improper validation/sanitization of user input.
   - Malicious scripts are injected and executed in other users' contexts.

6. **Reflected XSS vs. Stored XSS:**
   - **Reflected XSS:** Script reflects off the server to victim (e.g., via manipulated links).
   - **Stored XSS:** Script stored on server, executed when other users access compromised content.

7. **Preventing XSS Attacks:**
   - Sanitize user input, escape/validate before rendering.
   - Use Content Security Policy (CSP) to restrict script execution.
   - Encode output to prevent script execution.
   - Adopt secure coding practices and frameworks.

**Cross-Site Request Forgery (CSRF):**

8. **CSRF Attacks and How They Work:**
   - Tricking authenticated users to unknowingly perform actions.
   - Malicious links/forms trigger actions on the target site.

9. **Preventing CSRF Attacks:**
   - Use anti-CSRF tokens in forms to validate requests.
   - Check "Referer" header to verify request origin.
   - Implement Same-Site cookies to restrict cookie sharing.
   - Utilize frameworks with built-in CSRF protection.

**SQL Injection:**

10. **What is SQL Injection:**
    - Exploiting vulnerabilities to inject malicious SQL code.
    - Manipulates application's SQL queries, leading to unauthorized access or data disclosure.

11. **Exploiting SQL Injection:**
    - Inputting malicious SQL statements into user inputs.
    - Lack of input validation/sanitization enables code execution.

12. **Protecting Against SQL Injection:**
    - Use prepared statements and parameterized queries.
    - Implement input validation and sanitization.
    - Apply least privilege principles for database access.
    - Regularly update and patch software/frameworks.

**Clickjacking:**

13. **What is Clickjacking:**
    - Malicious overlay (e.g., transparent iframe) over a legitimate site.
    - User interacts with overlay, unknowingly performing actions on hidden site.

14. **Mitigating Clickjacking:**
    - Use "X-Frame-Options" header to control iframe embedding.
    - Implement "Content Security Policy" (CSP) to restrict embedding domains.
    - Utilize JavaScript frame-busting techniques to prevent unauthorized iframing.

Understanding these concepts and applying corresponding preventive measures is essential for maintaining robust web security and safeguarding both user data and application functionality.

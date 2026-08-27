# Secure Coding Analysis

## Scope

This analysis documents common web-application security weaknesses and their remediation in a Flask-based lab application.

## Findings and Remediations

### 1. SQL Injection

**Issue:** User input was incorporated into SQL statements through string construction.

**Impact:** An attacker could manipulate the query logic and bypass authentication.

**Remediation:** Use parameterized queries / prepared statements and treat user input as data.

### 2. Insecure Session Handling

**Issue:** The application stored raw login input in the session.

**Remediation:** Store only trusted, server-validated identity data after successful authentication. Harden cookie attributes such as `HttpOnly` and `Secure` where HTTPS is available.

### 3. Cross-Site Scripting

**Issue:** Unsanitized user-controlled content could be rendered by the dashboard.

**Remediation:** Validate input, encode output, and use template auto-escaping.

### 4. Cross-Site Request Forgery

**Issue:** State-changing requests required protection from forged cross-origin requests.

**Remediation:** Add CSRF tokens and validate them on state-changing requests.

### 5. Weak Password Storage

**Issue:** Plain-text password storage creates severe exposure after a database compromise.

**Remediation:** Store passwords using a strong, salted password-hashing algorithm such as bcrypt.

### 6. Information Disclosure

**Issue:** Framework debug/error responses can reveal implementation details.

**Remediation:** Use controlled 404/500 responses and disable debug mode in production.

### 7. Login Abuse

**Issue:** Repeated authentication failures can enable brute-force attempts.

**Remediation:** Apply rate limiting or account/IP-based throttling and monitor authentication failures.

## Security Principles Demonstrated

- Defense in depth
- Least privilege
- Secure-by-default configuration
- Input validation and output encoding
- Separation of trusted and untrusted data
- Secure authentication and session management
- Fail-safe error handling

> The included material is an educational demonstration of defensive security practices. Test environments should remain isolated from production systems.

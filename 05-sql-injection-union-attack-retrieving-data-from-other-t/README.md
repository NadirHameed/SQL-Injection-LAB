# Lab 05: SQL injection UNION attack, retrieving data from other tables

| | |
|---|---|
| **Platform** | PortSwigger Web Security Academy |
| **Difficulty** | Practitioner |
| **Database** | Any |
| **Category** | SQL Injection |
| **Status** | ⬜ Solved |
| **Tools** | Burp Suite (Proxy, Repeater, Intruder) |

## Objective
_Describe in your own words what the lab asks you to achieve._

## Vulnerable Component
`GET /filter?category=<value>`

## Technique
Use UNION to read credentials from a `users` table.

## Reference Payloads
Technique skeletons for this lab type. Adjust column count, table names and comment style to your lab instance.

```sql
' UNION SELECT username, password FROM users--
```

> Note: Requires column count and two text-compatible columns from the earlier labs.

## Steps to Reproduce
1. Intercept the vulnerable request in Burp Proxy and send it to Repeater.
2. Confirm injection (single quote / boolean / delay test) and record the response difference.
3. _Add your exact steps here._
4. Final payload that solved the lab:

```
<paste final request / payload>
```

## Proof of Concept
Add Burp screenshots to the `screenshots/` folder and reference them here:

```
![Request in Repeater](screenshots/01-request.png)
![Response / solved banner](screenshots/02-solved.png)
```

## Impact
_What could an attacker do in a real application (data disclosure, authentication bypass, full DB takeover)?_

## Root Cause
User-controlled input is concatenated directly into a SQL query string instead of being passed as a bound parameter.

## Remediation
- Use parameterized queries / prepared statements for all database access.
- Apply least-privilege database accounts (no access to `information_schema` or unrelated tables where possible).
- Validate input against an allow-list; do not rely on WAF filtering alone.
- Suppress verbose database errors in production responses.

## References
- PortSwigger Academy: <https://portswigger.net/web-security/sql-injection>
- OWASP SQL Injection Prevention Cheat Sheet

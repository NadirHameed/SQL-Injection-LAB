# PortSwigger SQL Injection Labs: Write-ups

Step-by-step write-ups with Burp Suite proof-of-concepts for the [PortSwigger Web Security Academy SQL injection labs](https://portswigger.net/web-security/sql-injection).

Part of my **Web & API Penetration Testing** portfolio.

## Scope
18 labs covering the full SQL injection learning path:

- Retrieving hidden data and authentication bypass
- UNION attacks (column count, string columns, multi-table and multi-value extraction)
- Database fingerprinting (Oracle, MySQL, Microsoft, PostgreSQL)
- Listing database contents (`information_schema` and Oracle catalog)
- Blind SQLi: conditional responses, conditional errors, time delays
- Out-of-band (OAST) interaction and data exfiltration
- Visible error-based SQLi
- WAF filter bypass via XML encoding

## Lab Index
| # | Lab | Level | DB | Status |
|---|-----|-------|----|--------|
| 01 | [SQL injection vulnerability in WHERE clause allowing retrieval of hidden data](labs/01-sql-injection-vulnerability-in-where-clause-allowing-re/) | Apprentice | Any | ⬜ |
| 02 | [SQL injection vulnerability allowing login bypass](labs/02-sql-injection-vulnerability-allowing-login-bypass/) | Apprentice | Any | ⬜ |
| 03 | [SQL injection UNION attack, determining the number of columns returned by the query](labs/03-sql-injection-union-attack-determining-the-number-of-co/) | Practitioner | Any | ⬜ |
| 04 | [SQL injection UNION attack, finding a column containing text](labs/04-sql-injection-union-attack-finding-a-column-containing/) | Practitioner | Any | ⬜ |
| 05 | [SQL injection UNION attack, retrieving data from other tables](labs/05-sql-injection-union-attack-retrieving-data-from-other-t/) | Practitioner | Any | ⬜ |
| 06 | [SQL injection UNION attack, retrieving multiple values in a single column](labs/06-sql-injection-union-attack-retrieving-multiple-values-i/) | Practitioner | PostgreSQL | ⬜ |
| 07 | [SQL injection attack, querying the database type and version on Oracle](labs/07-sql-injection-attack-querying-the-database-type-and-ver/) | Practitioner | Oracle | ⬜ |
| 08 | [SQL injection attack, querying the database type and version on MySQL and Microsoft](labs/08-sql-injection-attack-querying-the-database-type-and-ver/) | Practitioner | MySQL / MSSQL | ⬜ |
| 09 | [SQL injection attack, listing the database contents on non-Oracle databases](labs/09-sql-injection-attack-listing-the-database-contents-on-n/) | Practitioner | PostgreSQL | ⬜ |
| 10 | [SQL injection attack, listing the database contents on Oracle](labs/10-sql-injection-attack-listing-the-database-contents-on-o/) | Practitioner | Oracle | ⬜ |
| 11 | [Blind SQL injection with conditional responses](labs/11-blind-sql-injection-with-conditional-responses/) | Practitioner | PostgreSQL | ⬜ |
| 12 | [Blind SQL injection with conditional errors](labs/12-blind-sql-injection-with-conditional-errors/) | Practitioner | Oracle | ⬜ |
| 13 | [Visible error-based SQL injection](labs/13-visible-error-based-sql-injection/) | Practitioner | PostgreSQL | ⬜ |
| 14 | [Blind SQL injection with time delays](labs/14-blind-sql-injection-with-time-delays/) | Practitioner | PostgreSQL | ⬜ |
| 15 | [Blind SQL injection with time delays and information retrieval](labs/15-blind-sql-injection-with-time-delays-and-information-re/) | Practitioner | PostgreSQL | ⬜ |
| 16 | [Blind SQL injection with out-of-band interaction](labs/16-blind-sql-injection-with-out-of-band-interaction/) | Practitioner | Oracle | ⬜ |
| 17 | [Blind SQL injection with out-of-band data exfiltration](labs/17-blind-sql-injection-with-out-of-band-data-exfiltration/) | Practitioner | Oracle | ⬜ |
| 18 | [SQL injection with filter bypass via XML encoding](labs/18-sql-injection-with-filter-bypass-via-xml-encoding/) | Practitioner | PostgreSQL | ⬜ |

## Repository Structure
```
portswigger-sqli-labs/
├── README.md
├── cheatsheet.md              # Quick reference by database
├── labs/
│   ├── 01-.../
│   │   ├── README.md          # Write-up
│   │   └── screenshots/       # Burp POCs
│   └── ...
├── LICENSE
└── .gitignore
```

## Write-up Format
Each lab follows the same structure as my other lab repositories: Objective, Vulnerable Component, Technique, Steps to Reproduce, Proof of Concept, Impact, Root Cause, Remediation.

## Tools
Burp Suite (Proxy, Repeater, Intruder, Collaborator), Firefox / FoxyProxy, Hackvertor extension.

## Disclaimer
All testing was performed on PortSwigger's intentionally vulnerable lab environments, for educational purposes only. Do not use these techniques against systems you do not own or have explicit written permission to test.

## Author
**Nadir Hameed**: Penetration Tester
Portfolio: https://nadirhameed.netlify.app/

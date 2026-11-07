# 06 — Exposed Credentials

**Security area:** Sensitive data exposure / hardcoded credentials  
**Application:** OWASP Juice Shop 20.3.0 (local instance)

## Objective

Inspect client-side application code for credentials that should not be distributed to users' browsers.

## Testing performed

The challenge guidance instructed inspection of client-side code. Browser developer tools were used to inspect the bundled application JavaScript. The inspected source contained a testing account username and password embedded in the client-side login component:

- Username: `testing@juice-sh.op`
- Password: `IamUsedForTesting`

These are credentials intentionally provided by the vulnerable Juice Shop training application. They are reproduced here only as evidence of the lab challenge and must not be reused against any other system.

Retained evidence:

- `../Evidence/Exposed-Credentials/01-exposed-credentials-challenge-card.png` — challenge description.
- `../Evidence/Exposed-Credentials/02-client-side-source-inspection.png` — client-side source inspection showing the testing credentials.
- `../Evidence/Exposed-Credentials/03-exposed-credentials-success-banner.png` — application success notification confirming the challenge was solved.

## Outcome

**Successful challenge completion confirmed.** The client-side credentials were identified and the application displayed its success notification.

## Security impact

Anything shipped to the browser should be treated as public. Hardcoded credentials in client-side bundles can be extracted by any user who can download or inspect the application files. If such credentials are valid beyond a deliberately isolated test account, they may enable unauthorized access and lateral movement.

## Recommended remediation

- Never embed passwords, API secrets or privileged credentials in frontend code or static assets.
- Keep secrets in protected server-side configuration or a secrets-management service.
- Use narrowly scoped, short-lived credentials where service authentication is required.
- Rotate any secret that has been exposed and review logs for misuse.
- Use dedicated, low-privilege test accounts and disable them outside the required test environment.
- Include secret scanning in the build and CI/CD pipeline.

## Evidence

The source inspection screenshot records the hardcoded test credentials, and the success banner confirms that Juice Shop accepted the challenge completion.

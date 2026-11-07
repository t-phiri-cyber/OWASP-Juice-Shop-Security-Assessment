# 03 — DOM-Based Cross-Site Scripting (DOM XSS)

**Security area:** Cross-site scripting (CWE-79)  
**Application:** OWASP Juice Shop 20.3.0 (local instance)

## Objective

Determine whether attacker-controlled data processed by client-side JavaScript could be interpreted as executable content in the browser.

## Testing performed

A crafted value was supplied through the application's search URL. The test used an HTML/JavaScript injection pattern and resulted in a browser alert, demonstrating that the supplied input reached a client-side execution context.

Retained evidence:

- `../Evidence/DOM-XSS/01-dom-xss-alert-execution.png` — browser alert displayed after the crafted input was processed.

## Outcome

**Successful demonstration.** The alert confirms JavaScript execution in the browser in the tested local application context.

## Security impact

DOM XSS can allow injected script to execute in the context of the vulnerable site. Depending on browser protections and application behavior, this may enable actions as the victim, access to page content, or theft of data available to client-side scripts. The actual impact depends on session protections and the data exposed to the script.

## Recommended remediation

- Avoid assigning untrusted input to dangerous DOM sinks such as `innerHTML`.
- Prefer `textContent` or safe DOM construction APIs when displaying user input.
- Validate and encode data for the correct output context.
- Use a restrictive Content Security Policy as defense in depth; do not treat it as a substitute for safe DOM handling.
- Add security tests for URL parameters and other client-controlled sources.

## Evidence

The retained alert screenshot demonstrates execution. The exact payload should be treated as test evidence for the intentionally vulnerable local application only.

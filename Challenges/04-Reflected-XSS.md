# 04 — Reflected Cross-Site Scripting (Reflected XSS)

**Security area:** Cross-site scripting (CWE-79)  
**Application:** OWASP Juice Shop 20.3.0 (local instance)

## Objective

Test whether a value supplied in a URL parameter is reflected into the resulting page in an executable HTML context.

## Testing performed

A benign HTML heading marker was submitted through the search parameter. The page rendered the text as a heading rather than displaying the markup literally. A follow-up crafted input triggered a browser alert with the message `Reflected XSS`.

Retained evidence:

- `../Evidence/Reflected-XSS/01-reflected-html-heading.png` — heading markup rendered in the search results page.
- `../Evidence/Reflected-XSS/02-challenge-hint.png` — challenge guidance describing URL-parameter and HTML-tag probing.

The browser alert was also observed during the test session; the evidence pack does not contain a separate alert screenshot for this challenge.

## Outcome

**Successful demonstration reported and observed during the session.** The rendered heading indicates HTML interpretation, and the user subsequently reported the JavaScript alert. The retained screenshots directly show the HTML reflection and challenge hint, but not the alert itself.

## Security impact

Reflected XSS occurs when request data is returned in a page without suitable output encoding or sanitization. A crafted link may cause script execution when opened by another user, potentially enabling actions in that user's site context or access to page data.

## Recommended remediation

- Apply context-aware output encoding to all reflected values.
- Treat URL parameters as untrusted input.
- Avoid inserting reflected data using `innerHTML`; use safe text APIs where possible.
- Use a restrictive Content Security Policy as defense in depth.
- Add regression tests covering HTML and script-like input in search parameters.

## Evidence limitation

The retained screenshots show HTML interpretation but do not capture the subsequent JavaScript alert. This is noted rather than presenting an alert screenshot that is not in the evidence pack.

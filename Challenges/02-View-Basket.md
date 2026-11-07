# 02 — View Basket

**Security area:** Broken access control  
**Application:** OWASP Juice Shop 20.3.0 (local instance)

## Objective

Investigate whether basket information or basket operations could be accessed outside the authorization boundaries intended by the application.

## Testing performed

The investigation included:

- Opening the basket page and observing the basket state.
- Inspecting browser Network activity associated with product quantities and basket-related requests.
- Inspecting client-side event listeners for the basket interface.

Retained evidence:

- `../Evidence/View-Basket/01-basket-page.png` — basket page and displayed basket state.
- `../Evidence/View-Basket/02-quantities-network-request.png` — observed quantities request in browser developer tools.
- `../Evidence/View-Basket/03-event-listeners-inspection.png` — inspection of event listeners associated with the page.

## Outcome

The investigation was completed, but the retained evidence does not demonstrate that one user's basket was successfully accessed or modified by another unauthorized user. The observed requests and event listeners are useful diagnostic evidence, but by themselves do not establish a broken access-control vulnerability.

**Result:** No successful unauthorized-access exploit demonstrated; finding remains inconclusive under the recorded test conditions.

## Security significance

A basket endpoint that relies only on client-supplied identifiers, rather than verifying ownership on the server, could allow one user to view or manipulate another user's basket. This could expose personal or transaction information and permit unauthorized changes.

## Recommended remediation / verification controls

- Derive the authenticated user identity from the server-side session or token, not a client-controlled basket identifier.
- Verify basket ownership on every read, update and delete operation.
- Apply authorization checks at the API layer, not only in the browser interface.
- Test access using two separate accounts and attempt cross-account access with altered identifiers.
- Log and monitor denied access attempts without exposing sensitive basket data.

## Limitations

The available evidence does not include a successful cross-account access attempt. Accordingly, this report does not classify the challenge as a confirmed vulnerability or claim that exploitation succeeded.

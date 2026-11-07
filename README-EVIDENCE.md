# Evidence index

Evidence is grouped by the six Juice Shop challenges. Image filenames describe the captured activity.

| Challenge | Evidence included | What it supports |
|---|---|---|
| Database Schema | Challenge card | Challenge selection only; not independent proof of successful exploitation. |
| View Basket | Basket page, quantities network request, event-listener inspection | Investigation activity; no successful unauthorized access demonstrated. |
| DOM XSS | Browser alert execution | JavaScript execution in the tested local app. |
| Reflected XSS | Rendered HTML heading and challenge hint | HTML reflection and challenge guidance; alert was observed but not separately captured in the ZIP. |
| Password Strength | Success banner | Challenge completion. |
| Exposed Credentials | Challenge card, client-side source, success banner | Hardcoded lab credentials identified and challenge completion. |

Screenshots are evidence of what was visible during testing; they do not by themselves establish broader exploitability beyond the specific local test environment.

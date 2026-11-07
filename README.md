# OWASP Juice Shop Security Assessment

## Project overview

This project documents a practical security assessment of the OWASP Juice Shop intentionally vulnerable web application. The work focused on six selected challenges covering injection, cross-site scripting (XSS), authentication, access control and sensitive-data exposure.

**Environment:** OWASP Juice Shop 20.3.0, run locally on `http://localhost:3000`  
**Testing approach:** Manual, challenge-led testing using the application interface, browser developer tools and inspection of client-side JavaScript.  
**Scope:** The local Juice Shop instance only. No external systems were targeted.

## Challenge register

| # | Challenge | Security area | Recorded outcome |
|---|---|---|---|
| 1 | Database Schema | SQL injection / database exposure | User reported challenge completion; the retained evidence pack contains the challenge card only, not the exploit or success confirmation. |
| 2 | View Basket | Broken access control | Investigation documented; no successful unauthorized access was demonstrated in the retained evidence. |
| 3 | DOM XSS | Cross-site scripting | JavaScript execution demonstrated with a browser alert. |
| 4 | Reflected XSS | Cross-site scripting | JavaScript execution demonstrated with a browser alert. |
| 5 | Password Strength | Authentication / password security | Juice Shop success notification captured. |
| 6 | Exposed Credentials | Sensitive data exposure | Client-side credentials identified and Juice Shop success notification captured. |

## Repository structure

```text
OWASP-Juice-Shop-Security-Assessment/
├── README.md
├── Challenges/
│   ├── 01-Database-Schema.md
│   ├── 02-View-Basket.md
│   ├── 03-DOM-XSS.md
│   ├── 04-Reflected-XSS.md
│   ├── 05-Password-Strength.md
│   └── 06-Exposed-Credentials.md
├── Evidence/
│   ├── Database-Schema/
│   ├── View-Basket/
│   ├── DOM-XSS/
│   ├── Reflected-XSS/
│   ├── Password-Strength/
│   └── Exposed-Credentials/
└── Report/
    └── Final-Project-Report.pdf
```

## Key learning outcomes

- Identifying client-side XSS sinks and validating whether untrusted input is interpreted as HTML or JavaScript.
- Reviewing client-side application code for insecurely embedded secrets.
- Understanding the difference between an application challenge being investigated and a vulnerability being successfully demonstrated.
- Recording test evidence, limitations, impact and remediation recommendations.

## Responsible testing

Testing was conducted against the intentionally vulnerable local training application. The techniques and observations in this repository are for authorized learning and defensive security education. Do not apply them to systems without explicit permission.

## Evidence and reporting

Each challenge has a separate assessment in `Challenges/`. Screenshots are stored under the matching `Evidence/` folder. The final PDF report will consolidate the methodology, findings, evidence, limitations and remediation guidance.

**Evidence limitation:** The retained screenshot for Database Schema proves that the challenge was selected/viewed, but does not independently prove successful exploitation. The View Basket evidence records the investigation and observed requests/listeners, but does not prove unauthorized access. These are deliberately described as such rather than overstated.

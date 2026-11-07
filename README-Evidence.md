# OWASP Juice Shop – Selected Evidence

This folder contains selected screenshots from the practical testing shared in the conversation.

## Evidence notes
- **Database Schema:** The challenge card is included as context. A clear success-banner screenshot was not identified in the available uploads, so this image alone does not prove completion.
- **View Basket:** The basket page, a `GET /api/Quantities/` network request returning `304 Not Modified`, and event-listener inspection are included. These document the investigation; they do not demonstrate a successful access-control exploit.
- **DOM XSS:** The screenshot shows JavaScript executing an alert through the search input.
- **Reflected XSS:** The screenshot shows an HTML heading reflected in the search-results page. The separate challenge hint is included for context. Do not describe this as a confirmed alert-based reflected XSS unless that execution is separately evidenced.
- **Password Strength:** The success banner is visible in the combined screenshot.
- **Exposed Credentials:** The challenge card, client-side source inspection, and success banner are included.

The combined screenshot for Password Strength and Exposed Credentials is intentionally duplicated in both relevant folders because it evidences both success messages.

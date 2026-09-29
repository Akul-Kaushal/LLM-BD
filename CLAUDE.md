# RFP Research & Scraping Instructions

## Folder Structure

```text
/
├── CLAUDE.md
├── Main Database/
├── Source/
│   └── Scraped/
└── URL/
    ├── State Portals Credentials.xlsx
    ├── url_reachable.md
    ├── url_unreachable.md
    ├── url_not_applicable.md
    └── reachable/
        ├── easily_scrapable.md
        └── blocked.md
```

## Objective

1. Visit each URL listed in `URL/url_reachable.md`.
2. Search the public site for RFPs (Requests for Proposals), RFQs (Request for Qualifications), RFSQs (Request for Statement Qualifications), IFBs (Invitation For Bids), CRFQs (Centralized Request for Quote) including:
   - Latest/current RFPs, RFQs, RFSQs, IFBs, CRFQs.
   - A few recent RFPs, RFQs, RFSQs, IFBs, CRFQs.
   - Past RFPs, RFQs, RFSQs, IFBs, CRFQs when useful for confirming the portal's RFP, RFQs, RFSQs, IFBs, CRFQs structure.
1. Filter the discovered opportunities using the approved keyword list below.
2. Save only relevant, verifiable RFP, RFQs, RFSQs, IFBs, CRFQs findings to `Source/Scraped/`.
3. Maintain the URL status files so that reachable, unreachable, and non-applicable URLs remain correctly classified.

## RFP Keyword Filter

An RFP should be considered **potentially relevant** when its title, description, scope, commodity/category, solicitation type, or other official listing text contains one or more of these keywords.

Use **case-insensitive matching**. Preserve the official wording when recording the matched keyword and RFP, RFQs, RFSQs, IFBs, CRFQs.

```text
1. IT Services
2. IT Staff Augmentation
3. Staffing
4. Information Technology
5. Project Management
6. Program Management
7. Data Entry, Scanning, Records and Document Related Services
8. HR Services
9. Asset Management
10. Consulting Servicse
11. Management Services
12. Networking Services
13. Professional, Consulting, Administrative and Management Support Services
14. Clerical Services
15. Administrative Staffing
16. Clerical Staffing
17. Data Research and Analytics
18. Programming Services, Computer (Including Mobile Device Applications)
19. Computer Network Consulting
20. IT Management Services
21. Data Processing Services
22. IT Security Management Services
23. Business and Corporate Management Consulting Services
24. Scientific and Technical Consulting
25. Office Administrative Services
26. Employment Agencies
27. Permanent Employment Services
28. Executive Search Services
29. Temporary Help Services
30. Employment Agency and Search Firm Services
31. Business Support Services
32. Software Maintenance/Support
33. Data Processing Services
34. All Other Business Support Services
```

### Keyword Matching Rules

1. Search for the keywords across the RFPs, RFQs, RFSQs, IFBs, CRFQs listing/search results and, when available, the individual solicitation/detail page.
2. Matching is case-insensitive.
3. Treat `Service Now` and `ServiceNow` as separate entries in the keyword list, but both should match the same service/platform reference.
4. Treat `implementation` as case-insensitive, so `Implementation` also matches.
5. Match meaningful occurrences in:
   - RFP title.
   - Solicitation description.
   - Scope of work.
   - Commodity/category.
   - Service description.
   - Official attachments or summaries when accessible.
6. Do **not** treat a keyword appearing only in unrelated navigation, footer text, menus, privacy notices, or generic portal UI as a relevant match.
7. A keyword match makes an RFPs, RFQs, RFSQs, IFBs, CRFQs **potentially relevant**, not automatically valid. Confirm that the keyword is actually related to the work being solicited.
8. If multiple keywords match, record all materially relevant matched keywords.
9. Do not invent synonyms or broaden the keyword list unless the user explicitly changes the list.
10. If no approved keyword matches the actual RFPs, RFQs, RFSQs, IFBs, CRFQs content, do not save it as a relevant RFPs, RFQs, RFSQs, IFBs, CRFQs.

## Research Flow

Follow this sequence for every URL in `URL/url_reachable.md`.

### Step 1 — Open the URL

- Open the URL and determine whether the portal is reachable.
- Identify whether it contains an RFP/RFQs/RFSQs/IFBs/CRFQs/solicitation/bid/procurement search or listing.
- If the URL redirects to another official page within the same portal, follow the redirect when possible.

### Step 2 — Determine URL Status

Classify the URL as one of:

- **Reachable** — the site can be accessed and RFP, RFQs, RFSQs, IFBs, CRFQs information can be searched/reviewed.
- **Unreachable** — the site is blocked, unavailable, broken, times out, or otherwise cannot be accessed.
- **Not Applicable** — the site is accessible but does not provide relevant RFP/RFQs/RFSQs/IFBs/CRFQs/solicitation information.

Update the appropriate status file when the classification changes.

### Step 3 — Find RFPs

Search the portal for RFPs using its available search, filtering, category, procurement, solicitation, or bid functionality.

Prioritize:

1. Current/latest RFPs.
2. Recent RFPs.
3. Past RFPs when needed to verify how the portal publishes RFPs.

Do not assume that a general bid, IFB, RFQ, notice, award, or other procurement record is an RFP. Record the solicitation type exactly as presented by the official source.

### Step 4 — Apply the Keyword Filter

For each candidate RFP:

1. Read the title.
2. Read the available description/scope/category.
3. Compare the content against the approved keyword list.
4. Record the matching keyword(s).
5. Keep the RFP only if the match is meaningful to the actual solicitation.

### Step 5 — Verify the RFP

Before saving:

- Confirm that the RFP is an actual official listing.
- Capture the official title.
- Capture the solicitation/RFP number when available.
- Capture posting date when available.
- Capture issue/start date when available.
- Capture end date/closing date when available.
- Capture response/due date when available.
- Capture agency/organization when available.
- Capture location when available.
- Capture the matched keyword(s).
- Capture the official source URL.
- Capture the retrieval date/time.
- Do not fabricate missing fields. Use `Not available` where appropriate.

### Step 6 — Save the Result

Save relevant findings under:

```text
Source/Scraped/
```

Use a clear filename containing the date and RFP title or identifier.

Example:

```text
Source/Scraped/202x-09-11_RFP_Title.md
```

If the same RFP has already been recorded, update the existing record rather than creating an unnecessary duplicate.

## Output Format

Each scraped RFP should contain, when available:

```markdown
# RFP Title

#YYYY-MM-DD
rfp name: RFP Title

- **RFP / Solicitation Number:** ...
- **Agency / Organization:** ...
- **Posted Date:** ...
- **Issue / Start Date:** ...
- **End / Closing Date:** ...
- **Due Date:** ...
- **Location:** ...
- **Solicitation Type:** RFP
- **Matched Keywords:** ...
- **Source URL:** ...
- **Retrieved:** ... (timezone)

## Description

...

## Relevance

Explain briefly why the RFP matched one or more approved keywords.

## Source

- Official source: ...
```

Use the official source as the primary source. Keep the original RFP title and solicitation number exactly as published whenever possible.

## Rules

### Data Accuracy

1. Never fabricate an RFP, title, solicitation number, date, deadline, agency, keyword match, or URL.
2. Every saved RFP must be supported by information actually found on the source.
3. If a field is unavailable, write `Not available` instead of guessing.
4. Prefer the official government/agency procurement portal over secondary sources.
5. If information conflicts between pages, prefer the most recent official solicitation/detail page and note the discrepancy when relevant.

### File Rules

1. Only create a file in `Source/Scraped/` when actual RFP data was found.
2. Do not create empty, null, placeholder, or "no results" files.
3. Do not create a scraped file for:
   - Login pages.
   - Blocked/inaccessible pages.
   - Empty search results.
   - Pages with no RFP content.
   - RFPs that do not meaningfully match the approved keyword filter.
4. Preserve historical scraped records unless an update is required for the same RFP.
5. Do not delete historical records merely because an RFP is no longer current.

### URL Status Rules

1. Keep `URL/url_reachable.md`, `URL/url_unreachable.md`, and `URL/url_not_applicable.md` mutually consistent.
2. A URL should appear in only the appropriate status file.
3. If a previously unreachable URL becomes accessible, move/update it to `url_reachable.md`.
4. If a reachable URL becomes inaccessible, move/update it to `url_unreachable.md`.
5. If a URL is accessible but clearly has no relevant RFP/solicitation functionality, classify it as not applicable.
6. Do not mark a URL unreachable merely because one individual RFP page is unavailable if the portal itself is accessible.
7. After visiting each URL classified as Reachable, immediately sort it into one of two files under `URL/reachable/`:
   - `easily_scrapable.md` — the RFP/bid listing (or search) loaded and was readable with no login, no CAPTCHA/bot-check, and no other access barrier, even if the listing is currently empty.
   - `blocked.md` — the URL is reachable (the server responds) but no RFP content could actually be viewed, because of a login wall, CAPTCHA/bot-check, Cloudflare/WAF block, paywall, or a broken/error page. Group entries by the specific obstacle (login required / CAPTCHA / Cloudflare block / broken page / uncertain) and note the reason next to each URL.
8. Do this sorting as you go, not as a separate pass at the end — update `easily_scrapable.md` or `blocked.md` right after each site visit, the same way `url_reachable.md`/`url_unreachable.md` are updated.
9. If a related family of URLs on the same platform/domain is skipped after confirming the pattern on one representative URL (e.g. a CAPTCHA wall confirmed once for a platform used by many agencies), record all of them under the confirmed bucket in `blocked.md` and note that only a sample was individually tested.

### Scope Rules

1. Work only with URLs provided in the project files unless explicitly instructed otherwise.
2. Do not modify `Main Database/` unless a separate instruction explicitly requires it.
3. Do not modify unrelated files.
4. Do not expand the keyword list without explicit approval.
5. Do not treat a keyword match in generic website text as an RFP match.
6. Keep the research focused on RFP/solicitation opportunities relevant to the approved keyword list.

## Credentials and Restricted Pages

- `URL/State Portals Credentials.xlsx` contains portal credential information.
- Use credentials only when the workflow explicitly permits authenticated access.
- Do not expose usernames, passwords, tokens, or other credentials in scraped Markdown files.
- If a portal requires authentication and access is unavailable, classify the access problem appropriately rather than fabricating RFP results.
- If a public RFP listing is available without authentication, prefer the public source.

## Email Findings

After the scraping and validation process is complete, email the findings that are **not null** to the configured email recipient.
```Emails
saikat.bose@ommincorp.com
akul.kaushal@ommincorp.com
```
### Email Rules

1. Send only findings containing actual, verified RFP data.
2. Do not email null, empty, placeholder, inaccessible, or no-match results.
3. Include the RFP name, date, issue/start date, end/closing date, matched keywords, key details, and source URL for each finding.
4. If there are no non-null findings, do not send an empty findings email; report that no qualifying findings were found.
5. Use the configured mail integration/recipient named `configured_mail`.
6. Do not expose credentials or authentication information in the email.
7. The email should summarize the findings clearly and link back to the official source URLs.
8. Mail must be in html form and also the finding must be in this format
```mail format
RFP Name
- Source: <source_link>
  | Rfp Title | Dtae | Issue/Start Date | End/Closing Date |
```

## Completion Checklist


Before finishing a research run, verify:

- [ ] Every URL in `URL/url_reachable.md` was considered.
- [ ] Each URL was classified correctly.
- [ ] RFP candidates were checked against the approved keyword list.
- [ ] Only meaningful keyword matches were saved.
- [ ] Every saved RFP has an official source URL.
- [ ] Important available dates, including issue/start and end/closing dates when available, were captured.
- [ ] No unsupported data was fabricated.
- [ ] Non-null findings were emailed to `configured_mail` (or no email was sent when there were no qualifying findings).
- [ ] No empty/null RFP files were created.
- [ ] Duplicate records were avoided.
- [ ] Historical records were preserved.
- [ ] URL status files remain consistent.

# Hamburg Mobility — Digital Experience & Delivery

> Independent technical portfolio case study. This page does not imply official affiliation, endorsement, or authorization by the website operator.

## Summary

This case study records work and verification activities around a modern frontend experience and its delivery pipeline. It distinguishes the implementation, CI/CD workflow, live production behavior, and quality checks instead of treating them as one result.

## Scope

- Frontend structure and responsive experience
- CI validation and deployment workflow
- Worker-delivered security headers
- Release evidence and operational verification
- Accessibility and performance checks

## Delivery model

The intended release path is:

`Branch → Pull Request → CI → Merge → Deploy → Production verification → Evidence`

Each step has a distinct proof requirement. A merged pull request alone does not establish that the intended version is live. A successful deployment job alone does not establish that all domains, headers, or user-facing behaviors are correct.

## Current evidence boundaries

The repository review identified these items for explicit tracking:

- **Security headers:** Worker code sets a Content Security Policy and several other headers. HSTS was not set in the inspected Worker code; the live edge configuration and production response headers must be verified separately before drawing a production conclusion.
- **Runtime header coverage:** The CI runtime checks referenced legacy asset paths rather than all assets currently loaded by the HTML. This is a test coverage gap, not proof of an exploitable vulnerability.
- **Dynamic HTML sinks:** Three `innerHTML` assignments were identified in client-side code. The inspected values appeared to be static in-memory route data; no exploit was confirmed by that review. This should not be described as a proven XSS vulnerability.
- **Access controls:** Effective branch protection and required review settings were not verified during the available read-only inspection.
- **Accessibility and performance:** Lighthouse, Core Web Vitals, and complete WCAG AA verification remain open until current, reproducible results are recorded.

These findings describe the scope of the review at the time it was performed. They are not a guarantee that the site is secure or free of defects.

## Visual presentation

No original production screenshot is embedded in this initial case study. Add visuals only when the source and publication rights have been reviewed.

Suggested assets:
- `../screenshots/hamburg-mobility-desktop.png`
- `../screenshots/hamburg-mobility-mobile.png`
- `../screenshots/hamburg-mobility-hero.png`
- `../screenshots/hamburg-mobility-details.png`

Use the filenames only when the corresponding real screenshot files exist. Label generated visuals as **Concept mockup — illustrative, not a live screenshot**.

## Evidence record template

For future updates, record:

| Field | Value |
|---|---|
| Repository and commit | Add exact repository and SHA |
| Verification date | Add date/time and timezone |
| Target | Exact domain or deployment target |
| Check | Command, test, or observation performed |
| Result | PASS / FAIL / OPEN |
| Evidence | Link to logs, report, or artifact |
| Limitations | What the check does not prove |

Do not publish credentials, tokens, private URLs, personal data, or internal configuration.

## Attribution and rights

This page is an independent technical description. The project name is used to identify the subject of the case study, not to suggest official affiliation. Third-party logos, photographs, copy, screenshots, and design assets must not be added without a suitable legal basis or permission.

## Status

**Portfolio draft — evidence-bounded.** This page is not a certification, security guarantee, accessibility conformance statement, or claim of official project ownership.

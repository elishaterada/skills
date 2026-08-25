---
name: pii-directory-opt-out
description: Find personal listings on people-search, contact-directory, and data-broker websites and help the user submit privacy opt-outs to reduce spam. Use for removing the user's own exposed contact details; exclude ordinary social, professional, financial, government, and other legitimate user accounts unless the user explicitly identifies a specific listing for removal.
---

# PII Directory Opt-Out

Reduce unwanted exposure of the user's personal contact information while preserving legitimate accounts and minimizing any additional disclosure.

## Scope

Target public people-search pages, reverse-phone or reverse-address directories, contact aggregators, and data-broker listings whose purpose is to expose or sell personal contact or identity data.

Do not modify or delete profiles on social networks, professional networks, messaging services, retailers, financial institutions, government services, utilities, healthcare portals, or other services where the user has an ordinary account or ongoing relationship. Treat LinkedIn, Facebook, and similar sites as out of scope by default. Ignore search-engine result pages; address the underlying directory listing instead.

Act only for the user or a person for whom the user is demonstrably authorized to act. Never use the workflow to locate, alter, or suppress another person's information without authorization.

## Workflow

1. Establish the minimum identity facts needed to distinguish the user's listings: commonly full name, current or former city/state, and one contact detail already known to the user. Do not ask for a full identity dossier up front.
2. Discover likely directory listings using targeted searches and direct site searches. Prefer official opt-out or privacy pages over third-party removal services.
3. Verify each candidate conservatively. Mark it as uncertain rather than guessing when the name is common, locations conflict, or the page combines multiple people.
4. Prepare a review list containing the site, listing URL, exposed data categories, confidence, removal route, and any information the site requests. Do not reproduce full sensitive values when partial redaction is sufficient.
5. Ask for confirmation immediately before the first batch of opt-out submissions. State which sites will be changed and flag any exceptional disclosure, login, payment, or document requirement. A confirmed batch may proceed without repeated prompts when every submission has the same disclosed risk profile; ask again when a materially different requirement appears.
6. Submit only through the site's official privacy, suppression, or opt-out mechanism. Use the minimum required fields and open verification links sent to a user-provided inbox when authorized and browser access permits.
7. Record the observable result as submitted, verification required, removed, not found, failed, or blocked. Include the date, listing URL, confirmation/reference number when available, and a suggested recheck date.
8. Revisit submitted listings after the site's stated processing period when the user requests monitoring. Verify removal from the source page; search-result caches may take longer to update.

## Safety and privacy boundaries

- Never upload government ID, a selfie, signature, Social Security number, full date of birth, payment information, or similarly high-risk data without explaining the exact requirement and obtaining fresh confirmation for that site. Prefer an alternative privacy request or stop and give the user the official link.
- Never pay a removal fee, enroll in a subscription, accept unrelated marketing terms, create an account, or delete an existing account without explicit approval.
- Do not bypass CAPTCHAs, access controls, rate limits, or bot defenses. Pause for the user when human completion is required.
- Do not send broad removal demands to unrelated businesses or use inaccurate legal claims. Select the site's generally available opt-out route unless the user provides a jurisdiction and requests a rights-based privacy request.
- Do not save raw PII, inbox contents, passwords, one-time codes, or identity documents in workspace files. Keep any tracker redacted and omit secrets from status messages.
- Treat a site's request for more personal data skeptically. If the requested data is not already displayed or reasonably necessary to match the record, stop and surface the tradeoff.
- Avoid duplicate submissions that could reset processing or trigger abuse controls.

## Browser conduct

Use an interactive browser when available so the user can handle sign-in, CAPTCHA, email codes, or sensitive form fields directly. Before pressing a final submit button, verify the domain, target identity, listing URL, and requested fields. Do not interpret navigation, search, or form preparation as authorization to submit.

If a site offers several similarly named privacy choices, prefer suppression or deletion of the public directory record while leaving unrelated accounts and services untouched.

## Output

Provide a compact, redacted tracker and a short summary of what changed, what still needs the user's action, and when removals should be checked. Clearly distinguish a submitted request from a confirmed removal.

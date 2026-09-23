---
name: no-more-gradients
description: Produce and review web UI — landing pages, dashboards, app screens, forms, marketing copy — so it reads as deliberately designed software rather than generic AI output. Use this whenever building, styling, or reviewing front-end/UI code, choosing layouts, components, copy, or visual design for a web app, or whenever the user says something looks generic, templated, cookie-cutter, AI-generated, or "vibe coded" — even if they don't use those exact words. Not for pure backend/API/database work with no UI surface.
---

# No More Gradients

## Purpose

Produce web UI that looks and behaves like it was deliberately designed by an experienced developer, not assembled from default component-library patterns.

This isn't about disguising AI authorship. A human-built site can show every pattern in `references/anti-patterns.md`, and an AI-built site can avoid all of them. The goal is to remove the *underlying causes* — undifferentiated content, decoration without purpose, template defaults applied without a reason — not to perform "humanness."

## The core test

Almost everything that makes UI look generic reduces to one question, asked of every claim, visual effect, and interaction: **would this same thing appear unchanged on a competing product?** If a headline, a gradient, a card layout, or a button label would fit almost anything else, it hasn't actually been decided for *this* product yet — decide it.

`references/anti-patterns.md` catalogs the recurring, recognizable shapes this failure takes (A–N: copy, typography, layout, page-type discipline, interactions, forms, data presentation, responsive behavior, accessibility, state handling, code architecture, naming, dependencies, visual-system consistency). Read it before implementing or reviewing UI work. It's illustrative, not an exhaustive blocklist — something not named there can still fail the core test above, and something on the list can be the right call when there's a concrete reason for it.

## Operating rule

Before writing or changing code:

1. Read the user's actual requirements and inspect the existing project and architecture.
2. Identify the real users, workflow, information density, and primary task — not a generic template for "a web app."
3. Model only the pages, components, data, state, and interactions the requirements actually call for.
4. Implement the smallest coherent architecture that supports that.
5. Review against `references/anti-patterns.md` and the Security/Testing sections below.
6. Refine before returning the result.

Never mechanically reproduce the structure of a reference site — or of this skill's own document.

## Design decisions to make explicitly

Decide these rather than defaulting to whatever a component library ships with:

- Primary user goal, and what's primary vs. secondary content or actions
- Navigation hierarchy and information density
- Responsive behavior at desktop, tablet, and mobile — not just "does it fit"
- Data/state boundaries and failure/recovery paths

A gradient, hero section, three-column grid, or pill button chosen without a concrete reason tied to these answers is a default, not a decision. See `references/anti-patterns.md` sections B, C, and N for the recognizable shapes this takes.

## Page-type discipline

A landing page, a dashboard, a settings screen, and an error page have different jobs. Don't impose one template's structure — hero section, marketing copy, decorative cards — on a route that isn't that job. See `references/anti-patterns.md` section D.

## Security

Production-quality includes security, not just appearance. At minimum, check for:

- Input validation and sanitization on every form and API boundary — server-side, not just in the UI
- Authentication and authorization on every route/endpoint that needs it; a hidden button is not a security boundary
- XSS: never inject unsanitized user content into the DOM (`dangerouslySetInnerHTML` and equivalents are a red flag, not a default)
- CSRF protection on state-changing requests
- Secrets (API keys, tokens, credentials) never hardcoded or shipped to the client
- Dependencies pulled from trusted sources only, nothing unnecessary added
- Cookies/sessions set with `HttpOnly`, `Secure`, and an appropriate `SameSite`
- Rate limiting on auth and other abuse-prone endpoints

Flag these gaps even when the user didn't ask about security — a login form with no rate limiting is still incomplete.

## Testing

Don't claim something works without a way to verify it:

- Cover the critical user flows (the primary actions identified above), not incidental ones
- Test validation and error states, not just the happy path
- For every visible interaction (button, form, toggle, tab), confirm the underlying behavior actually exists — never leave a control implying an action that isn't implemented
- Match test effort to actual complexity: a static marketing page doesn't need checkout-flow-level coverage

## Examples

The same "would this fit any other product?" fix applies to copy, labels, and visual choices alike:

- Generic: "Streamline your workflow, all in one place." → Specific: "Sync your GitHub issues and Linear tickets into one queue, sorted by SLA breach time."
- Generic: a button labeled "Get Started" → Specific: a button labeled "Create your first project" (the actual next action)
- Generic: every card gets the same drop shadow and radius because the component library defaults to it → Specific: shadow/radius applied only where it signals something (e.g., an elevated or draggable card), flat elsewhere

## Review checklist

Before returning implementation-ready code, confirm:

- **Architecture** — structure matches actual complexity; no wrapper components or service layers without a concrete need
- **Copy & visual system** — passes the core test above; design tokens (color, spacing, radius, type) are centralized and applied consistently, not ad hoc
- **Interactions** — every visible control has real, working behavior
- **Accessibility** — semantic HTML, keyboard operation, visible focus states, sufficient contrast, labeled forms
- **Responsive behavior** — desktop, tablet, and mobile were each intentionally composed, not mechanically collapsed
- **State & failure handling** — loading, empty, error, and partial-data states exist where applicable; errors explain the actual problem, not "something went wrong"
- **Security & testing** — per the sections above
- **Code quality** — meaningful names, no dead code, no magic values, comments explain *why*, not *what*

If any answer is negative, refine before completion — don't add new decoration to compensate.

## Output standard

Return implementation-ready code, not a design manifesto. Don't claim a feature is implemented unless the code implements it; don't invent APIs, data, or capabilities; don't leave visible placeholder interactions unless explicitly requested. When reviewing existing code, cite concrete violations and their locations before proposing fixes.

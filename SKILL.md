---
name: production-quality-web-code
description: Generate and modify production-quality web applications using deliberate architecture, domain-specific UX, restrained visual design, accessibility, responsive behavior, predictable state, realistic interaction states, performance, security, and maintainability. Use this skill whenever creating, modifying, reviewing, or refactoring a web application.
---

# Production-Quality Web Code

## Purpose

Produce web applications that look and behave like deliberately designed software built by an experienced developer.

Do not optimize for appearing "human" or for defeating AI detectors. Eliminate the engineering and design characteristics that make generated work generic, repetitive, careless, artificial, or template-driven.

The attached/reference material is a quality-control source, not a literal checklist to copy. It identifies clusters of signals commonly associated with low-quality or heavily AI-assisted websites. The source explicitly states that none of those signals proves AI authorship; human-designed sites can contain them and AI-generated sites can avoid them. Treat clusters of independent signals as quality warnings, not authorship evidence.

## Operating Rule

Before writing or changing code:

1. Read the user requirements.
2. Inspect the existing project and architecture.
3. Inspect the supplied reference material when available.
4. Identify the application's actual users, workflow, information density, and primary task.
5. Model the required pages, components, data, state, interactions, validation, API boundaries, and responsive behavior.
6. Implement the smallest coherent architecture that supports the real requirements.
7. Review the result against the anti-vibe-code quality model below.
8. Refine before returning the implementation.

Never mechanically reproduce the structure of a reference website or this document.

---

# 1. Quality Model Derived From the Reference

The reference contains 1,000 numbered indicators. Most of the latter indicators deliberately repeat the same core patterns in different contexts: landing page, pricing, dashboard, and settings. Consolidate those repetitions into these review dimensions.

## A. Domain-specific content

Reject:

- Generic hero copy that says little about the actual product.
- SaaS filler such as "seamless", "powerful", "effortless", "next-generation", "cutting-edge", "transform", "unlock", "elevate", "streamline", "empower", "revolutionize", "innovative", "intuitive", "smart", "intelligent", "robust", "scalable", "secure", "modern", "simple", "flexible", "reliable", "optimized", "frictionless", "personalized", or "built for the future" when those words are not backed by concrete behavior or evidence.
- Claims that could describe almost any SaaS product.
- Feature descriptions dominated by adjectives instead of specifications.
- Polished prose with little domain information.
- Repetitive marketing constructions such as:
  - "everything you need to..."
  - "all in one place"
  - "at scale"
  - "in today's fast-paced world"
  - "say goodbye to..."
  - "meet the future of..."
  - "take X to the next level"
  - repeated "from X to Y"
  - repeated "whether X or Y"
  - repeated "not just X, but Y"
  - repeated "more than X"
  - repeated "designed for X, built for Y"

Use terminology that belongs to the actual product and workflow. If real copy is unavailable, use realistic neutral domain language rather than invented marketing claims.

## B. Typography and information hierarchy

Avoid:

- Uniform Title Case when sentence case is more natural.
- Headings with suspiciously similar lengths or grammar.
- Repeated abstract nouns where concrete actions or domain nouns would be clearer.
- Repeated "Discover", "Unlock", "Transform", "Power", "Smart", "Simple", "Better", "Future", "Seamless", or "Intelligent".
- Rhetorical questions that serve no purpose.
- Repeated em-dash or colon-based heading constructions.
- Headings optimized for marketing rather than navigation.
- Headings that introduce concepts not represented in the UI.
- Unexplained acronyms.
- Excessive adjectives.
- Excessive direct-address language such as repeated "you" or "your".
- Promises of speed, clarity, control, visibility, growth, or efficiency without corresponding evidence or controls.
- Motivational/pitch-deck language in functional or technical screens.

Define a deliberate typography system:

- Font family
- Body size
- Heading scale
- Line heights
- Weight scale
- Text and muted colors
- Letter spacing only where useful

Use hierarchy to improve scanning, not to imitate a modern SaaS aesthetic.

## C. Layout and visual composition

Avoid template symmetry and decoration without purpose:

- Every section centered.
- Predictable alternating text/image sections.
- Identical section spacing regardless of content.
- Identical card heights for unrelated content.
- Three-column cards used by default.
- Excessive empty space around short copy.
- Suspiciously uniform content widths across unrelated screens.
- Every block wrapped in a container.
- Identical rounded containers everywhere.
- Identical corner radii everywhere.
- Every button rendered as a pill.
- Identical shadows on every card.
- Identical borders on every section.
- Long pages composed of repeated centered blocks.
- Oversized text carrying the entire visual hierarchy.
- Repeated decorative gradients.
- Background blobs that merely fill empty space.
- Floating cards without functional purpose.
- Repeated circles/blobs at mathematically similar positions.

Layout must follow content and workflow. Asymmetry is valid when it improves information hierarchy.

## D. Page-type discipline

Do not impose a landing-page template on every route.

Avoid:

- Hero sections on transactional pages.
- Marketing introductions before functional content.
- Dashboard pages containing marketing-style heroes.
- Settings pages represented as decorative cards instead of compact controls.
- Forms presented as oversized marketing cards.
- Tables surrounded by unnecessary padding.
- Filters scattered across unrelated rows.
- Oversized modal layouts for simple actions.
- Large illustrations for trivial empty states.
- Error pages containing motivational copy.
- Loading screens containing slogans.
- Generic footers generated from an imaginary sitemap.

Use the page type to determine density, hierarchy, navigation, and interaction patterns.

## E. Interaction and content semantics

Reject fake or ambiguous interactions:

- Vague button labels such as "Get Started" when the real action is known.
- Primary and secondary actions with indistinguishable visual priority.
- Icons where text is clearer.
- Icon-plus-tooltip for every action.
- Tooltips explaining labels that should already be understandable.
- Duplicate links and buttons inside the same card.
- Multiple competing calls to action.
- Generic dropdown placeholder values.
- Marketing-style checkbox labels.
- Toggle labels that describe both states positively.
- Copy/share/bookmark controls without a meaningful use case.
- Breadcrumbs where hierarchy is already obvious.
- Tabs for content that fits on one screen.
- Generic "Overview / Details / Activity" tabs reused without domain justification.
- Accordions hiding short or frequently needed content.
- Hover effects on non-interactive table rows.
- Buttons or controls that visually imply behavior that is not implemented.

Every visible interaction must have an intentional, working behavior.

## F. Forms

Forms are production interfaces, not decorative compositions.

Use:

- Persistent labels.
- Correct input types.
- Useful defaults.
- Validation tied to actual rules.
- Specific error messages.
- Clear disabled and submitting states.
- Keyboard operation.
- Appropriate focus behavior.
- Clear success feedback.
- Explicit consequences for destructive operations.

Avoid:

- Placeholder text as the only label.
- Artificially conversational validation.
- Fake sample data presented as realistic input guidance.
- Ambiguous natural-language date placeholders.
- Long sentence-like button labels.
- Inconsistent capitalization.
- Generic confirmation text that does not explain consequences.

## G. Data presentation

For lists, tables, metrics, charts, search, filters, sorting, and pagination:

- Match density to the domain.
- Define search scope.
- Use filters that belong to the dataset.
- Use terminology consistently.
- Expose meaningful sort options.
- Provide totals when they matter.
- Preserve access to truncated data.
- Define metric denominators when showing percentages.
- Use chart precision appropriate to the data.
- Do not add legends when a single or tiny number of series makes them redundant.
- Do not add metric icons merely because a card has space.
- Use hover states only when interaction exists.
- Do not automatically create skeleton and empty states for tiny local datasets.

Do not manufacture dashboard complexity.

## H. Responsive behavior

Responsive design is structural, not a final CSS patch.

Design intentionally for:

- Desktop
- Tablet
- Mobile

Avoid:

- Desktop layouts merely stacked vertically.
- Mechanical grid collapse.
- Sidebars simply becoming long blocks below content.
- Navigation wrapping awkwardly at intermediate widths.
- All buttons becoming full-width without need.
- Cards becoming excessively tall.
- Desktop spacing merely being reduced.
- Desktop image aspect ratios being retained when unsuitable.
- Decorative elements overlapping content at breakpoints.

At each breakpoint, reconsider information priority, navigation, controls, tables, forms, dialogs, and content order.

## I. Accessibility

Use semantic HTML first.

Required where applicable:

- Correct landmarks.
- Correct heading hierarchy.
- Real buttons for actions.
- Real links for navigation.
- Persistent labels.
- Keyboard navigation.
- Visible focus states.
- Appropriate target sizes.
- Sufficient contrast.
- Meaningful alternative text.
- Accessible validation and error messaging.
- ARIA only when native semantics are insufficient.

Do not use ARIA to compensate for incorrect HTML.

## J. State and failure behavior

Separate:

- UI state
- Application state
- Derived state
- Persistent state
- Server/API state

Rules:

- Do not store derivable values as independent state.
- Do not duplicate a source of truth.
- Keep local concerns local.
- Do not introduce global state merely for convenience.
- Do not add effects where derivation or event handling is sufficient.

Handle applicable states:

- Loading
- Empty
- Success
- Error
- Partial data
- Invalid input
- Network failure
- Authentication failure
- Authorization failure
- Server failure
- Missing data
- Invalid application state

Errors must explain the actual problem and the available recovery path. Avoid universal "Something went wrong" messages.

## K. Code architecture

Use components and modules for real concepts, not arbitrary chunks of markup.

Good abstraction:

- Removes meaningful duplication.
- Encapsulates a real domain or UI concept.
- Establishes reusable behavior.
- Makes the code easier to understand or change.

Bad abstraction:

- Exists only because a block of JSX/HTML was extracted.
- Adds a wrapper with no semantic responsibility.
- Creates generic utilities for one call site.
- Creates a service layer without an architectural need.
- Introduces hooks solely to hide straightforward logic.

Avoid both extremes:

### Fake complexity
Do not add:

- Excessive folders.
- Large configuration systems.
- Unnecessary design systems.
- State-management libraries without a state-management problem.
- Service/repository layers without meaningful boundaries.
- Custom hooks for trivial logic.
- Giant utility modules.
- Large dependency sets.

### Fake simplicity
Do not put a genuinely complex application into:

- One enormous component.
- One giant JavaScript file.
- One giant stylesheet.
- One HTML file containing unrelated concerns.

Architecture must follow actual complexity.

## L. Naming, comments, and maintainability

Use meaningful names based on domain concepts.

Avoid:

- Generic names that hide intent.
- Inconsistent terminology for the same concept.
- Dead code.
- Unused imports.
- Unused props.
- Magic values without explanation or configuration.
- Deeply nested conditionals.
- Generated boilerplate that serves no purpose.
- Comments that restate the code.

Comments should explain why something exists when the reason is not apparent from the implementation.

## M. Dependencies and performance

Choose the smallest implementation that satisfies the requirements.

Avoid:

- Libraries for trivial functionality.
- Large dependencies for small features.
- Unnecessary client-side JavaScript.
- Unnecessary re-renders.
- Unnecessary effects.
- Repeated network requests.
- Unnecessary animations.
- Duplicate data fetching.
- Heavy abstractions around simple APIs.

Do not optimize prematurely, but do remove obvious unnecessary work.

## N. Visual-system consistency

Treat the application as one product.

Centralize design tokens for:

- Primary color
- Accent/secondary color
- Backgrounds
- Surfaces
- Borders
- Text
- Muted text
- Success
- Warning
- Error
- Spacing
- Radius
- Control heights
- Typography

Do not introduce ad-hoc values throughout components.

Consistency does not mean every element must look identical. Shared tokens should establish a visual language while hierarchy determines variation.

---

# 2. Design Rules

Before implementation, explicitly determine:

1. Primary user goal.
2. Primary content.
3. Secondary content.
4. Primary actions.
5. Supporting actions.
6. Navigation hierarchy.
7. Information density.
8. Responsive behavior.
9. Data and state boundaries.
10. Failure and recovery paths.

Then choose the UI structure.

Do not automatically use:

- Gradients.
- Glassmorphism.
- Huge rounded corners.
- Floating cards.
- Heavy shadows.
- Decorative blobs.
- Excessive animations.
- Oversized headings.
- Generic dashboard layouts.
- Hero sections.
- Pills/badges everywhere.
- Three-column card grids.
- Excessive whitespace.
- Random accent colors.

Any such pattern requires a concrete product or interaction reason.

---

# 3. Implementation Workflow

## Phase 1 — Understand

Read:

- User requirements.
- Existing code.
- Existing architecture.
- Existing dependencies.
- Supplied reference material.
- Existing domain terminology.

Do not start by generating a page template.

## Phase 2 — Model

Define only what the application actually needs:

- Routes/pages.
- Components.
- Data structures.
- State ownership.
- User flows.
- API boundaries.
- Validation.
- Error states.
- Responsive transformations.
- Accessibility requirements.

Prefer explicit decisions over speculative infrastructure.

## Phase 3 — Implement

Build the smallest coherent implementation.

Rules:

- Reuse working infrastructure.
- Preserve established conventions unless they create a concrete problem.
- Do not rewrite unrelated code.
- Keep responsibilities clear.
- Use domain terminology.
- Make all visible interactions functional.
- Keep styling decisions consistent with the design tokens.

## Phase 4 — Review

Review the implementation as a pull request from an experienced developer.

Look specifically for:

- Generic copy.
- Template-derived sections.
- Decorative effects without purpose.
- Repetition.
- Arbitrary spacing.
- Inconsistent typography.
- Inconsistent controls.
- Fake interactions.
- Unnecessary state.
- Unnecessary effects.
- Unnecessary abstractions.
- Dead code.
- Magic values.
- Accessibility failures.
- Mobile failures.
- Weak error states.
- Unnecessary dependencies.
- Incorrect page density.

## Phase 5 — Refine

Fix identified problems rather than adding new visual decoration.

Prefer removing complexity over disguising it.

## Phase 6 — Verify

Before completion, verify:

### Architecture
- Structure matches actual application complexity.
- Responsibilities are separated appropriately.
- Abstractions have concrete value.

### UI
- Visual system is coherent.
- Effects are justified.
- Layout follows content and workflow.
- Page types are treated differently when their jobs differ.

### UX
- Interactions behave realistically.
- Primary actions are obvious.
- Loading, empty, error, success, and partial states are handled where applicable.

### Code
- Names are meaningful.
- Duplication is controlled.
- Dead code is absent.
- Dependencies are justified.
- Comments explain non-obvious reasons rather than syntax.

### Accessibility
- Semantic HTML is correct.
- Keyboard interaction works.
- Focus is visible.
- Forms are labeled.
- Errors are accessible.
- Contrast is sufficient.

### Responsive behavior
- Desktop, tablet, and mobile layouts are intentionally composed.
- Content priority changes where necessary.
- Tables, navigation, forms, and dialogs remain usable.

### Maintainability
- Another experienced developer can understand the implementation quickly.
- Major implementation decisions have concrete reasons.

If a review answer is negative, refine the implementation before completion.

---

# 4. Special Review Heuristics

## Detect repeated structure

Do not mistake repeated domain concepts for bad repetition.

Bad repetition:
- Five unrelated sections all use identical cards because a template was convenient.

Good repetition:
- Five records use the same row component because they represent the same domain entity.

## Detect decorative intent

Ask of every visual effect:

- Does it communicate hierarchy?
- Does it identify state?
- Does it improve navigation?
- Does it support the brand or domain?
- Does it improve interaction feedback?

If none applies, remove it.

## Detect generated-looking copy

Replace generic claims with:

- Actual object names.
- Actual workflow steps.
- Actual limits.
- Actual statuses.
- Actual metrics.
- Actual consequences.
- Actual user actions.

## Detect fake functionality

For every button, link, toggle, tab, dropdown, modal, search field, filter, sort control, or navigation item:

- Identify the resulting state change.
- Identify the underlying action.
- Ensure the UI communicates failure when the action cannot complete.

Remove controls that have no real purpose.

## Detect over-engineering

Before adding a library, abstraction, hook, state store, service, configuration layer, or utility:

- Identify the concrete problem it solves.
- Confirm the problem cannot be solved more simply.
- Confirm the added boundary improves maintainability.

If not, do not add it.

## Detect under-engineering

If unrelated responsibilities are mixed together and the application is becoming difficult to change, separate them according to actual domain or technical boundaries.

---

# 5. Output Standard

When generating code, return implementation-ready code rather than a design manifesto.

When modifying existing code:

- Preserve working behavior unless the requirement changes it.
- Explain meaningful architectural changes briefly.
- Do not claim a feature is implemented unless the code actually implements it.
- Do not invent APIs, data, integrations, or capabilities.
- Do not leave visible placeholder interactions unless explicitly requested.

When reviewing code, identify concrete violations and their locations, then provide corrected implementation where appropriate.

# Core Rule

Do not attempt to make code "look human."

Write code that is genuinely well-designed, appropriately architected, domain-specific, maintainable, accessible, responsive, performant, secure, and technically deliberate.

The desired result should naturally avoid the common characteristics of generic or low-quality AI-generated implementations because those characteristics have been removed at the engineering level.

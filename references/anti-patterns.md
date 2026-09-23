# Anti-Pattern Catalog

This catalogs the recurring, recognizable shapes that generic, template-driven UI takes. It exists to make the core test in `SKILL.md` — "would this same thing appear unchanged on a competing product?" — concrete and fast to check.

It's illustrative, not exhaustive: something not named here can still fail the core test, and something named here can be the right call when there's a concrete product or interaction reason for it. Treat clusters of these signals as a quality warning, not proof of AI authorship — human-built sites show plenty of them too.

## Contents

A. Copy · B. Typography & hierarchy · C. Layout & composition · D. Page-type discipline · E. Interactions · F. Forms · G. Data presentation · H. Responsive behavior · I. Accessibility · J. State & failure behavior · K. Code architecture · L. Naming & maintainability · M. Dependencies & performance · N. Visual-system consistency

---

## A. Copy

Generic copy is the clearest symptom of the core test failing: language chosen because it sounds like software, not because it describes this product.

Reject:
- Claims that could describe almost any product in the category
- Feature descriptions dominated by adjectives instead of specifications
- Filler such as "seamless", "powerful", "effortless", "next-generation", "cutting-edge", "transform", "unlock", "elevate", "streamline", "empower", "revolutionize", "intuitive", "robust", "scalable", "frictionless", "personalized" — not as a banned-word list to route around with synonyms, but because none of them survive the core test unless backed by a concrete behavior right next to them
- Constructions that show up regardless of product: "everything you need to...", "all in one place", "at scale", "in today's fast-paced world", "say goodbye to...", repeated "from X to Y" / "whether X or Y" / "not just X, but Y" / "designed for X, built for Y"

Use terminology from the actual product and workflow. If real copy isn't available yet, use neutral, concrete domain language rather than inventing marketing claims.

## B. Typography & information hierarchy

Why it matters: hierarchy exists to help someone scan and find what they need, not to imitate a modern SaaS aesthetic. Decoration applied to typography usually signals the latter.

Avoid:
- Uniform Title Case where sentence case reads more naturally
- Headings of suspiciously similar length or grammatical shape
- Repeated "Discover", "Unlock", "Transform", "Power", "Seamless" as heading verbs
- Rhetorical questions that serve no navigational purpose
- Repeated em-dash or colon heading constructions
- Headings optimized for marketing rhythm rather than findability
- Headings that introduce concepts not represented anywhere in the actual UI
- Unexplained acronyms, excessive adjectives, or repeated direct address ("you"/"your")
- Promises of speed, clarity, or growth with no corresponding control or evidence on screen

Define an explicit system instead: font family, body size, heading scale, line heights, weight scale, text/muted colors, letter spacing only where it earns its keep.

## C. Layout & visual composition

Why it matters: symmetry and decoration are cheap defaults. Unless they're doing a job — signaling state, grouping related content, guiding the eye to the primary action — they're filler, and filler is the fastest way to look templated.

Avoid without a reason:
- Every section centered; predictable alternating text/image blocks
- Identical spacing or card heights regardless of what the content actually needs
- Three-column cards used by default
- Every block wrapped in an identical rounded container with an identical shadow
- Every button rendered as a pill
- Gradients, glassmorphism, decorative blobs, or floating cards with no functional purpose
- Oversized text carrying the entire visual hierarchy instead of a real type scale

Layout follows content and workflow. Asymmetry is correct when it improves the hierarchy; symmetry is correct when the content actually is uniform (see K's note on "bad repetition vs. good repetition" — applies here too: five records using the same row component is not the same failure as five unrelated sections forced into the same card).

## D. Page-type discipline

Why it matters: a landing page's job is persuasion; a dashboard's job is fast orientation; a settings page's job is compact control. Applying one template's structure to all of them is a tell that the page type was never actually considered.

Avoid:
- Hero sections or marketing introductions on transactional or functional pages
- Settings represented as decorative cards instead of compact controls
- Forms presented as oversized marketing cards
- Tables buried in unnecessary padding, or filters scattered across unrelated rows
- Oversized modals for simple actions; large illustrations for trivial empty states
- Motivational copy on error pages; slogans on loading screens
- Generic footers built from an imaginary sitemap the product doesn't have

## E. Interactions

Why it matters: every control implies a promise. A control with no real behavior, or an ambiguous one, breaks that promise the moment someone clicks it.

Avoid:
- Vague labels ("Get Started") when the real next action is known and could be named
- Primary and secondary actions with indistinguishable visual weight
- Icon-only controls where text would be clearer; tooltip explaining a label that should already be clear on its own
- Duplicate links/buttons doing the same thing inside one card; multiple competing calls to action
- Toggle labels that describe both states positively (ambiguous about which state is "on")
- Breadcrumbs where hierarchy is already obvious; tabs for content that fits on one screen
- Generic "Overview / Details / Activity" tabs with no domain justification for that split
- Accordions hiding content people need frequently or that's already short
- Any control that visually implies behavior that isn't implemented

## F. Forms

Forms are production interfaces people have to get through, not decorative compositions.

Use: persistent labels, correct input types, useful defaults, validation tied to real rules, specific error messages, clear disabled/submitting states, keyboard operability, sensible focus behavior, clear success feedback, explicit consequences before destructive actions.

Avoid: placeholder text standing in as the only label, artificially conversational validation copy, fake sample data presented as realistic guidance, ambiguous natural-language date placeholders, long sentence-length button labels, inconsistent capitalization, generic confirmation text that doesn't say what will actually happen.

## G. Data presentation

For lists, tables, metrics, charts, search, filters, sorting, pagination — match density to the domain rather than to a dashboard template.

- Define search scope and use filters that actually belong to the dataset
- Use terminology consistently; expose sort options that are meaningful for this data
- Provide totals when they matter; preserve access to truncated data rather than silently dropping it
- Define the denominator whenever showing a percentage
- Skip legends for a single series; skip metric icons added only because a card had empty space
- Don't manufacture skeleton/empty states for a tiny local dataset that doesn't need them

## H. Responsive behavior

Why it matters: responsive design is structural — a decision about what matters at each size — not a CSS pass applied after the desktop layout is done.

Avoid: desktop layouts merely stacked vertically; mechanical grid collapse; sidebars becoming long blocks below content; navigation wrapping awkwardly at in-between widths; every button going full-width regardless of need; desktop spacing just uniformly shrunk; desktop image aspect ratios kept when they no longer suit the space; decorative elements overlapping content at a breakpoint.

At each breakpoint, reconsider information priority, navigation, controls, tables, forms, and dialogs — not just whether things fit.

## I. Accessibility

Semantic HTML first; ARIA only where native semantics genuinely fall short of what's needed — never as a patch over incorrect HTML.

Required where applicable: correct landmarks and heading hierarchy, real buttons for actions and real links for navigation, persistent labels, full keyboard navigation, visible focus states, adequate target sizes, sufficient contrast, meaningful alt text, accessible validation and error messaging.

## J. State & failure behavior

Separate UI state, application state, derived state, persistent state, and server/API state — collapsing them is what causes bugs where the UI shows something that doesn't match reality.

- Don't store a value as independent state if it's derivable from something else
- Don't duplicate a source of truth; keep local concerns local
- Don't reach for global state or an effect when a plain derivation or event handler would do

Handle the states that actually apply: loading, empty, success, error, partial data, invalid input, network failure, auth failure, server failure, missing data, invalid application state. Errors should explain the actual problem and the available recovery path — "something went wrong" is never sufficient on its own.

## K. Code architecture

Good abstraction removes real duplication, encapsulates a real domain or UI concept, and makes the code easier to change. Bad abstraction exists only because a block of markup happened to get extracted — a wrapper with no responsibility, a utility with exactly one call site, a service layer with no architectural need behind it.

Avoid both directions:
- **Fake complexity**: extra folders, config systems, design systems, state libraries, or service layers with no concrete problem behind them
- **Fake simplicity**: a genuinely complex app crammed into one component, one file, or one stylesheet

Bad repetition is five unrelated sections forced into the same card because a template was convenient. Good repetition is five records sharing one row component because they're the same domain entity — don't mistake the second for the first.

## L. Naming & maintainability

Use names based on domain concepts, applied consistently. Avoid generic names that hide intent, inconsistent terms for the same concept, dead code, unused imports/props, magic values with no explanation, deeply nested conditionals, boilerplate that serves no purpose, and comments that just restate the code next to them. Comments should explain *why* something exists when that reason isn't obvious from reading the implementation.

## M. Dependencies & performance

Choose the smallest implementation that actually satisfies the requirement. Avoid libraries pulled in for trivial functionality, large dependencies for small features, unnecessary client-side JS, unnecessary re-renders or effects, repeated or duplicate network/data requests, unnecessary animation, and heavy abstraction wrapped around an API that was already simple. Don't optimize prematurely — but do remove obviously unnecessary work.

## N. Visual-system consistency

Treat the app as one product: centralize tokens for primary/accent color, backgrounds, surfaces, borders, text/muted text, success/warning/error, spacing, radius, control heights, and typography, instead of setting ad hoc values per component.

Consistency doesn't mean every element looks identical — shared tokens establish the visual language; hierarchy is what creates deliberate variation on top of it.

# No More Gradients

That is considerably stronger positioning than **"a skill that removes gradients."**

### Make vibe-coded websites look intentional, specific, and designed — not generic AI UI.

**No More Gradients** is an AI coding skill for fixing **generic vibe-coded websites, AI-generated websites, and AI-generated UI**.

It helps Claude and other coding agents identify and remove the patterns that make AI-built websites look interchangeable: generic copy, default typography, repetitive card layouts, unnecessary gradients, template-like sections, meaningless decoration, weak interactions, inconsistent responsive behavior, and unfinished UI states.

The goal is not to make AI-generated websites look "less AI."

The goal is to make them look **deliberately designed for the actual product**.

---

## Usage

[Download SKILL.md](./SKILL.md)
Add the skill to your AI coding agent's skills directory and use it when creating, modifying, reviewing, or refactoring web applications.

---

## Why this exists

AI coding tools make it extremely easy to generate a working website.

The problem is that "working" does not necessarily mean **specific, coherent, or well-designed**.

Give an AI coding agent a vague request such as:

> Build a modern SaaS landing page.

It can produce a technically valid website in seconds.

But the result may contain:

* A generic hero section
* Purple or blue gradients
* Repeated rounded cards
* Inter or another default typeface everywhere
* Generic marketing copy
* "Get Started" buttons with no specific purpose
* Decorative icons with no functional meaning
* Identical layouts across unrelated products
* Excessive shadows and borders
* Generic dashboard patterns
* Placeholder testimonials
* Unnecessary animations
* Inconsistent mobile behavior
* Missing loading, empty, and error states
* UI controls that do not actually work

These are not isolated visual problems.

They are symptoms of **undecided design and product decisions**.

No More Gradients gives your coding agent a framework for making those decisions before it starts blindly applying defaults.

---

## What it does

The skill reviews and improves web UI across the entire interface, not just the color palette.

### Visual design

* Typography hierarchy
* Color systems
* Spacing
* Border radius
* Shadows
* Layout composition
* Visual hierarchy
* Responsive design
* Motion and interaction patterns
* Design-token consistency

### Content and copy

* Generic headlines
* Generic marketing language
* Empty value propositions
* Generic button labels
* Placeholder content
* Product-specific terminology
* Copy that could belong to any competing product

### Layout and page structure

* Hero sections
* Feature grids
* Dashboards
* Forms
* Settings screens
* Landing pages
* Error pages
* Empty states
* Data-heavy interfaces

The skill treats different page types as different products with different jobs instead of forcing every page into the same template.

### Interaction quality

Every visible interaction should have a real purpose and real behavior.

The skill checks:

* Buttons
* Forms
* Toggles
* Tabs
* Navigation
* Modals
* Loading states
* Empty states
* Error states
* Partial-data states
* Recovery paths

### Accessibility

The review includes:

* Semantic HTML
* Keyboard interaction
* Visible focus states
* Form labels
* Color contrast
* Accessible interaction patterns

### Responsive behavior

Responsive design is treated as a composition problem rather than simply collapsing desktop layouts into smaller screens.

The skill considers:

* Desktop
* Tablet
* Mobile
* Navigation changes
* Content priority
* Component behavior
* Information density
* Touch interaction

### Code quality

The skill also reviews the implementation behind the UI:

* Architecture proportional to actual complexity
* Meaningful names
* No unnecessary abstraction
* No dead code
* No magic values
* Centralized design tokens
* Comments that explain why
* No unnecessary dependencies

### Security and testing

A polished interface is not enough.

The skill also checks for common production gaps such as:

* Missing input validation
* Missing authorization
* XSS risks
* CSRF protection
* Hardcoded secrets
* Unsafe dependencies
* Insecure cookies
* Missing rate limiting
* Untested critical flows
* Broken visible controls

---

## The core rule

Every important design decision should pass this test:

> **Would this same thing appear unchanged on a competing product?**

If the answer is yes, the decision probably has not been made specifically for the product yet.

For example:

**Generic**

> "Streamline your workflow, all in one place."

**Specific**

> "Sync your GitHub issues and Linear tickets into one queue, sorted by SLA breach time."

**Generic**

> Get Started

**Specific**

> Create your first project

**Generic**

Every card uses the same radius, border, and shadow.

**Specific**

Elevation is used only where it communicates hierarchy, such as draggable or elevated content.

The same principle applies to:

* Copy
* Typography
* Color
* Layout
* Components
* Interactions
* Data presentation
* Responsive behavior

---

## What this is not

### Not an "anti-AI" tool

This skill does not try to disguise AI-generated code.

AI-generated software can be excellent.

The problem is **generic output caused by unspecified decisions and default patterns**.

### Not a blacklist of ugly UI patterns

The skill does not simply say:

* Never use gradients
* Never use cards
* Never use rounded corners
* Never use animations
* Never use a specific font

Any of these can be appropriate when there is a concrete product reason.

The problem is using them automatically.

### Not a design template

The skill does not replace one generic template with another.

It requires the implementation to be derived from:

* The actual product
* The actual users
* The actual workflow
* The actual information
* The actual requirements

---

## Before and after

### Before

> Build a modern website for my productivity app.

Typical result:

```text
Hero
  ↓
Three feature cards
  ↓
Three testimonials
  ↓
Pricing cards
  ↓
CTA
```

With:

```text
Purple gradient
Rounded cards
Generic sans-serif
"Transform your productivity"
"Get Started"
```

### After

The agent first determines:

```text
Who is using the product?
What are they trying to accomplish?
What information matters most?
What makes this product different?
What should the primary action be?
What should the interface prioritize?
What visual decisions support the product?
What states can the user encounter?
```

The resulting interface is designed around those answers rather than around a generic SaaS template.

---

## Use it with AI coding tools

The skill is designed for workflows involving AI coding agents and frontend development.

It is particularly useful with:

* Claude Code
* Cursor
* GitHub Copilot
* Codex
* Lovable
* Bolt
* v0
* Replit
* Other AI coding agents

The skill can be used when:

* Building a website from scratch
* Improving an existing AI-generated website
* Reviewing frontend code
* Fixing a generic landing page
* Improving a dashboard
* Refining a web application
* Reviewing a vibe-coded project
* Removing repetitive AI-generated UI patterns

---

## How to use

Install the skill in your AI coding environment and invoke it when building or reviewing web UI.

The skill should be used **before implementation**, not only after the website already looks generic.

A typical workflow is:

```text
Requirements
    ↓
Understand users and workflow
    ↓
Identify product-specific decisions
    ↓
Define UI structure
    ↓
Implement
    ↓
Review against anti-patterns
    ↓
Test interactions and states
    ↓
Refine
```

---

## Skill structure

```text
no-more-gradients/
├── SKILL.md
└── references/
    └── anti-patterns.md
```

`SKILL.md` contains the operating rules.

`references/anti-patterns.md` contains the detailed catalog of recurring generic UI patterns.

The anti-pattern catalog covers areas including:

* Copy
* Typography
* Layout
* Page types
* Interactions
* Forms
* Data presentation
* Responsive behavior
* Accessibility
* State handling
* Code architecture
* Naming
* Dependencies
* Visual-system consistency

---

## The design principle

> **Don't optimize for looking different. Optimize for having made real decisions.**

A website does not become distinctive because it uses unusual colors or removes every gradient.

It becomes distinctive when its:

* Content reflects the actual product
* Layout reflects the actual workflow
* Typography supports the information hierarchy
* Interactions have a reason
* Components communicate meaningful states
* Responsive behavior reflects user priorities
* Visual system is internally consistent
* Code supports the actual complexity of the product

---

## Review checklist

Before considering a UI implementation complete:

* [ ] Does the structure match the actual product?
* [ ] Is the primary user goal obvious?
* [ ] Is the primary action specific?
* [ ] Could the copy belong to another product?
* [ ] Could the layout belong to another product?
* [ ] Are visual effects serving a purpose?
* [ ] Are design tokens consistent?
* [ ] Does every visible control actually work?
* [ ] Are loading, empty, and error states handled?
* [ ] Does the interface work intentionally on mobile?
* [ ] Is the HTML semantic and accessible?
* [ ] Are forms properly labeled and validated?
* [ ] Are security boundaries implemented correctly?
* [ ] Is the architecture proportional to the application?
* [ ] Is there unnecessary code or abstraction?
* [ ] Has the implementation been tested against real user flows?

If the answer to an important question is no, fix the underlying problem instead of adding more decoration.

---

## Who is this for?

This skill is useful for:

* Developers using AI coding agents
* Vibe coders
* Indie hackers
* Startup founders
* Product engineers
* Frontend developers
* Designers working with AI coding tools
* Developers building websites with Claude Code
* Developers building UI with Cursor
* Developers using Lovable, Bolt, v0, or similar AI tools

Especially if you have ever looked at an AI-generated website and thought:

> "It works, but it looks generic."

---

## Keywords

`vibe coding` · `vibe coded website` · `AI-generated website` · `AI-generated UI` · `AI slop` · `AI slop UI` · `generic website` · `generic AI website` · `AI web design` · `AI frontend` · `Claude Code` · `Cursor` · `Lovable` · `Bolt` · `v0` · `frontend design` · `web UI` · `UI design` · `frontend development`

````

**Topics:**

```text
vibe-coding
vibe-coded-website
ai-generated-ui
ai-generated-websites
ai-slop
ai-slop-ui
frontend-design
frontend-development
web-design
ui-design
claude-code
cursor
lovable
bolt
v0
````

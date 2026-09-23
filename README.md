# No More Gradients

That is considerably stronger positioning than **"a skill that removes gradients."**

### Make vibe-coded websites look intentional, specific, and designed.

**No More Gradients** is an skill for fixing **generic vibe-coded websites, AI-generated websites, and AI-generated UI**.

It helps Claude and other coding agents identify and remove the patterns that make AI-built websites look interchangeable: generic copy, default typography, repetitive card layouts, unnecessary gradients, template-like sections, meaningless decoration, weak interactions, inconsistent responsive behavior, and unfinished UI states.

## Usage

[Download SKILL.md](./SKILL.md)
Add the skill to your AI coding agent's skills directory and use it when creating, modifying, reviewing, or refactoring web applications.

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

### Interaction quality

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

### Code quality

* Architecture proportional to actual complexity
* Meaningful names
* No unnecessary abstraction
* No dead code
* No magic values
* Centralized design tokens
* Comments that explain why
* No unnecessary dependencies

### Security and testing

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

## Use it with AI coding tools

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

## Keywords

`vibe coding` · `vibe coded website` · `AI-generated website` · `AI-generated UI` · `AI slop` · `AI slop UI` · `generic website` · `generic AI website` · `AI web design` · `AI frontend` · `Claude Code` · `Cursor` · `Lovable` · `Bolt` · `v0` · `frontend design` · `web UI` · `UI design` · `frontend development`

## Topics:

vibe-coding, vibe-coded-website, ai-generated-ui, ai-generated-websites, ai-slop, ai-slop-ui, frontend-design, frontend-development, web-design, ui-design, claude-code, cursor, lovable, bolt
v0
````

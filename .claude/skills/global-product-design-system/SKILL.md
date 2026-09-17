---
name: global-product-design-system
description: GLOBAL HARD RULE (2026-09-17) — Premium Product Design, UI/UX, Graphics & System Completeness. Apply whenever building, modifying, redesigning, improving, fixing or continuing ANY app, website, dashboard, SaaS, landing page, admin panel, portal or internal tool — and on any phrase like "make it look sharp / professional / modern / better / like a million-dollar system / like Meta Business Suite", "fix the UI", "redo the design", "bring all pages up to standard", "use our global design system". Act as CPO + CDO + UX architect + brand designer + design-systems engineer. Enterprise-grade quality (Stripe/Linear/HubSpot/Salesforce bar, no copying). Functional ≠ complete: design, branding, responsiveness, states and workflows must be complete too. Canonical text: essman929/AI-MEMORY memory/GLOBAL-PRODUCT-DESIGN-SYSTEM.md.
---

# Global Product Design System (compact operating version)

**Source of truth:** `essman929/AI-MEMORY` → `memory/GLOBAL-PRODUCT-DESIGN-SYSTEM.md` (17 sections, verbatim). This is the vendored operating copy — edit the canonical file, then re-vendor.

**Who you are:** CPO · CDO · Senior UX/UI Architect · Brand & Visual Identity Designer · Senior Frontend Engineer · Design Systems Engineer · Product Completeness Auditor · Enterprise SaaS Experience Architect. **Bar:** Meta Business Suite, Stripe, Linear, Notion, HubSpot, Salesforce, Shopify, Atlassian — hierarchy, consistency, usability, IA, interaction. Never copy their branding. **No generic template-looking apps.** A functional app is not complete until design, UX, brand, responsiveness, states and workflows are complete.

## Scott's design preference (read this first)

Scott is a business owner + marketer, not a designer. He gives concept, audience, brand, logo, colour preference, examples, screenshots, rough words. **Translate that into professional decisions and proceed.** "Make it look sharp / professional / modern / better / million-dollar / like Meta" = full product-design improvement, not a colour change. Ask only what materially affects brand, business rules, architecture or UX. Never ask him to pick paddings, fonts or component styles.

## Every build/modify/redesign request — the 11 steps

1 understand business objective → 2 inspect architecture + implementation → 3 identify existing design language, brand, colours, type, components → 4 new design system or extend existing? → 5 design hierarchy + layouts **before** major UI code → 6 build/improve graphics, logos, icons, illustrations, charts → 7 implement responsive, accessible, production UI → 8 connect every interface to real functionality → 9 test full workflows incl. empty/loading/error/success/permission states → 10 audit against this skill → 11 revisit weak decisions **before** declaring done. Never stop at "the page works". Find design problems proactively.

## Discovery before touching an existing project

Repo layout, branch state, framework, package config, design system, Tailwind config, CSS architecture, component library, routing, auth, schema, API routes, pages, shared layouts, assets, logo/brand files, responsive behaviour, tests, deploy config, env usage. Decide: works / incomplete / visually weak / reusable / must redesign / must not break / dependencies. **Never** rewrite working backend for a frontend look, replace approved branding without authorization, or discard work you don't understand.

## Design Director Mode (before any significant new interface)

Preserve + extend existing brand guidelines if they exist (repo CLAUDE.md palettes win). Otherwise establish: brand personality, tone, primary/secondary/surface/text/border/accent colours, typography, icon style, logo treatment, illustration + chart style, button + nav treatment. Pick one coherent direction (premium enterprise SaaS · modern corporate · clean financial · professional marketing · high-conversion landing · ops command center · minimalist productivity · premium AI · modern CRM · healthcare admin). **Light corporate is often better than dark-tech.** No auto dark mode, glassmorphism, gradient piles or neon.

## Design system requirements

Use the stack already present; prefer Tailwind + shadcn/ui + Radix + Lucide + Inter/Geist + CSS-variable tokens + reusable React components + semantic HTML when compatible. No new frameworks for looks. **Tokens** (centralized, never scattered): primary, secondary, background, surface, elevated surface, text primary/secondary, border, success/warning/error/info, focus, spacing, radius, shadows, typography, component heights. **Type hierarchy:** page title · section · card title · body · supporting · labels · nav · button · table · numeric metrics. **Layout:** intentional content width, margins, grid, sidebar width, header height, card/section spacing, alignment, whitespace, breakpoints. Every page has one clear primary task.

## Premium UI standard

**Required:** clear hierarchy · consistent alignment · pro typography · balanced whitespace · strong contrast · consistent component sizing · cohesive palette · right density · polished nav · predictable interactions · responsive · meaningful empty states · pro loading states · clear errors · consistent success feedback · keyboard access · no clutter.
**Avoid:** unstyled/default-browser controls · random colours · over-rounded cards · inconsistent radii · purposeless empty areas · crowded dashboards · needless gradients/glass · distracting animation · placeholder content as real data · broken image icons · misaligned buttons · text overflow · squeezed desktop-on-mobile · duplicate nav · inconsistent terminology. Every visual element must serve brand, comprehension, hierarchy or interaction.

## Graphics, logos, assets

You own the visuals. Logo: preserve official one if it exists; else propose identity → clean scalable SVG → icon-only/horizontal/stacked/light/dark/favicon variants → works at mobile + desktop → contrast + consistent geometry → never generic, never copyrighted marks, **never placeholder logos in production**. Illustrations/hero/marketing imagery via image-gen tools or supplied assets. Consistent vector icons. Charts: one visual language, readable labels/legends/tooltips/states (see `dataviz` skill when present). Nothing that looks like an unfinished mockup.

## Page-by-page

Per page: purpose · primary user · primary action · secondary actions · hierarchy · nav context · content structure · density · required states · mobile behaviour · permission differences · assets · reusable components. **Dashboards:** sidebar, header, breadcrumbs, title, contextual actions, KPI cards, tables, charts, filters, search, pagination, empty/loading/error, detail panels, modals, notifications, role visibility, mobile nav. **Landing pages:** brand, hero, value prop, primary CTA, proof, feature hierarchy, screenshots/illustrations, pricing if needed, FAQ, trust, footer, responsive conversion flow. No filler sections.

## Product completeness (per feature)

Accessible · understandable · action works · validation · loading · success feedback · error handling · persistence · updated data shows everywhere relevant · permissions · related features stay in sync · mobile · refresh/navigation keep state · empty/first-use · destructive actions confirmed. Audit every button, link, form, table, filter, search, sort, pagination, tab, dropdown, modal, drawer, toggle, checkbox, nav, auth, CRUD, API call, DB write, notification, setting, export, upload, billing flow, role permission. **A button existing ≠ feature complete.** (This is the Universal Completeness Protocol applied to the interface.)

## Responsive

320 / 375 / 390 / 430 / tablet / laptop / desktop / wide. Check overflow, nav, sidebar collapse, tables, forms, button wrap, cards, modals, type + image scaling, touch targets, scroll, long labels/numbers, empty states, errors. **Redesign layout behaviour for small screens; don't shrink desktop.**

## Process for major features

1 Understand → 2 Plan (pages, components, workflows, tokens, deps) → 3 Design (direction, hierarchy, responsive layout, components) → 4 Implement → 5 Integrate (FE/BE/DB/auth/workflows) → 6 Validate (function, responsive, a11y, visual consistency) → 7 Refine (hierarchy, spacing, type, alignment, feedback, polish) → 8 Audit (Universal Completeness Protocol; Forensic QA gate before "done") → 9 Report (changed, tested, remaining, approvals needed). **Never stop after 4.**

## Existing-project redesign mode

Retrofit audit, not rebuild: list pages, components, inconsistencies, weak layouts, missing states, poor mobile, unprofessional graphics, inconsistent nav, unfinished/broken workflows. Improve in a controlled way. **Preserve** working functionality, DB integrity, API contracts, auth, user data, business rules, approved branding, integrations. Shared components + tokens across the **whole** app — never one polished page next to unchanged ones.

## Global design audit (after the work)

Same product on every page? Colours, fonts, buttons, cards, tables, nav, titles, spacing, icons consistent? Empty/loading/error states professional? Graphics sharp? Mobile usable? Commercially credible? Intentionally designed, not assembled from defaults? **Fix what you find. Never report only "build succeeded."**

## Quality gate (all before "done")

Business requirements · existing functionality preserved · design system established · pro typography · consistent colours · consistent spacing · consistent components · pro graphics · responsive · accessible · loading · empty · error · success · complete workflows · DB + API integration · auth + permissions · no obvious UI defects · no placeholder content in production paths · relevant tests · project still works. Any critical fail → keep working or name the blocker.

## Communication

Direct, precise, minimal jargon. For design decisions: what was chosen · why it fits the business · alternatives if relevant · what was implemented · what needs approval. Decide and proceed on reasonable ambiguity; ask one focused question only when business function is at stake.

## Trigger phrases → whole-app scope

"Redo the design" · "make it look professional" · "audit the entire system" · "make it like a million-dollar SaaS" · "fix the UI" · "bring all pages up to standard" · "use our global design system" · "redo all existing projects" → apply across the relevant application, not just the current screen.

## Coexistence

Universal Completeness Protocol = what must be connected (this skill's §10 and step 8 call it). Forensic QA Protocol (Part II §41–67 "$100M standard") = the final completion audit of the same standard. Repo CLAUDE.md wins on stack, branch, deploy and any approved palette/brand — extend, never replace. Mentor Mode's 1–2 lines come first. Caveman Ultra compresses the report, never the design work.

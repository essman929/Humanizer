# Humanizer

.NET library for humanizing numbers, dates, times, enums, quantities, and more across 65 locale files.

## Quick Commands

```bash
# Build the main library (all target frameworks)
dotnet build src/Humanizer/Humanizer.csproj -c Release

# Build entire solution
dotnet build Humanizer.slnx -c Release

# Pack NuGet package
dotnet pack src/Humanizer/Humanizer.csproj -c Release -o artifacts

# Run tests (all three TFMs build on every platform; net48 test execution requires a Windows host)
dotnet test --project tests/Humanizer.Tests/Humanizer.Tests.csproj --framework net11.0
dotnet test --project tests/Humanizer.Tests/Humanizer.Tests.csproj --framework net10.0
dotnet test --project tests/Humanizer.Tests/Humanizer.Tests.csproj --framework net8.0
dotnet test --project tests/Humanizer.Tests/Humanizer.Tests.csproj --framework net48  # Windows only

# Run analyzer tests
dotnet test --project tests/Humanizer.Analyzers.Tests/Humanizer.Analyzers.Tests.Roslyn38.csproj
dotnet test --project tests/Humanizer.Analyzers.Tests/Humanizer.Analyzers.Tests.Roslyn48.csproj
dotnet test --project tests/Humanizer.Analyzers.Tests/Humanizer.Analyzers.Tests.Roslyn414.csproj

# Run source generator tests
dotnet test --project tests/Humanizer.SourceGenerators.Tests/Humanizer.SourceGenerators.Tests.csproj

# Lint (verify formatting without changes)
dotnet format Humanizer.slnx --verify-no-changes --verbosity diagnostic

# Format (auto-fix)
dotnet format Humanizer.slnx

# Verify package structure after packing
pwsh tests/verify-packages.ps1 -PackagePath artifacts
```

## Project Structure

```
src/
  Humanizer/                    # Main library (net10.0, net8.0, net48, netstandard2.0)
    Locales/                    # 65 YAML locale definition files
    Configuration/              # Formatter/converter registries
  Humanizer.SourceGenerators/   # Roslyn source generators (YAML -> C# tables, library build-time only, not shipped)
  Humanizer.Analyzers/          # Roslyn analyzers shipped in NuGet package (namespace migration, API guidance)
  Benchmarks/                   # BenchmarkDotNet performance benchmarks
tests/
  Humanizer.Tests/              # Primary test suite (xUnit v3, 40k+ tests)
    Localisation/               # Culture-specific test folders
  Humanizer.Analyzers.Tests/    # Analyzer unit tests
  Humanizer.SourceGenerators.Tests/  # Source generator tests
  fixtures/                     # Package smoke tests (Console, Blazor, WebApi)
website/                        # Docusaurus source, generated API, and immutable version snapshots
docs/plans/                     # Documentation implementation plans
```

## Code Conventions

- Follow `.editorconfig` strictly: 4-space indentation, file-scoped namespaces, `var` for obvious types
- `EnforceCodeStyleInBuild=true` and `TreatWarningsAsErrors=true` are enabled globally
- Naming: camelCase private fields, PascalCase public members/constants/static readonly
- Use `System.*` usings first; prefer existing global usings
- Add XML documentation for new/modified public APIs
- No `try/catch` around imports, no unnecessary `this.`, no redundant braces on one-line blocks

## Testing

- Framework: xUnit v3 with Microsoft Testing Platform
- Use `UseCulture` attribute for culture-specific tests
- Place locale tests under `tests/Humanizer.Tests/Localisation/{culture}/`
- Snapshot testing via Verify library for golden-file comparisons

## Localization

- Locale data defined in YAML files under `src/Humanizer/Locales/`
- Source generators transform YAML into C# lookup tables at build time
- To add a locale: duplicate a YAML file and translate it; the source generator wires all registries automatically (see `website/docs/contributing/adding-or-updating-a-locale.mdx`)
- When ICU-supplied data (month names, decimal separators) differs across platforms, author explicit overrides in `calendar:` and/or `number.formatting:` YAML surfaces
- See `website/docs/contributing/adding-or-updating-a-locale.mdx` and `website/docs/contributing/locale-yaml-surface-reference.mdx` for the full guide

## Key Config Files

- `global.json` - .NET SDK version (11.0.100-preview.6.26359.118)
- `Directory.Build.props` - Shared MSBuild properties (nullable, warnings-as-errors, analyzers)
- `Directory.Packages.props` - Central package management (all NuGet versions)
- `version.json` - Nerdbank.GitVersioning semver config
- `.editorconfig` - Code style rules enforced at build time

---

<!-- universal-completeness:begin (vendored from essman929/AI-MEMORY templates/universal-completeness-repo-kit — edit there, re-run install.py) -->
## Global rule: Universal Product Completeness & System Integration Protocol (2026-09-05)

**Applies to every development request in this repo, every session, every prompt.** A
request names one part of a larger system. Never change only the thing named.

Before any meaningful change run: **UNDERSTAND → LOCATE → SCAN → MAP → DESIGN →
IMPLEMENT → CONNECT → VERIFY → SEARCH AGAIN → AUDIT → REPORT.**

- **Four levels, never stop at 1:** User goal → full Workflow → System (pages, DB,
  APIs, automations, permissions, AI, notifications, reports) → Architecture.
- **Scan the whole repo first** (grep references, imports, schema, queries,
  endpoints, consumers, webhooks, jobs, prompts, agents, config, env, permissions,
  analytics, notifications, docs, tests, flags). Inspect DB schema and API
  contracts when available. Search again after building.
- **Change Impact Map** across frontend · backend · database · APIs · automations ·
  AI · business logic · analytics · security · tests.
- **Classify gaps P0 / P1 / P2.** Build P0 + safe P1. No speculative P2.
- **Connect every layer:** UI → API → backend → DB → result → UI; automations,
  AI prompts/agents, permissions (enforced on the backend), analytics, integrations.
- **Complete the entity:** CRUD + states (loading/empty/error/…) + forms +
  tables + permissions + cross-module links, sized to what the entity needs.
- **Single source of truth** over duplicated logic/config. Search before any
  rename/remove. Name architectural problems instead of building on them.
- **Done = user can operate the full workflow end to end**, verified with the
  repo's own checks and a real user-flow test. Visual ≠ functional.
- **Report:** changed · connected · dependencies found · extras · intentionally
  skipped · risks · P2 recs · workflow verified?

Operating copy: `.claude/skills/universal-completeness/SKILL.md`. Canonical text
(43 sections): `essman929/AI-MEMORY` → `memory/UNIVERSAL-COMPLETENESS-PROTOCOL.md`.
Per-prompt reminder: `.claude/hooks/universal-completeness.sh` (UserPromptSubmit).
Repo-specific rules above win on conventions (branch, deploy, DB access); this
protocol wins on completeness.
<!-- universal-completeness:end -->

---

<!-- product-design-system:begin (vendored from essman929/AI-MEMORY templates/universal-completeness-repo-kit — edit there, re-run install.py) -->
## Global rule: Premium Product Design, UI/UX, Graphics & System Completeness (2026-09-17)

**Applies whenever this repo's UI, pages, branding, graphics or user experience are
built, modified, redesigned, improved, fixed or continued — every session, every prompt.**
Act as CPO + CDO + UX architect + brand designer + design-systems engineer. Target the
Stripe / Linear / HubSpot / Salesforce / Meta Business Suite bar (never copy them). No
generic template-looking output. **Functional ≠ complete** until design, branding,
responsiveness, states and workflows are complete too.

- **Scott is not a designer.** "Make it sharp / professional / modern / better / like a
  million-dollar system" = a full product-design pass. Make defensible design decisions
  and proceed; ask only what affects brand, business rules, architecture or UX.
- **Discover first:** stack, existing design system, tokens, components, brand/logo
  files, palette in this file, routes, auth, schema. Extend what exists; never replace
  approved branding or rewrite working backend for a look.
- **Design direction before major UI code:** coherent palette, type hierarchy, spacing,
  radius, shadows, component heights as centralized tokens (Tailwind/shadcn/Radix/
  Lucide/Inter when compatible). Light corporate often beats dark-tech. No auto dark
  mode, glassmorphism, gradient piles, neon, placeholder logos or mock-looking graphics.
- **Every page:** purpose, primary user, primary action, hierarchy, states (loading,
  empty with CTA, error, success, unauthorized), mobile behaviour, permissions.
- **Responsive for real:** 320 / 375 / 390 / 430 / tablet / laptop / desktop / wide —
  redesign layout behaviour, don't shrink desktop.
- **Whole-app consistency:** one page polished next to unchanged pages is a defect.
  Shared tokens + components across the application.
- **Quality gate before "done":** design system · typography · colours · spacing ·
  components · graphics · responsive · accessible · loading/empty/error/success ·
  complete workflows · DB/API/auth wired · no placeholder content · tests · project
  still works. Then the Forensic QA gate.

Operating copy: `.claude/skills/global-product-design-system/SKILL.md`. Canonical text
(17 sections): `essman929/AI-MEMORY` → `memory/GLOBAL-PRODUCT-DESIGN-SYSTEM.md`.
Repo-specific rules above win on stack, branch, deploy and approved palette; this rule
wins on design quality. Pairs with the Universal Completeness Protocol (what must be
connected) and the Forensic QA Protocol (final audit).
<!-- product-design-system:end -->

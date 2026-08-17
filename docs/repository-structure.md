# Tailorfolio repository structure

> Status: Draft v0.1  
> Date: 2026-08-17  
> Scope: repository organization, not application architecture implementation

## 1. Purpose

This document defines:

- what must exist in the repository during iteration 0;
- the target monorepo layout planned for iteration 3;
- the responsibility of each top-level directory;
- constraints that prevent premature architecture and uncontrolled shared code.

The target layout is a direction, not permission to initialize all applications and packages immediately. Application code is introduced only after product requirements, domain modelling, and system design are complete.

## 2. Initial structure — iteration 0

```text
tailorfolio/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug-report.yml
│   │   ├── documentation.yml
│   │   └── feature-request.yml
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows/
│       └── documentation.yml
├── docs/
│   ├── decisions/
│   │   ├── README.md
│   │   └── ADR-template.md
│   ├── roadmap.md
│   └── repository-structure.md
├── .editorconfig
├── .gitignore
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── README.ru.md
└── README.md
```

### Responsibilities

| Path | Responsibility |
| --- | --- |
| `.github/ISSUE_TEMPLATE/` | structured task, defect, documentation, and change requests |
| `.github/PULL_REQUEST_TEMPLATE.md` | mandatory self-review and verification checklist |
| `.github/workflows/` | repository automation; only lightweight documentation checks during iteration 0 |
| `docs/decisions/` | Architecture Decision Records and their index |
| `docs/roadmap.md` | the governing roadmap and progress log |
| `docs/repository-structure.md` | repository layout and directory rules |
| `CONTRIBUTING.md` | branch, commit, pull request, review, and Definition of Done rules |
| `README.md` | public project entry point |

### What is intentionally absent

During iteration 0, the repository does not need:

- `apps/web` or `apps/api`;
- a root `package.json`;
- a package-manager lockfile;
- Turborepo configuration;
- frontend FSD layers;
- backend modules;
- database schema and migrations;
- Docker Compose;
- deployment workflows.

These artifacts belong to later roadmap iterations. Adding them now would force technology and architecture decisions before the requirements and domain model are ready.

## 3. Documentation growth by roadmap stage

The `docs` directory grows only when the corresponding iteration starts.

```text
docs/
├── architecture/
│   ├── diagrams/
│   ├── sequences/
│   └── fsd-map.md
├── decisions/
│   ├── README.md
│   ├── ADR-template.md
│   └── NNNN-decision-name.md
├── development/
│   └── local-setup.md
├── domain/
│   ├── domain-model.md
│   ├── glossary.md
│   └── relations.md
├── operations/
├── product/
│   ├── personas.md
│   ├── user-journeys.md
│   └── vision.md
├── requirements/
│   ├── business-rules.md
│   ├── functional.md
│   ├── non-functional.md
│   └── open-questions.md
├── security/
├── testing/
├── roadmap.md
└── repository-structure.md
```

Empty directories are not committed merely to mirror this tree. A directory appears together with its first meaningful document.

## 4. Target monorepo structure — from iteration 3

```text
tailorfolio/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   ├── workflows/
│   └── PULL_REQUEST_TEMPLATE.md
├── apps/
│   ├── api/
│   └── web/
├── packages/
│   ├── api-contract/
│   ├── config-eslint/
│   ├── config-typescript/
│   └── testing/
├── docs/
├── tooling/
├── .editorconfig
├── .gitignore
├── compose.yaml
├── CONTRIBUTING.md
├── LICENSE
├── package.json
├── pnpm-lock.yaml
├── pnpm-workspace.yaml
├── README.md
└── turbo.json
```

### Top-level responsibilities

| Path | Responsibility | Must not contain |
| --- | --- | --- |
| `apps/web` | browser application and frontend composition | backend persistence or server-only secrets |
| `apps/api` | HTTP API, application use cases, domain rules, persistence adapters | React code or frontend-specific state |
| `packages/api-contract` | OpenAPI artifacts and generated/derived contract tooling | database entities or UI components |
| `packages/config-*` | reusable repository configuration | product business logic |
| `packages/testing` | cross-application test infrastructure with proven reuse | application-specific fixtures by default |
| `docs` | decisions, requirements, architecture, and operating knowledge | generated build output |
| `tooling` | repository automation not published as an application package | business rules |

## 5. Package creation rule

A new package is created only when all conditions are met:

1. At least two consumers have a real need for the same capability, or the package represents an explicit system boundary such as the API contract.
2. The package has one clear responsibility.
3. Its public API can be described without referring to private application details.
4. Moving the code to a package reduces coupling rather than hiding it.
5. The decision does not create a second source of truth.

There is no generic `packages/shared` package. Shared code is classified by responsibility. If responsibility cannot be named, the code remains close to its first consumer until a real abstraction emerges.

## 6. Planned frontend structure

Feature-Sliced Design is introduced incrementally. Empty layers and slices are not created in advance.

```text
apps/web/src/
├── app/
├── pages/
├── widgets/
├── features/
├── entities/
└── shared/
```

### FSD dependency direction

```text
app → pages → widgets → features → entities → shared
```

A layer may import only layers below it. Slices on the same layer should remain independent. Each slice exposes a deliberate public API rather than allowing imports from arbitrary internal paths.

### FSD responsibilities

| Layer | Responsibility | Tailorfolio examples |
| --- | --- | --- |
| `app` | providers, routing, global initialization, application styles | router, query provider, locale initialization |
| `pages` | route-level composition | profile editor, portfolio preview, public portfolio |
| `widgets` | large self-contained interface sections | experience editor, portfolio header, publication panel |
| `features` | user actions that deliver business value | sign in, edit profile, reorder sections, publish portfolio |
| `entities` | domain concepts represented on the client | user, profile, project, experience, portfolio view |
| `shared` | domain-independent infrastructure and UI primitives | API base client, button, modal, date utilities |

Not every component must live in `features`, `entities`, or `widgets`. A component used by one page may remain inside that page until its semantic role becomes clear.

## 7. Planned backend structure

The backend is a modular monolith organized by business capability. It does not copy FSD.

```text
apps/api/src/
├── app/
│   ├── config/
│   ├── errors/
│   ├── plugins/
│   └── server/
├── modules/
│   ├── identity/
│   ├── profiles/
│   ├── portfolio-views/
│   ├── publications/
│   └── themes/
└── shared/
    ├── database/
    ├── observability/
    └── security/
```

The exact internal module structure is decided after the domain model and first vertical slice. A possible module may contain application use cases, domain rules, transport schemas, and infrastructure adapters, but those directories are not created unless their separation solves a concrete problem.

### Backend dependency rules

- modules own their business rules and persistence access;
- one module does not read another module's tables directly;
- cross-module interaction uses an explicit public interface;
- HTTP route handlers remain thin;
- validation happens at system boundaries;
- database constraints protect critical invariants;
- `shared` contains technical capabilities, not unidentified business logic.

## 8. Planned test placement

Tests stay close to the code when they describe local behaviour. Repository-level test suites exist only for cross-application scenarios.

```text
tailorfolio/
├── apps/
│   ├── api/
│   │   └── src/**/*.test.ts
│   └── web/
│       └── src/**/*.test.tsx
└── tests/
    ├── contract/
    └── e2e/
```

| Test type | Preferred location |
| --- | --- |
| domain unit test | beside the domain rule/use case |
| frontend component test | beside the component or feature |
| API integration test | inside the owning backend module |
| API contract test | `tests/contract` when it spans applications |
| browser E2E test | `tests/e2e` |

The final test structure is fixed in the testing strategy during iteration 11.

## 9. Naming conventions

- directories and filenames use `kebab-case` unless a tool imposes another convention;
- React components and their files use the convention selected in the frontend ADR;
- ADR filenames use `NNNN-short-decision-name.md`;
- environment variables use `UPPER_SNAKE_CASE`;
- package names use the project scope once the package namespace is selected;
- database names follow one convention fixed in the database ADR;
- abbreviations are avoided unless they are unambiguous in the project glossary.

## 10. Generated files and repository hygiene

The repository does not commit:

- dependency directories;
- build output;
- local environment files with secrets;
- test screenshots and reports unless intentionally retained as documentation;
- generated API clients without an explicit regeneration and review policy;
- editor-specific settings that are not shared project configuration;
- placeholder directories without meaningful content.

Generated artifacts must have a documented source and reproduction command.

## 11. Open decisions

These decisions are intentionally deferred to the roadmap iteration where enough information is available:

| Decision | Target iteration |
| --- | ---: |
| repository visibility and ownership | 0 |
| license | 0 |
| package scope/name | 3 |
| exact package manager and monorepo tools | 3 |
| frontend naming conventions | 3 |
| API contract generation strategy | 3–4 |
| backend internal module layout | 4–6 |
| database migration organization | 4 |
| test placement details | 11 |
| deployment layout | 14 |

## 12. Change policy

This document can be clarified during implementation without changing the roadmap. A change requires a separate Change Request when it:

- replaces the planned monorepo with independent repositories;
- combines frontend and backend into a full-stack framework;
- abandons FSD for the frontend;
- changes the modular monolith direction;
- introduces microservices;
- adds a new independently deployed application to the MVP.

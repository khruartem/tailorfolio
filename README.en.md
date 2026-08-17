# Tailorfolio

> Create one professional profile. Tailor it for every role.

[Русский](README.md) | [English](README.en.md)

Tailorfolio is an open-source full-stack platform for creating multilingual resume portfolios and publishing them through a single shareable link.

The project is currently at the product and engineering foundation stage. The functionality described below is planned and is not yet implemented.

## The problem

Professional information is usually scattered across a traditional resume, job platforms, GitHub repositories, personal websites, and separate project descriptions. Sending all of it to an employer is inconvenient, while a single generic resume rarely fits every role or language.

Tailorfolio is intended to provide one source of professional data from which a user can create different portfolio views for specific roles, vacancies, audiences, and locales.

## Product idea

A user creates a professional profile containing experience, projects, skills, education, contacts, and relevant links. Based on that profile, the user can prepare several portfolio views, customize their content and presentation, translate them, and publish each view through a unique URL.

Examples of future views based on the same source profile:

- Frontend Developer;
- Full-stack Developer;
- System Analyst;
- English-language portfolio for international applications.

## Planned MVP

- account registration and authentication;
- professional profile editor;
- experience, projects, skills, education, contacts, and links;
- multiple portfolio views based on one source profile;
- section visibility and ordering;
- Russian and English content;
- predefined themes and limited visual customization;
- draft, preview, publish, and unpublish workflow;
- unique public portfolio URL;
- responsive and accessible public pages;
- basic SEO and social metadata;
- automated tests, CI/CD, and production observability.

The exact MVP boundaries are maintained in the [roadmap](docs/roadmap.md). New ideas do not enter the active scope automatically.

## Learning goals

Tailorfolio is also a production-like educational project focused on practical full-stack engineering:

- React and TypeScript application architecture;
- Feature-Sliced Design on the frontend;
- Node.js API development;
- PostgreSQL data modelling and migrations;
- authentication, authorization, and web security;
- unit, integration, component, and end-to-end testing;
- Docker and reproducible local environments;
- CI/CD, logging, metrics, and incident readiness;
- architectural documentation and technical decision-making.

## Preliminary technical direction

The technology choices and exact versions will be confirmed through Architecture Decision Records during the corresponding roadmap iterations.

| Area | Preliminary direction |
| --- | --- |
| Repository | pnpm workspaces and Turborepo monorepo |
| Frontend | React, TypeScript, Vite |
| Frontend architecture | Feature-Sliced Design |
| Data fetching | TanStack Query |
| Forms and validation | React Hook Form and Zod |
| Backend | Node.js, TypeScript, Fastify |
| Database | PostgreSQL and Drizzle ORM |
| API contract | OpenAPI |
| Testing | Vitest, Testing Library, Playwright |
| Infrastructure | Docker Compose and GitHub Actions |

Feature-Sliced Design applies to the frontend. The backend is planned as a modular monolith and will use boundaries appropriate to backend business modules rather than copying the frontend structure.

## Repository structure

The repository is intentionally documentation-first during iteration 0. Application directories will be initialized during iteration 3, after requirements, domain modelling, and system design are complete.

```text
tailorfolio/
├── .github/
├── docs/
│   ├── decisions/
│   ├── roadmap.md
│   └── repository-structure.md
├── .editorconfig
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

See [Repository structure](docs/repository-structure.md) for the initial and target layouts, directory responsibilities, and dependency rules.

## Roadmap

Development follows a fixed theory-to-practice roadmap:

1. product foundation;
2. domain modelling and system design;
3. engineering foundation and monorepo initialization;
4. vertical feature slices;
5. core product functionality;
6. testing, security, accessibility, and performance;
7. deployment, observability, and production release;
8. open-source packaging and final architecture defense.

After every iteration, the roadmap is updated with the result, completed checks, discovered gaps, and links to relevant pull requests and documents. Timeline estimates may change; changes to the project goal or mandatory scope require a separate Change Request.

## Project status

**Iteration 0 — Initialization: in progress.**

Current tasks:

- [x] select a working project name;
- [x] define the initial and target repository structures;
- [x] prepare the initial README;
- [ ] create the GitHub repository;
- [ ] add the roadmap to `docs/roadmap.md`;
- [ ] add contribution rules and repository templates;
- [ ] configure the project board and milestones;
- [ ] complete the first task through the full pull request workflow.

## Documentation

- [Roadmap](docs/roadmap.md)
- [Repository structure](docs/repository-structure.md)
- [Русская версия README](README.md)
- Architecture Decision Records: `docs/decisions/`

Product, architecture, security, testing, and operations documentation will be added during the roadmap iterations in which those decisions are made.

## Contributing

The contribution workflow is being defined as part of iteration 0. Until `CONTRIBUTING.md` is finalized, the repository should be treated as an early-stage educational project.

## License

The license has not been selected yet. It will be fixed before the first public release.

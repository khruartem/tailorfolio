# Full-stack Resume Portfolio Platform — дорожная карта

> Статус: `Draft v0.1`  
> Дата фиксации: `2026-08-15`  
> Формат: теория → проектирование → реализация → проверка → фиксация прогресса  
> Рабочее название продукта: `TBD`

## 1. Назначение документа

Эта дорожная карта — основной управляющий документ проекта. Она одновременно задаёт:

- продуктовую цель и границы проекта;
- порядок изучения теории;
- последовательность практических итераций;
- обязательные инженерные артефакты;
- критерии завершения каждой итерации;
- правила изменения плана;
- журнал фактического прогресса.

Сроки можно двигать без изменения содержания. Содержательные изменения цели, MVP, архитектурного направления или состава обязательных итераций принимаются только после отдельного обсуждения и фиксируются в журнале изменений.

## 2. Режим работы

### 2.1. Правила

1. Двигаемся строго по порядку итераций.
2. Не начинаем следующую итерацию, пока не выполнен Definition of Done текущей.
3. Внутри итерации сначала разбираем необходимую теорию, затем проектируем и только после этого пишем код.
4. Теория изучается применительно к проекту, а не как изолированный курс.
5. Каждое существенное техническое решение оформляется как ADR.
6. После каждой итерации проводим ревью результата и обновляем этот документ.
7. Новые идеи не добавляются в текущую работу автоматически. Они попадают в Product Backlog или Parking Lot.
8. Исправление ошибки, уязвимости или неверного архитектурного решения не считается изменением сути дорожной карты.
9. Изменение сроков не требует пересмотра содержания дорожной карты.
10. Изменение цели, состава MVP или обязательного технологического контура требует отдельного согласования.

### 2.2. Результат каждой итерации

Итерация считается завершённой только при наличии четырёх результатов:

- понятна изученная теория и пройдено короткое устное/письменное интервью;
- создан запланированный работающий инкремент;
- пройдены проверки качества;
- обновлены документация и таблица прогресса.

### 2.3. Маркировка статуса

- `[ ]` — не начато;
- `[~]` — в работе;
- `[x]` — завершено;
- `[!]` — заблокировано;
- `[-]` — исключено отдельным согласованным решением.

## 3. Видение продукта

### 3.1. Проблема

Специалисту неудобно отправлять работодателю разрозненные сведения об опыте, проектах, навыках и GitHub. Стандартные платформы ограничивают оформление, требуют отдельного аккаунта или плохо поддерживают несколько языков и адаптацию под конкретную вакансию.

### 3.2. Решение

Многопользовательский веб-сервис, в котором специалист создаёт единый профиль резюме-портфолио, формирует на его основе разные представления, локализует контент, настраивает оформление и публикует результат по одной ссылке.

### 3.3. Основная ценность

- единый источник профессиональных данных;
- одна публичная ссылка для работодателя;
- разные представления под роли, вакансии и языки без полного дублирования данных;
- индивидуальное визуальное оформление;
- независимость от HH, LinkedIn и других карьерных платформ.

### 3.4. Целевые пользователи MVP

- разработчики и другие IT-специалисты;
- кандидаты, работающие с международными вакансиями;
- специалисты с несколькими профессиональными позиционированиями;
- кандидаты, которым важно показать проекты и GitHub вместе с опытом.

### 3.5. Продуктовый результат MVP

Зарегистрированный пользователь может создать профессиональный профиль, наполнить его данными, сформировать русское и английское представления, настроить внешний вид, опубликовать выбранное представление по уникальной ссылке и отправить её работодателю.

## 4. Границы проекта

### 4.1. Обязательный MVP

- регистрация, вход, выход и управление сессией;
- профиль пользователя;
- профессиональный профиль как единый источник данных;
- разделы: о себе, опыт, проекты, навыки, образование, контакты и ссылки;
- создание нескольких представлений одного профиля;
- выбор видимости и порядка разделов в представлении;
- локализованный контент минимум на русском и английском;
- тема оформления и ограниченная кастомизация;
- черновик, предпросмотр, публикация и снятие с публикации;
- уникальный публичный URL;
- адаптивная и доступная публичная страница;
- базовая SEO-разметка и метаданные публичной страницы;
- тесты критических пользовательских сценариев;
- контейнеризированное локальное окружение;
- CI/CD и production-развёртывание;
- логирование, обработка ошибок и базовая наблюдаемость.

### 4.2. После MVP

- импорт репозиториев через GitHub API;
- AI-перевод и адаптация описания под вакансию;
- экспорт в PDF;
- собственные домены;
- аналитика просмотров;
- пароль для отдельного представления;
- QR-коды;
- дополнительные шаблоны;
- загрузка резюме и импорт данных;
- совместное редактирование;
- marketplace шаблонов;
- биллинг и платные тарифы.

### 4.3. Не делаем в рамках основного плана

- полноценный no-code page builder;
- произвольное редактирование HTML/CSS пользователем;
- социальную сеть и ленту;
- встроенную систему откликов на вакансии;
- ATS или CRM для рекрутеров;
- мобильные приложения;
- микросервисную архитектуру до появления измеримой необходимости.

## 5. Учебные цели

К завершению проекта разработчик должен уметь объяснить и практически показать:

### Frontend

- проектирование React-приложения на TypeScript;
- границы слоёв, слайсов и сегментов FSD;
- серверное и клиентское состояние;
- формы, валидацию и обработку ошибок;
- аутентификацию на клиенте;
- локализацию;
- доступность и адаптивность;
- тестирование компонентов и пользовательских сценариев;
- архитектурные компромиссы и предотвращение преждевременной абстракции.

### Backend

- устройство Node.js и асинхронной модели выполнения;
- проектирование HTTP API;
- модульную архитектуру backend;
- валидацию входных данных и сериализацию ответов;
- аутентификацию, авторизацию и управление сессиями;
- транзакции, конкурентный доступ и идемпотентность;
- обработку ошибок, логирование и конфигурацию;
- интеграционные и контрактные тесты.

### Data

- реляционное моделирование;
- ограничения целостности;
- нормализацию и осознанную денормализацию;
- индексы и анализ запросов;
- миграции;
- транзакции и уровни изоляции;
- резервное копирование и восстановление.

### Production engineering

- monorepo и управление зависимостями;
- Docker и локальную инфраструктуру;
- CI/CD;
- управление секретами и окружениями;
- безопасность web-приложения;
- метрики, логи, трассировку и health checks;
- производительность и нагрузочное тестирование;
- документирование и защиту системного дизайна.

## 6. Предварительное техническое направление

Окончательный выбор и версии фиксируются в ADR на соответствующих итерациях.

| Контур | Предварительный выбор | Для чего изучаем |
| --- | --- | --- |
| Monorepo | pnpm workspaces + Turborepo | общие пакеты, единые проверки, независимые приложения |
| Frontend | React + TypeScript + Vite | SPA-редактор и публичное представление |
| Frontend architecture | Feature-Sliced Design | архитектурные границы и масштабирование UI |
| Routing | React Router | приватные и публичные маршруты |
| Server state | TanStack Query | кеш, запросы, мутации и инвалидация |
| Forms | React Hook Form | сложные формы с контролируемой производительностью |
| Validation | Zod | runtime-валидация и типизация на границах |
| Backend | Node.js + TypeScript + Fastify | отдельный API без сокрытия backend-механики full-stack фреймворком |
| Database | PostgreSQL | реляционная модель и production-практики |
| Data access | Drizzle ORM | типизированные запросы и явная работа со схемой |
| API contract | OpenAPI | документированный и проверяемый контракт |
| Unit/integration tests | Vitest | быстрые тесты frontend и backend |
| Component tests | Testing Library | проверка поведения UI |
| E2E | Playwright | критические пользовательские сценарии |
| Infrastructure | Docker Compose | воспроизводимое локальное окружение |
| CI/CD | GitHub Actions | автоматические проверки и доставка |
| Observability | structured logs + error tracking + metrics | диагностика production-системы |

### Архитектурные ограничения

- FSD применяется к frontend, но не переносится механически на backend.
- Backend начинается как модульный монолит.
- Приложения могут иметь общие пакеты, но бизнес-логика не должна бесконтрольно утекать в `shared`.
- Общие типы не заменяют API-контракт и runtime-валидацию.
- ORM не заменяет знание SQL и PostgreSQL.
- Архитектура усложняется только после появления конкретной проблемы.

## 7. Карта этапов

| Этап | Итерации | Результат |
| --- | --- | --- |
| A. Product foundation | 0–2 | требования, модель, решения и план MVP |
| B. Engineering foundation | 3–4 | monorepo, инфраструктура, каркас frontend/backend |
| C. First vertical slice | 5–6 | авторизация и первый сохраняемый раздел профиля |
| D. Core product | 7–10 | редактор, представления, локализация и публикация |
| E. Quality and security | 11–13 | тестирование, безопасность, доступность и performance |
| F. Production | 14–16 | CI/CD, наблюдаемость, deployment и эксплуатация |
| G. Portfolio release | 17–18 | документация, demo, архитектурная защита и релиз MVP |

## 8. Подробные итерации

## Итерация 0. Инициализация процесса

**Цель:** создать управляемую основу проекта до выбора решений и написания кода.

**Теория**

- product roadmap, backlog, milestone, iteration;
- Definition of Ready и Definition of Done;
- semantic versioning документации;
- ADR и журнал решений;
- GitHub Issues, milestones и project board;
- conventional commits и trunk-based development в solo-проекте.

**Практика**

- выбрать рабочее и публичное название;
- создать репозиторий и базовую структуру документации;
- создать `README`, `CONTRIBUTING`, шаблоны issue и pull request;
- завести board: Backlog → Ready → In Progress → Review → Done;
- создать milestones по этапам дорожной карты;
- зафиксировать правила веток, коммитов и self-review;
- перенести эту дорожную карту в репозиторий без изменения смысла.

**Артефакты**

- `docs/roadmap.md`;
- `docs/decisions/ADR-template.md`;
- `CONTRIBUTING.md`;
- issue/PR templates;
- настроенный project board.

**Definition of Done**

- [ ] репозиторий доступен;
- [ ] структура управления задачами настроена;
- [ ] правила работы зафиксированы;
- [ ] первая задача проходит полный workflow через PR;
- [ ] проведено мини-интервью по Git-процессу и ADR.

---

## Итерация 1. Product discovery и требования

**Цель:** доказать и точно описать решаемую проблему и границы MVP.

**Теория**

- problem statement и value proposition;
- персона, JTBD и пользовательский сценарий;
- функциональные и нефункциональные требования;
- ограничения, допущения и бизнес-правила;
- acceptance criteria;
- приоритизация MoSCoW;
- метрики продукта и критерии успеха MVP.

**Практика**

- сформировать problem statement;
- описать основные персоны и JTBD;
- провести конкурентный обзор без копирования продукта;
- описать happy paths и error paths;
- сформировать список функциональных требований;
- определить нефункциональные требования с измеримыми значениями;
- определить scope MVP, post-MVP и out of scope;
- написать критерии приёмки MVP.

**Артефакты**

- `docs/product/vision.md`;
- `docs/product/personas.md`;
- `docs/product/user-journeys.md`;
- `docs/requirements/functional.md`;
- `docs/requirements/non-functional.md`;
- `docs/requirements/business-rules.md`;
- `docs/requirements/open-questions.md`.

**Definition of Done**

- [ ] у каждого требования есть идентификатор и приоритет;
- [ ] каждое обязательное требование связано с пользовательской ценностью;
- [ ] MVP не содержит post-MVP возможностей;
- [ ] отсутствуют критичные открытые вопросы;
- [ ] проведена защита требований в формате интервью с заказчиком.

---

## Итерация 2. Доменная модель и системный дизайн

**Цель:** спроектировать систему до выбора деталей реализации.

**Теория**

- сущности, value objects, агрегаты и инварианты;
- связи 1:1, 1:N и M:N;
- bounded context как способ поиска границ, без преждевременного DDD;
- C4 Context и Container diagrams;
- монолит, модульный монолит и микросервисы;
- sync/async взаимодействие;
- consistency, availability и основные failure modes;
- build vs buy.

**Практика**

- выделить сущности и бизнес-правила;
- разделить профессиональные данные, представления, локализации и публикации;
- определить владельца каждого типа данных;
- построить ER-модель первого приближения;
- построить C4 Context и Container;
- определить модули backend и крупные slices frontend;
- описать ключевые sequence diagrams;
- создать risk register;
- принять ADR о модульном монолите и границах frontend/backend.

**Артефакты**

- `docs/domain/glossary.md`;
- `docs/domain/domain-model.md`;
- `docs/domain/relations.md`;
- `docs/architecture/c4-context.md`;
- `docs/architecture/c4-container.md`;
- `docs/architecture/sequences/`;
- `docs/architecture/risk-register.md`;
- первые ADR.

**Definition of Done**

- [ ] все сущности поддерживают требования MVP;
- [ ] у связей указаны cardinality, обязательность и правила удаления;
- [ ] различаются профиль, его представление, локализация и публикация;
- [ ] известны основные failure modes;
- [ ] архитектуру можно объяснить за 10 минут без обращения к коду.

---

## Итерация 3. Стек, monorepo и quality gates

**Цель:** создать воспроизводимый инженерный каркас проекта.

**Теория**

- monorepo: преимущества, цена и границы пакетов;
- package manager, workspace и lockfile;
- TypeScript project references;
- linting, formatting и static analysis;
- dependency graph и circular dependencies;
- environment configuration;
- quality gates и fail-fast CI.

**Практика**

- зафиксировать ADR выбора стека;
- создать `apps/web`, `apps/api` и минимально необходимые `packages`;
- настроить TypeScript strict mode;
- настроить lint, format, typecheck и test scripts;
- определить правила импортов и границ модулей;
- добавить проверку FSD-границ;
- настроить pre-commit только для быстрых проверок;
- создать первый CI с install, lint, typecheck и test.

**Артефакты**

- рабочий monorepo;
- ADR по стеку;
- конфигурации TypeScript и quality tools;
- базовый CI workflow;
- `docs/development/local-setup.md`.

**Definition of Done**

- [ ] проект запускается по документированной инструкции;
- [ ] lockfile воспроизводим;
- [ ] lint, typecheck и tests проходят локально и в CI;
- [ ] запрещённые импорты обнаруживаются автоматически;
- [ ] секреты не закоммичены;
- [ ] проведено мини-интервью по monorepo и TypeScript boundaries.

---

## Итерация 4. Локальная инфраструктура, API skeleton и PostgreSQL

**Цель:** поднять минимальную систему web → API → database.

**Теория**

- Node.js runtime, event loop и async I/O;
- HTTP request/response lifecycle;
- REST constraints и resource-oriented API;
- Fastify plugins, hooks, schemas и encapsulation;
- PostgreSQL: таблицы, ключи, ограничения и индексы;
- migrations и seed data;
- Docker image, container, volume и network;
- health, readiness и liveness.

**Практика**

- поднять PostgreSQL через Docker Compose;
- создать API application factory;
- добавить конфигурацию с runtime-валидацией;
- реализовать `/health/live` и `/health/ready`;
- подключить БД и миграции;
- добавить structured logging и correlation/request ID;
- настроить единый error response;
- подключить frontend к health endpoint;
- описать локальный lifecycle инфраструктуры.

**Артефакты**

- `compose.yaml`;
- API skeleton;
- первая миграция;
- конфигурационная схема;
- OpenAPI skeleton;
- документация локальной инфраструктуры.

**Definition of Done**

- [ ] чистое окружение поднимается одной последовательностью команд;
- [ ] readiness отражает доступность обязательных зависимостей;
- [ ] ошибки API имеют единый формат;
- [ ] каждый запрос можно найти в логах по request ID;
- [ ] миграции применяются и откатываются безопасно в dev;
- [ ] есть интеграционный тест API с тестовой БД.

---

## Итерация 5. Identity: регистрация, вход и сессии

**Цель:** реализовать первый полный production-like вертикальный срез.

**Теория**

- authentication vs authorization;
- password hashing и политика паролей;
- cookie-based sessions vs access/refresh tokens;
- HttpOnly, Secure и SameSite cookies;
- CSRF, XSS, brute force и credential stuffing;
- session rotation, expiration и revocation;
- CORS и browser credentials;
- threat modeling.

**Практика**

- спроектировать identity-модель;
- принять ADR по механизму сессий;
- реализовать registration, login, logout и current user;
- хранить пароли только как устойчивый hash;
- реализовать валидацию и безопасные ошибки;
- добавить rate limiting на чувствительные endpoints;
- создать приватный маршрут frontend;
- реализовать формы входа и регистрации;
- покрыть happy path и основные атаки тестами;
- составить threat model для identity.

**Артефакты**

- identity module;
- frontend auth flow;
- OpenAPI endpoints;
- security tests;
- `docs/security/threat-model.md`.

**Definition of Done**

- [ ] пользователь может зарегистрироваться, войти и выйти;
- [ ] приватный API недоступен без валидной сессии;
- [ ] сессия корректно истекает и отзывается;
- [ ] отсутствует раскрытие факта существования аккаунта там, где это опасно;
- [ ] зафиксированы CSRF/XSS/CORS решения;
- [ ] пройдено security-review и мини-интервью по web authentication.

---

## Итерация 6. Первый профильный вертикальный срез

**Цель:** сохранить и отобразить первый реальный профессиональный контент end-to-end.

**Теория**

- server state vs client state;
- query keys, cache, invalidation и optimistic updates;
- forms, validation, dirty state и unsaved changes;
- DTO, domain model и persistence model;
- repository pattern: где полезен и где избыточен;
- FSD layers, slices, segments и public API;
- dependency rule и cross-imports.

**Практика**

- реализовать раздел `About` или `Profile Basics`;
- создать database schema и migration;
- реализовать create/read/update API;
- добавить ownership authorization;
- сгенерировать или написать типизированный API client;
- создать frontend по FSD;
- реализовать загрузку, редактирование, сохранение и ошибки;
- предотвратить потерю несохранённых изменений;
- добавить unit, integration и component tests.

**Артефакты**

- первый business module backend;
- первый entity/feature/page slice frontend;
- API contract;
- тестовая пирамида вертикального среза;
- `docs/architecture/fsd-map.md`.

**Definition of Done**

- [ ] данные проходят путь browser → API → database → browser;
- [ ] пользователь не может изменить чужие данные;
- [ ] runtime-валидация есть на API boundary;
- [ ] UI различает loading, empty, success и error states;
- [ ] FSD dependency rule не нарушена;
- [ ] вертикальный срез полностью покрыт критическими тестами.

---

## Итерация 7. Полная модель профессионального профиля

**Цель:** реализовать единый источник профессиональных данных.

**Теория**

- aggregate boundaries и transactional consistency;
- ordered collections;
- soft delete vs hard delete;
- optimistic concurrency control;
- idempotency;
- pagination и filtering;
- database constraints как последняя линия защиты.

**Практика**

- реализовать опыт, проекты, навыки, образование, контакты и ссылки;
- определить повторяемые UI-паттерны без преждевременного универсального конструктора;
- реализовать создание, изменение, удаление и изменение порядка элементов;
- добавить транзакции для составных операций;
- защититься от lost updates выбранной стратегией;
- добавить ограничения и индексы;
- создать seed-профиль для demo;
- расширить OpenAPI и тесты.

**Артефакты**

- полный profile module;
- editor widgets/features;
- миграции и seed;
- ADR по ordering и concurrent updates;
- обновлённая ER diagram.

**Definition of Done**

- [ ] все обязательные разделы профиля редактируются;
- [ ] порядок сохраняется детерминированно;
- [ ] конкурентное обновление не приводит к молчаливой потере данных;
- [ ] ограничения БД соответствуют бизнес-правилам;
- [ ] отсутствует преждевременный god-component/generic-builder;
- [ ] проведено ревью SQL, транзакций и FSD-декомпозиции.

---

## Итерация 8. Представления под роли и вакансии

**Цель:** отделить единые исходные данные от опубликованных вариантов портфолио.

**Теория**

- source of truth и projections;
- reference vs copy semantics;
- snapshotting и versioning;
- composition over duplication;
- draft/published state machine;
- authorization rules for nested resources.

**Практика**

- создать Portfolio View;
- разрешить несколько представлений одного профиля;
- выбирать видимые элементы и их порядок;
- переопределять заголовок и краткое позиционирование;
- реализовать draft state;
- добавить preview без публичной публикации;
- определить поведение представления при изменении исходного профиля;
- протестировать изоляцию представлений.

**Артефакты**

- portfolio-view module;
- state diagram lifecycle;
- ADR reference vs snapshot;
- preview page;
- acceptance tests.

**Definition of Done**

- [ ] один профиль поддерживает минимум два разных представления;
- [ ] изменение порядка в одном представлении не влияет на другое;
- [ ] preview доступен только владельцу;
- [ ] поведение при изменении исходных данных явно определено;
- [ ] lifecycle представления покрыт тестами.

---

## Итерация 9. Локализация данных и интерфейса

**Цель:** поддержать русское и английское портфолио без неконтролируемого дублирования.

**Теория**

- i18n vs l10n;
- UI messages vs localized domain content;
- locale negotiation и fallback;
- модели хранения переводов;
- Unicode, directionality и форматирование дат;
- SEO для мультиязычных страниц;
- missing translation strategies.

**Практика**

- локализовать интерфейс редактора;
- спроектировать хранение переводимого domain content;
- реализовать RU и EN версии;
- добавить явный fallback и индикатор неполного перевода;
- переключать язык preview/public page;
- корректно форматировать даты;
- подготовить `lang`, canonical и alternate metadata;
- протестировать смешанные и неполные переводы.

**Артефакты**

- i18n infrastructure;
- translation editor;
- ADR по модели локализации;
- translation completeness rules;
- тесты локалей.

**Definition of Done**

- [ ] UI и пользовательский контент локализуются независимо;
- [ ] публичная ссылка открывается в определённой локали;
- [ ] fallback детерминирован и видим в редакторе;
- [ ] отсутствуют строки интерфейса, зашитые в компонентах вне правил проекта;
- [ ] метаданные соответствуют выбранной локали.

---

## Итерация 10. Темы, кастомизация и публикация

**Цель:** довести главную пользовательскую ценность до рабочего релиза.

**Теория**

- design tokens и CSS custom properties;
- theme contract;
- ограниченная кастомизация vs arbitrary styles;
- responsive design;
- slug design и uniqueness;
- cache-control и публичный контент;
- publish/unpublish и immutable snapshot;
- SEO, Open Graph и social preview.

**Практика**

- создать минимум две темы на общем contract;
- настроить безопасные параметры цвета, типографики и плотности;
- реализовать slug и проверку доступности;
- реализовать publish/unpublish;
- решить, публикуется live view или snapshot;
- создать публичную страницу без авторизации;
- добавить metadata, Open Graph и sitemap strategy;
- добавить responsive preview;
- проверить публичный URL в чистой сессии браузера.

**Артефакты**

- theme system;
- public portfolio page;
- publication module;
- ADR по publication model и caching;
- release candidate функционального MVP.

**Definition of Done**

- [ ] пользователь публикует портфолио по уникальной ссылке;
- [ ] неопубликованная версия недоступна публично;
- [ ] темы не требуют дублирования бизнес-компонентов;
- [ ] пользовательские значения не позволяют внедрить произвольный CSS/HTML;
- [ ] публичная страница адаптивна и имеет корректные метаданные;
- [ ] основной end-to-end сценарий проходит полностью.

---

## Итерация 11. Стратегия тестирования и надёжность

**Цель:** построить осмысленную тестовую систему, а не коллекцию тестов ради coverage.

**Теория**

- test pyramid и testing trophy;
- unit, integration, component, contract и E2E tests;
- test doubles и границы mocking;
- deterministic tests;
- test data builders и database isolation;
- consumer/provider contract;
- coverage как сигнал, а не цель;
- flaky tests.

**Практика**

- зафиксировать test strategy;
- составить risk-based test matrix;
- привести существующие тесты к единой структуре;
- покрыть domain rules unit-тестами;
- покрыть API с реальной тестовой БД;
- покрыть UI поведением через Testing Library;
- реализовать E2E: регистрация → профиль → представление → публикация;
- добавить negative paths;
- настроить отчёты тестов в CI.

**Артефакты**

- `docs/testing/strategy.md`;
- test matrix;
- factories/builders/fixtures;
- стабильный E2E suite;
- CI test reports.

**Definition of Done**

- [ ] критические риски связаны с конкретными тестами;
- [ ] API integration tests используют PostgreSQL, а не несовместимую подмену;
- [ ] E2E не зависят от порядка запуска;
- [ ] тесты проверяют наблюдаемое поведение;
- [ ] flaky tests отсутствуют или имеют оформленный план устранения;
- [ ] разработчик может обосновать каждый уровень тестов.

---

## Итерация 12. Security hardening

**Цель:** системно проверить безопасность всего приложения.

**Теория**

- OWASP Top 10;
- broken access control и IDOR;
- injection, XSS, CSRF и SSRF;
- security headers и CSP;
- mass assignment;
- file upload threats, если изображения входят в MVP;
- dependency и secret scanning;
- least privilege;
- audit logging и privacy.

**Практика**

- обновить threat model всей системы;
- проверить authorization matrix для каждого ресурса;
- добавить security headers и CSP;
- проверить CORS и cookie settings;
- внедрить safe logging без паролей, токенов и лишних персональных данных;
- добавить dependency и secret scanning;
- проверить rate limits;
- провести ручной abuse-case review;
- исправить найденные проблемы и зафиксировать residual risks.

**Артефакты**

- обновлённый threat model;
- authorization matrix;
- security checklist;
- CI security checks;
- security review report.

**Definition of Done**

- [ ] object-level authorization протестирована;
- [ ] security headers проверены;
- [ ] секреты не попадают в repository, image и client bundle;
- [ ] чувствительные данные не попадают в логи;
- [ ] high/critical findings отсутствуют;
- [ ] residual risks явно задокументированы.

---

## Итерация 13. Accessibility, UX и performance

**Цель:** сделать продукт удобным, доступным и измеримо быстрым.

**Теория**

- semantic HTML и accessibility tree;
- keyboard navigation и focus management;
- ARIA: когда нужна и когда вредна;
- accessible forms и error announcements;
- Core Web Vitals;
- browser rendering и code splitting;
- image optimization;
- API latency percentiles p50/p95/p99;
- performance budgets.

**Практика**

- провести keyboard-only review;
- проверить screen reader critical flows;
- обеспечить labels, focus, errors и contrast;
- добавить automated accessibility checks;
- измерить bundle и web performance;
- определить performance budgets;
- оптимизировать маршруты, изображения и критический rendering path;
- измерить API latency;
- устранить N+1 и необоснованные запросы;
- провести минимальный load test публичного чтения.

**Артефакты**

- accessibility checklist/report;
- performance budget;
- Lighthouse/Web Vitals baseline;
- API/load test report;
- список принятых оптимизаций.

**Definition of Done**

- [ ] критический сценарий выполняется с клавиатуры;
- [ ] формы сообщают ошибки доступным способом;
- [ ] отсутствуют критические автоматические a11y-нарушения;
- [ ] performance budgets выполняются;
- [ ] публичное чтение выдерживает согласованный тестовый профиль нагрузки;
- [ ] оптимизации подтверждены измерениями.

---

## Итерация 14. Production infrastructure и CI/CD

**Цель:** создать воспроизводимый безопасный путь от коммита до production.

**Теория**

- multi-stage Docker builds;
- immutable artifacts;
- environment promotion;
- CI vs CD;
- database migration strategy;
- zero/low-downtime deployment;
- rollback и roll-forward;
- secrets management;
- supply-chain basics и image scanning.

**Практика**

- создать production Dockerfiles;
- запускать контейнеры под non-root user;
- настроить build cache;
- создать CI stages: validate → test → build → scan;
- настроить staging deployment;
- автоматизировать production deployment с контролируемым gate;
- определить порядок применения миграций;
- реализовать rollback/roll-forward runbook;
- проверить восстановление после неуспешного deployment.

**Артефакты**

- production images;
- CI/CD workflows;
- staging environment;
- deployment runbook;
- migration and rollback policy.

**Definition of Done**

- [ ] один commit однозначно связан с deployed artifact;
- [ ] production image минимален и запускается не от root;
- [ ] deploy невозможен при провале обязательных quality gates;
- [ ] секреты передаются вне image/repository;
- [ ] миграции имеют безопасный план совместимости;
- [ ] процедура восстановления проверена на staging.

---

## Итерация 15. Observability и эксплуатация

**Цель:** уметь обнаруживать, диагностировать и устранять проблемы production.

**Теория**

- logs, metrics и traces;
- RED и USE methods;
- SLI, SLO и error budget;
- alert quality;
- health checks;
- incident response;
- backup, restore и disaster recovery;
- RPO и RTO.

**Практика**

- централизовать structured logs;
- внедрить error tracking;
- добавить ключевые metrics API и БД;
- связать frontend error с backend request ID, где возможно;
- создать dashboard для golden signals;
- определить SLI/SLO MVP;
- настроить минимальный набор actionable alerts;
- автоматизировать backup БД;
- выполнить restore drill;
- написать incident runbook.

**Артефакты**

- observability dashboard;
- SLI/SLO document;
- alert rules;
- backup/restore runbook;
- incident response runbook;
- результат restore drill.

**Definition of Done**

- [ ] ошибочный запрос прослеживается по логам;
- [ ] критическая frontend/backend ошибка попадает в error tracking;
- [ ] alerts связаны с пользовательским воздействием;
- [ ] backup создаётся автоматически;
- [ ] восстановление проверено, а RPO/RTO измерены;
- [ ] проведена учебная симуляция инцидента.

---

## Итерация 16. Production release и обратная связь

**Цель:** выпустить MVP реальным пользователям и проверить продуктовые гипотезы.

**Теория**

- release readiness;
- feature flags и controlled rollout;
- product analytics с учётом privacy;
- feedback loops;
- activation funnel;
- qualitative vs quantitative feedback.

**Практика**

- провести release checklist;
- подготовить demo accounts/data;
- развернуть production;
- создать собственное реальное резюме-портфолио;
- отправить ссылку ограниченной группе пользователей;
- собрать feedback по заранее заданным вопросам;
- измерить путь registration → first published portfolio;
- классифицировать проблемы без расширения MVP;
- выпустить стабилизирующий patch release.

**Артефакты**

- production MVP;
- release notes;
- feedback report;
- product metrics baseline;
- post-release issue list.

**Definition of Done**

- [ ] реальный пользователь проходит основной сценарий;
- [ ] опубликована рабочая страница автора проекта;
- [ ] критические post-release bugs устранены;
- [ ] обратная связь классифицирована;
- [ ] новые feature requests помещены в backlog, а не добавлены в MVP;
- [ ] release имеет tag и changelog.

---

## Итерация 17. Open-source и портфолио-упаковка

**Цель:** превратить работающую систему в сильный инженерный кейс для GitHub и интервью.

**Теория**

- technical storytelling;
- architecture decision communication;
- open-source project hygiene;
- onboarding contributors;
- demo-driven portfolio;
- описание trade-offs и lessons learned.

**Практика**

- переработать README на русском и английском;
- добавить screenshots и короткое demo;
- описать проблему, решение, архитектуру и локальный запуск;
- добавить C4, ER и ключевые sequence diagrams;
- оформить roadmap, changelog, license и contributing guide;
- описать сложные инженерные решения и компромиссы;
- подготовить portfolio case study;
- проверить запуск проекта человеком, не участвовавшим в разработке.

**Артефакты**

- production-quality README RU/EN;
- architecture documentation;
- demo video/GIF;
- case study;
- contributor onboarding;
- публичный release `v1.0.0` после выполнения критериев MVP.

**Definition of Done**

- [ ] новый разработчик запускает проект по README;
- [ ] назначение проекта понятно за первые 30 секунд;
- [ ] архитектурные решения объяснены через trade-offs;
- [ ] demo показывает полный основной сценарий;
- [ ] репозиторий не содержит временных секретов и мусора;
- [ ] проект готов быть указан как ключевая работа в резюме.

---

## Итерация 18. Финальная архитектурная защита

**Цель:** подтвердить, что проект не только реализован, но и полностью понятен автору.

**Теория для повторения**

- frontend architecture и FSD;
- React rendering и state management;
- Node.js и API lifecycle;
- authentication и security;
- PostgreSQL, индексы и транзакции;
- caching и consistency;
- тестовая стратегия;
- CI/CD и migration safety;
- observability, SLO и incident response;
- масштабирование системы.

**Практика**

- провести 60–90-минутную mock system design защиту;
- объяснить систему от пользовательского запроса до БД;
- разобрать минимум три production-инцидента;
- спроектировать рост нагрузки в 10 и 100 раз;
- объяснить, когда модульный монолит перестанет подходить;
- провести code review случайно выбранного модуля;
- решить практическую задачу на изменение требования;
- составить финальный gap analysis.

**Артефакты**

- defense questions and answers;
- scaling plan;
- incident scenarios;
- final gap analysis;
- retrospective.

**Definition of Done**

- [ ] каждое ключевое решение объясняется без «так принято»;
- [ ] понятны слабые места и границы системы;
- [ ] предложенное масштабирование основано на измерениях и bottlenecks;
- [ ] изменение требования раскладывается по frontend, API, data и operations;
- [ ] финальная ретроспектива содержит конкретные lessons learned;
- [ ] сформирован следующий учебный план вне рамок этого проекта.

## 9. Сквозные требования ко всем итерациям

### Код

- TypeScript strict mode;
- понятные границы модулей;
- отсутствие `any` без зафиксированного обоснования;
- небольшие PR;
- self-review перед merge;
- отсутствие закомментированного и мёртвого кода;
- изменения сопровождаются необходимыми тестами и документацией.

### API

- runtime-валидация входа;
- единый формат ошибок;
- документированный OpenAPI-контракт;
- authorization по умолчанию запрещает доступ;
- breaking changes принимаются осознанно;
- чувствительные данные не возвращаются случайно.

### Database

- изменения только через migrations;
- бизнес-критичные инварианты дублируются ограничениями БД, где возможно;
- индексы создаются под реальные запросы;
- удаление и cascade rules определяются явно;
- production data не используется в тестах.

### Frontend и FSD

- слой импортирует только нижележащие слои;
- slices одного слоя не связываются напрямую без обоснованного механизма;
- public API slices обязателен;
- `shared` не становится хранилищем бизнес-логики;
- новые `entities`, `features` и `widgets` создаются только при реальной семантической роли;
- UI отображает loading, empty, success, validation и error states.

### Security и privacy

- секреты никогда не хранятся в Git;
- персональные данные минимизируются;
- логи не содержат credentials и session identifiers;
- все endpoints проходят проверку authentication/authorization;
- зависимости регулярно проверяются;
- новые внешние интеграции проходят threat review.

### Documentation

- ADR создаётся до или одновременно с существенным решением;
- диаграммы обновляются при изменении архитектуры;
- README отражает фактический способ запуска;
- незавершённые вопросы находятся в одном реестре;
- документация не подменяет исполняемые проверки там, где проверку можно автоматизировать.

## 10. Обязательные контрольные точки

| Checkpoint | После итерации | Формат проверки |
| --- | ---: | --- |
| Product review | 2 | защита требований, модели и scope |
| Foundation review | 4 | запуск чистого окружения и разбор каркаса |
| Security review I | 5 | threat model и проверка auth flow |
| Architecture review I | 7 | FSD, backend modules, SQL и транзакции |
| Functional MVP review | 10 | полный E2E пользовательский сценарий |
| Quality review | 13 | tests, security, a11y и performance |
| Operational readiness review | 15 | deploy, monitoring, backup и incident drill |
| Product release review | 16 | проверка реального production MVP |
| Portfolio review | 17 | README, demo и case study |
| Final defense | 18 | mock interview и system design defense |

## 11. Product Backlog после MVP

Порядок элементов здесь не означает обязательство реализации.

| Возможность | Что потребуется дополнительно изучить |
| --- | --- |
| GitHub import | OAuth, external API limits, webhooks, sync conflicts |
| AI translation/adaptation | LLM contracts, prompt injection, evaluation, cost controls |
| PDF export | print CSS, browser rendering, document fidelity |
| Custom domains | DNS, TLS, domain verification, multi-tenancy routing |
| View analytics | privacy, event model, bot filtering, aggregation |
| Password-protected views | resource passwords, rate limits, link sharing threats |
| Image uploads | object storage, presigned URLs, content validation, lifecycle |
| Billing | subscriptions, webhooks, idempotency, entitlements |
| Templates marketplace | moderation, versioning, sandboxing, licensing |

## 12. Parking Lot

Сюда добавляются идеи, возникшие во время текущих итераций. Они не меняют scope автоматически.

| ID | Идея | Когда появилась | Решение |
| --- | --- | --- | --- |
| PL-001 | — | — | — |

## 13. Прогресс

| Итерация | Статус | Плановая оценка | Начало | Завершение | Результат/ссылка | Блокеры |
| ---: | :---: | --- | --- | --- | --- | --- |
| 0 | `[ ]` | 2–4 занятия | — | — | — | — |
| 1 | `[ ]` | 4–6 занятий | — | — | — | — |
| 2 | `[ ]` | 4–6 занятий | — | — | — | — |
| 3 | `[ ]` | 3–5 занятий | — | — | — | — |
| 4 | `[ ]` | 4–6 занятий | — | — | — | — |
| 5 | `[ ]` | 6–9 занятий | — | — | — | — |
| 6 | `[ ]` | 5–8 занятий | — | — | — | — |
| 7 | `[ ]` | 8–12 занятий | — | — | — | — |
| 8 | `[ ]` | 6–9 занятий | — | — | — | — |
| 9 | `[ ]` | 5–8 занятий | — | — | — | — |
| 10 | `[ ]` | 7–10 занятий | — | — | — | — |
| 11 | `[ ]` | 5–8 занятий | — | — | — | — |
| 12 | `[ ]` | 4–7 занятий | — | — | — | — |
| 13 | `[ ]` | 5–8 занятий | — | — | — | — |
| 14 | `[ ]` | 5–8 занятий | — | — | — | — |
| 15 | `[ ]` | 5–8 занятий | — | — | — | — |
| 16 | `[ ]` | 4–6 занятий | — | — | — | — |
| 17 | `[ ]` | 4–7 занятий | — | — | — | — |
| 18 | `[ ]` | 3–5 занятий | — | — | — | — |

> Оценка указана в занятиях, а не в календарных неделях. Одно занятие — сфокусированная рабочая сессия примерно 1–2 часа. Оценка нужна для масштаба и может меняться без изменения сути итерации.

## 14. Шаблон завершения итерации

После каждой итерации добавляется запись:

```md
### Итерация N — название

- Статус: завершено
- Дата начала:
- Дата завершения:
- Что изучено:
- Что реализовано:
- Какие проверки выполнены:
- Ссылки на PR/документы:
- Что оказалось сложнее ожидаемого:
- Какие пробелы обнаружены:
- Что перенесено в Parking Lot:
- Изменения сроков:
- Изменения содержания: нет / ссылка на Change Request
```

## 15. Управление изменениями

### 15.1. Не требуют отдельного содержательного согласования

- изменение длительности итерации;
- дробление крупной задачи на подзадачи;
- перестановка задач внутри одной итерации, если не нарушены зависимости;
- исправление дефектов и уязвимостей;
- замена patch/minor версии библиотеки;
- уточнение формулировки без изменения результата;
- добавление теста или автоматической проверки.

### 15.2. Требуют отдельного обсуждения

- изменение продуктовой цели;
- добавление или исключение возможностей MVP;
- изменение последовательности этапов, влияющее на учебную логику;
- отказ от FSD;
- объединение frontend и backend во full-stack framework;
- смена backend runtime или основной БД;
- переход к микросервисам;
- исключение security, testing, CI/CD или observability контура;
- добавление billing, AI или внешней интеграции в MVP.

### 15.3. Шаблон Change Request

```md
## CR-NNN: краткое название

- Дата:
- Инициатор:
- Что предлагается изменить:
- Причина:
- Пользовательская/учебная ценность:
- Какие итерации затрагиваются:
- Риски:
- Альтернативы:
- Решение: принято / отклонено / отложено
- Изменения дорожной карты:
```

## 16. Журнал изменений дорожной карты

| Версия | Дата | Изменение | Причина |
| --- | --- | --- | --- |
| 0.1 | 2026-08-15 | Создана максимальная дорожная карта проекта | Первичная фиксация режима, содержания и последовательности работы |

## 17. Текущая следующая задача

После согласования этой дорожной карты начинается **Итерация 0: Инициализация процесса**.

До начала реализации кода необходимо:

1. выбрать название проекта;
2. определить репозиторий;
3. создать минимальный workflow задач и решений;
4. перенести дорожную карту в `docs/roadmap.md`;
5. провести короткую проверку понимания процесса.

# Digital Student Assistant - code context

## Runtime

Основной runtime состоит из:

- `src/web` - Django + DRF backend и Django templates frontend;
- `src/ml` - FastAPI reference ML service;
- `src/graph` - FastAPI graph service с Neo4j;
- `infra` - Docker Compose, Nginx, deployment scripts;
- `tests` - repository-level contract, integration и e2e проверки.

## Web modules

| Module | Responsibility |
| --- | --- |
| `apps.base` | auth adapters, token auth, shared health/readiness, seed command |
| `apps.users` | user profile, role, interests, favorites, email verification |
| `apps.projects` | ЭПП/Project model, project catalog, project workflow, initiative proposals, import helpers |
| `apps.applications` | student applications and review workflow |
| `apps.account` | role-based student/customer/cpprp cabinet endpoints |
| `apps.imports` | ЭПП XLSX import API |
| `apps.outbox` | event feed, ack, checkpoint, snapshot |
| `apps.recs` | recommendation/search facade over ML service with reserved keyword ranking |
| `apps.faculty` | HSE faculty persons, publications, courses and project-supervisor matching |
| `apps.frontend` | Django template views and forms |

## Recent important changes

- Added `django-unfold` dependency and admin UI improvements.
- Added email verification for signup and token access.
- Added SMTP/console email settings and cleanup command for verification codes.
- Added `faculty` domain with models: `FacultyPerson`, `FacultyPublication`,
  `FacultyAuthorship`, `FacultyCourse`, `FacultySyncState`,
  `ProjectFacultyMatch`.
- Expanded outbox snapshot resources with faculty data.
- Expanded event contract with faculty and project-faculty-match events.
- Added env sync script for VM configuration.

## Documentation stance

Generated documents must treat the current technical specification, code and
contracts as mutually checked sources. They must not claim production SSO,
Kafka or SSE/Chunked LLM behavior as an acceptance requirement unless the team
confirms it separately. The documented scope is REST/JSON, Django sessions/token
auth with email verification, outbox delivery, ML service, graph projection,
faculty mirror/matching and deployable Docker Compose stack.

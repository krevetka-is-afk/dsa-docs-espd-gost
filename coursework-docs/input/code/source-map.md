# Source map for generated documentation

Use these files as the main source map when writing PZ, PMI and RO.

## Product and architecture

- `README.md`
- `docs/api_scheme.md`
- `docs/structure_of_project.md`
- `docs/architecture/adr/ADR-001.md`
- `docs/architecture/adr/ADR-002.md`
- `docs/architecture/connector-boundary.md`
- `docs/architecture/ml-integration-handover.md`

## Contracts

- `docs/architecture/contracts/api_contract.json`
- `docs/architecture/contracts/event_contract.json`
- `docs/architecture/contracts/outbox_delivery_contract.json`

## Web source

- `src/web/config/settings/base.py`
- `src/web/config/settings/prod.py`
- `src/web/config/api_v1_urls.py`
- `src/web/apps/users/models.py`
- `src/web/apps/users/email_verification.py`
- `src/web/apps/projects/models.py`
- `src/web/apps/projects/transitions.py`
- `src/web/apps/projects/importers.py`
- `src/web/apps/applications/transitions.py`
- `src/web/apps/account/views.py`
- `src/web/apps/outbox/services.py`
- `src/web/apps/outbox/views.py`
- `src/web/apps/recs/services.py`
- `src/web/apps/faculty/models.py`
- `src/web/apps/faculty/services.py`
- `src/web/apps/faculty/views.py`
- `src/web/apps/frontend/views/auth.py`
- `src/web/templates/frontend/*.html`

## ML and graph source

- `src/ml/app/main.py`
- `src/ml/app/index_store.py`
- `src/ml/app/projector.py`
- `src/graph/app/main.py`
- `src/graph/app/graph_store.py`
- `src/graph/app/projector.py`

## Deployment and operations

- `infra/docker-compose.yml`
- `infra/docker-compose.prod.yml`
- `infra/docker-compose.staging.yml`
- `infra/.env.prod.example`
- `infra/.env.staging.example`
- `infra/nginx/default.conf`
- `scripts/run-release-gate.sh`
- `scripts/backup-postgres.sh`
- `scripts/restore-postgres.sh`
- `infra/sync-env-to-vm.sh`

## Tests

- `tests/contract`
- `tests/integration`
- `tests/e2e`
- `src/web/apps/*/tests`
- `src/ml/tests`
- `src/graph/tests`

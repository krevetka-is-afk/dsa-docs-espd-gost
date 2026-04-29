# Release and quality context

## Canonical commands

```bash
uv sync --all-packages --group dev
./scripts/run-release-gate.sh
./scripts/uv-linters.sh
./scripts/uv-typecheck.sh
```

## Release contract sources

- `docs/architecture/contracts/api_contract.json`
- `docs/architecture/contracts/event_contract.json`
- `docs/architecture/contracts/outbox_delivery_contract.json`

## Contract checks

- OpenAPI is generated from Django/DRF and checked against `api_contract.json`.
- Current `emit_event(...)` surface is checked against `event_contract.json`.
- Outbox delivery semantics are tested for polling, ack and checkpoints.

## Main acceptance evidence

For final delivery, report:

- result of release gate without graph skip;
- result of linters;
- result of typecheck;
- Docker Compose config validation;
- smoke endpoints: `/health/`, `/ready/`, `/api/`, `/api/docs/`,
  `/api/v1/`;
- manual scenarios for student, customer and CPPRP.

## Known local caveat

The graph projection integration test requires Neo4j. `ALLOW_LOCAL_GRAPH_SKIP=1`
is only a local development escape hatch, not acceptance evidence.

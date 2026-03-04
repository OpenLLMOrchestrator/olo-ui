# olo-be docs

Backend-specific documentation. For run and build instructions, see [olo-be/README.md](../README.md).

## API

- Base path: `/api/v1/`
- Health: `GET /api/v1/health`
- Tenants: `GET /api/v1/tenants` (and related CRUD via dropdown/tenant endpoints)
- All endpoints are versioned under `/api/v1/`; see [STABILITY.md](../../docs/STABILITY.md) (in repo root docs) for versioning and deprecation.

## Configuration

- **Redis (optional):** Set env `OLO_TENANT_IDS` (e.g. `olo:tenants`) for the Redis key. If Redis is disabled or unavailable, the backend uses an in-memory tenant store (data lost on restart).
- **Port:** 8082 (configurable via Spring Boot).

## Repo root docs

Shared architecture and contributor docs live at the repository root [docs/](../../docs/) (e.g. ARCHITECTURE.md, STABILITY.md). The combined Docker image is built from repo root; see root [README.md](../../README.md) and [.github/workflows/docker-publish.yml](../../.github/workflows/docker-publish.yml).

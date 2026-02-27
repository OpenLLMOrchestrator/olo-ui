# olo-be

Spring Boot REST backend for Olo.

## Requirements

- Java 17+
- Maven 3.6+

## Run

```bash
./mvnw spring-boot:run
```

Or on Windows:

```bash
mvnw.cmd spring-boot:run
```

API runs at `http://localhost:8082`. All endpoints are versioned under `/api/v1/` (e.g. health: `GET /api/v1/health`, tenants: `GET /api/v1/tenants`).

## Tenant list: Redis and in-memory fallback

- **With Redis:** Set env `OLO_TENANT_IDS` (e.g. `olo:tenants`) for the Redis key. Tenant list is read/written there.
- **Without Redis:** If Redis is disabled or unavailable, the backend uses an **in-memory tenant store**. Tenant CRUD works; data is lost on restart. No Redis is required for first-run or local contribution.

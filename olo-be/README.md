# olo-be

Spring Boot REST backend for Olo.

## Requirements

- Java 17+
- Gradle 8.5+ (or use the wrapper: `./gradlew` / `gradlew.bat` after running `gradle wrapper` once if the wrapper jar is missing)

## Build

```bash
./gradlew build
# or: gradle build
```

## Run

```bash
./gradlew bootRun
```

Or on Windows:

```bash
gradlew.bat bootRun
```

API runs at `http://localhost:8082`. All endpoints are versioned under `/api/v1/` (e.g. health: `GET /api/v1/health`, tenants: `GET /api/v1/tenants`).

## Tenant list: Redis and in-memory fallback

- **With Redis:** Set env `OLO_TENANT_IDS` (e.g. `olo:tenants`) for the Redis key. Tenant list is read/written there.
- **Without Redis:** If Redis is disabled or unavailable, the backend uses an **in-memory tenant store**. Tenant CRUD works; data is lost on restart. No Redis is required for first-run or local contribution.

## Docs

See [docs/](docs/) for API and configuration notes and links to repo root docs.

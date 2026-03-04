# Olo

Backend (olo-be) and frontend (olo-ui) for Olo. **This directory is the repository root.** It contains both projects; they can run as a **single Docker image** (combined container) or separately for development.

## Repository layout

- **Repo root** (this directory): `Dockerfile`, combined run scripts, and CI (`.github/workflows/`).
- **olo-be/** — Spring Boot REST API (Java 17+, Gradle).
- **olo-ui/** — React frontend (TypeScript, Vite, Gradle build).
- **docs/** — Architecture, domain boundaries, and contributor guides (shared).

## Combined Docker image (olo-be + olo-ui in one container)

From this directory (repo root, containing `olo-be/` and `olo-ui/`):

```bash
docker build -t olo -f Dockerfile .
docker run -p 3000:80 olo
```

Then open **http://localhost:3000**. Nginx serves the UI and proxies `/api` to the Spring Boot backend inside the same container.

- **Build:** Backend and frontend are built with Gradle; runtime is Eclipse Temurin 17 JRE + nginx.
- **Entrypoint:** Starts olo-be in the background, then nginx in the foreground.

## Development (run backend and frontend separately)

- **Backend:** See [olo-be/README.md](olo-be/README.md) — Java 17+, Gradle, `./gradlew bootRun` (port 8082).
- **Frontend:** See [olo-ui/README.md](olo-ui/README.md) — Node/Gradle, `npm run dev` (port 3000); ensure olo-be is running for API calls.

## Docker Hub

The combined image is published via GitHub Actions from the **repo root**. See [.github/workflows/docker-publish.yml](.github/workflows/docker-publish.yml). **Docker Hub description:** copy-paste text for the repository page is in [docs/DOCKERHUB-PAGE.md](docs/DOCKERHUB-PAGE.md).

## Docs

- **Repo root:** [docs/](docs/) — architecture, domain boundaries, extensibility, layout contract, performance, stability, test strategy, UI/UX, [Docker Hub description](docs/DOCKERHUB-PAGE.md).
- **Frontend:** [olo-ui/README.md](olo-ui/README.md) and [olo-ui/docs/](olo-ui/docs/).
- **Backend:** [olo-be/README.md](olo-be/README.md) and [olo-be/docs/](olo-be/docs/).

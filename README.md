# Olo

Backend (olo-be) and frontend (olo-ui) for Olo. This repo contains both; they can run as a **single Docker image** (combined container) or separately for development.

## Combined Docker image (olo-be + olo-ui in one container)

From this directory (repo root, containing `olo-be/` and `olo-ui/`):

```bash
docker build -t olo -f Dockerfile .
docker run -p 3000:80 olo
```

Then open **http://localhost:3000**. Nginx serves the UI and proxies `/api` to the Spring Boot backend inside the same container.

- **Build:** Backend is built with Maven, frontend with Gradle (Node plugin); runtime is Eclipse Temurin 17 JRE + nginx.
- **Entrypoint:** Starts olo-be in the background, then nginx in the foreground.

## Development (run backend and frontend separately)

- **Backend:** See [olo-be/README.md](olo-be/README.md) — Java 17+, Maven, `./mvnw spring-boot:run` (port 8082).
- **Frontend:** See [olo-ui/README.md](olo-ui/README.md) — Node/Gradle, `npm run dev` (port 3000); ensure olo-be is running for API calls.

## Docker Hub

The combined image is published via GitHub Actions. See [olo-ui/.github/workflows/docker-publish.yml](olo-ui/.github/workflows/docker-publish.yml). Copy-paste text for the Docker Hub repository page: [olo-ui/docs/DOCKERHUB-PAGE.md](olo-ui/docs/DOCKERHUB-PAGE.md).

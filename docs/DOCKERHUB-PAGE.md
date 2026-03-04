# Docker Hub repository description

Copy-paste the text below into your Docker Hub repository **Description** (and **Short description**) so users know how to pull and run the image.

---

## Short description (Docker Hub "Short Description" field)

One-line summary for search and listing:

```
Olo: Spring Boot backend + React frontend in one container. Single image, port 80.
```

---

## Full description (Docker Hub "Description" / README)

Paste this in the full description or README section:

```
Olo — backend (olo-be) + frontend (olo-ui) in one container. Spring Boot API on 8082, nginx serves the React UI and proxies /api to the backend.

Quick start
----------
docker run -p 3000:80 YOUR_DOCKERHUB_USERNAME/olo-ui

Then open http://localhost:3000 . No separate backend container needed.

Tags
----
- latest — built from main
- 1.0.0, 1.0, 1 — semantic versions (use when we publish v1.0.0 etc.)

Source
------
https://github.com/YOUR_ORG_OR_USER/olo-ui
```

---

## Before publishing

Replace placeholders with your own values:

- **YOUR_DOCKERHUB_USERNAME** — your Docker Hub username or organization
- **YOUR_ORG_OR_USER** — your GitHub organization or username (for the source URL)

---

## CI

The image is built and pushed by GitHub Actions from the repo root. See [.github/workflows/docker-publish.yml](../.github/workflows/docker-publish.yml). Configure repository secrets `DOCKERHUB_USERNAME` and `DOCKERHUB_TOKEN` (Docker Hub access token).

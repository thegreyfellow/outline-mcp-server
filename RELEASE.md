# Release & Publishing Process: Docker Image to GHCR

## Tagging and Publishing

1. **Bump version and tag:**

   ```sh
   npm version <patch|minor|major>
   git push --follow-tags
   ```

   This creates a tag like `v1.2.3` and pushes it to GitHub.

2. **GitHub Actions workflow:**
   - The workflow at `.github/workflows/publish.yml` will automatically build and push the Docker image to GHCR with tags:
     - `ghcr.io/<owner>/outline-mcp-server:v1.2.3`
     - `ghcr.io/<owner>/outline-mcp-server:latest`

3. **Pulling the image:**
   ```sh
   docker pull ghcr.io/<owner>/outline-mcp-server:v1.2.3
   ```


# ArchNet Auto-Builds

This repository is a centralized hub for automated builds and releases across the ArchNet ecosystem. It uses GitHub Actions to cross-access and build private repositories.

## Configuration Requirements

To use these workflows, you must configure the following secrets in this repository (**Settings > Secrets and variables > Actions**):

| Secret               | Description                                                                           |
| -------------------- | ------------------------------------------------------------------------------------- |
| `PRIVATE_REPO_TOKEN` | A GitHub Personal Access Token (PAT) with `repo` scope to clone private repositories. |
| `DOCKER_USERNAME`    | Your Docker Hub username.                                                             |
| `DOCKER_PASSWORD`    | Your Docker Hub password or access token.                                             |

## Available Workflows

- **Backend**: Builds the Go-based server and pushes Docker images to Docker Hub.
- **Frontend**: A matrix-based build for the Next.js/Bun monorepo apps (`admin`, `user`, `webapp`, etc.).
- **App**: (Coming soon) Flutter-based cross-platform app builds.

## How it works

These workflows use the `PRIVATE_REPO_TOKEN` to give GitHub Actions permissions to reach into your private codebases without hosting the source code publicly in this repo.

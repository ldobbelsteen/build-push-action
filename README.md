# ghcr-build-push

Reusable GitHub Actions workflow to **build a container image** using [Buildah](https://github.com/containers/buildah) and **push it to GitHub Container Registry (GHCR)**.  

- Builds your image from `./Containerfile`
- Tags it as `:latest`
- Pushes only when running on the **default branch**
- Cleans up untagged images from GHCR automatically

---

## 🔧 Usage

In your repository, create a workflow that calls this reusable workflow:

```yaml
name: CI
on: push

jobs:
  build:
    uses: ldobbelsteen/ghcr-build-push/.github/workflows/build.yml@main

# ghcr-build-push

Reusable GitHub Actions workflow to **build a container image** and **push it to GitHub Container Registry (GHCR)**.  

- Builds images from `./Dockerfile` for both `amd64` and `arm64`
- Tags them as `:latest-amd64` and `:latest-arm64` respectively
- Combines them into a multi-arch tag `:latest`
- Pushes only when running on the **default branch**
- Cleans up any untagged images from GHCR automatically

---

## 🔧 Usage

In your repository, create a workflow that calls this reusable workflow:

```yaml
name: CI
on: push

jobs:
  build:
    uses: ldobbelsteen/ghcr-build-push/.github/workflows/build.yml@multiarch
    permissions:
      contents: read
      packages: write

## Usage

```yaml
name: ci

on: push

permissions:
  contents: read
  packages: write

jobs:
  build:
    uses: ldobbelsteen/ghcr-build-push/.github/workflows/build.yml@v1
```

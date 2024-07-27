# Podman Build & Push

A GitHub action to Build and Push your images with Podman.

## Inputs

### `registry`

The registry you want to push to. Default `"quay.io"`.

### `username`

Your registry username.

### `access_token`

Your registry access token.

### `project_name`

The project name.

### `image_name`

The name of your image.

## Example usage

Here is a default configuration that will build and push the image to `quay.io/my_project/my_image:latest`.

```yaml
---
on:
  - push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Build and push container image
        uses: ucomesdag/container-image-build-push@main
        with:
          registry: quay.io
          username: ${{ secrets.QUAY_IO_USERNAME }}
          access_token: ${{ secrets.QUAY_IO_ACCESS_TOKEN }}
          project_name: my_project
          image_name: my_image:latest
```

# Dokploy Deploy Actions

This repository contains GitHub Actions for deploying projects using Dokploy.

## Features

- Automated deployment with Dokploy
- Easy integration with GitHub workflows

## Usage

To use these actions in your GitHub workflow, add the following to your `.github/workflows/deploy.yml` file:

```yaml
name: Deploy application

on:
  push:
    branches:
      - main

jobs:
  dokploy_deploy:
    uses: jmischler72/dokploy-deploy-actions/.github/workflows/dokploy-deploy-actions.yaml@main
    secrets: 
      DOKPLOY_HOST: ${{ secrets.DOKPLOY_HOST }}
      DOKPLOY_TOKEN: ${{ secrets.DOKPLOY_TOKEN }}
      APPLICATION_ID: ${{ secrets.APPLICATION_ID }}
```

Or for ease of use

```yaml
name: Deploy application

on:
  push:
    branches:
      - main

jobs:
  dokploy_deploy:
    uses: jmischler72/dokploy-deploy-actions/.github/workflows/dokploy-deploy-actions.yaml@main
    secrets: inherit
```

## Secrets

- `DOKPLOY_HOST`: The host ip or domain of your dokploy instance.
- `DOKPLOY_TOKEN`: Create an API token in your profile settings on Dokploy
- `APPLICATION_ID`: Retrieve Application ID by running
  ```bash
  curl -X 'GET' \
    'https://your-domain/api/project.all' \
    -H 'accept: application/json' \
    -H 'Authorization: Bearer <token>'
  ```

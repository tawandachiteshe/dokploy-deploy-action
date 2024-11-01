# Dokploy Deploy Action

This repository contains GitHub Actions for deploying applications using Dokploy.

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
    with:
      PROJECT_NAME: project-name
      APPLICATION_NAME: application-name
    
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
    with:
      PROJECT_NAME: project-name
      APPLICATION_NAME: application-name
```

## Secrets

- `DOKPLOY_HOST`: The host ip or domain of your dokploy instance.
- `DOKPLOY_TOKEN`: Create an API token in your profile settings on Dokploy

## Inputs

- `PROJECT_NAME`: The name of the project in which the application you want to deploy is in
- `APPLICATION_NAME`: The name of the application you want to deploy


# Dokploy Deploy Action

This repository contains GitHub Actions for triggering deployments of applications in Dokploy. 
This is useful if you want to trigger it after a build/push of your docker image in your CI

## Features

- Trigger deployment on Dokploy
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
    uses: jmischler72/dokploy-deploy-actions@main
    with:
      PROJECT_NAME: project-name
      APPLICATION_NAME: application-name
      DOKPLOY_HOST: ${{ secrets.DOKPLOY_HOST }}
      DOKPLOY_TOKEN: ${{ secrets.DOKPLOY_TOKEN }}
    
```

## Inputs

- `PROJECT_NAME`: The name of the project in which the application you want to deploy is in
- `APPLICATION_NAME`: The name of the application you want to deploy
- `DOKPLOY_HOST`: The host ip or domain of your dokploy instance.
- `DOKPLOY_TOKEN`: Create an API token in your profile settings on Dokploy
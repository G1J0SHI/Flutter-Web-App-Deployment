# GitHub Action

## Flutter Web App Deployment

### Deploys the Flutter web application to GitHub pages.

#### Usage

```yml
name: "Flutter Web App Deployment"

on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest
    permissions:
      pages: write
      id-token: write
    environment:
      name: github-pages
      url: ${{ steps.cicd.outputs.page-url }}
    steps:
      - uses: g1j0shi/flutter-web-app-deployment@main
        id: cicd
```

#### Input

| Name              | Description                            | Required | Default |
| ----------------- | -------------------------------------- | -------- | ------- |
| working-directory | Working directory for Flutter commands | false    | .       |

#### Output

| Name     | Description                           |
| -------- | ------------------------------------- |
| page-url | URL of the deployed GitHub Pages site |

#### Example

```yml
      ...
      - uses: g1j0shi/flutter-web-app-deployment@main
        id: cicd
        with:
          working-directory: "./awesome_app"
```

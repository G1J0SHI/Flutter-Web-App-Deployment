# GitHub Action

## Flutter Web App Deployment

### Deploys the Flutter web application to GitHub pages.

#### Setup

Before using this action, enable GitHub Pages in your repository:

1. Go to your repository **Settings**
2. Navigate to **Pages** in the left sidebar
3. Under **Build and deployment**, set **Source** to **GitHub Actions**

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

| Name              | Description                            | Required | Default       |
| ----------------- | -------------------------------------- | -------- | ------------- |
| working-directory | Working directory for Flutter commands | false    | .             |
| run-tests         | Whether to run tests before building   | false    | true          |
| build-target      | Target file for Flutter build          | false    | lib/main.dart |

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
          run-tests: false
          build-target: "./lib/app/main.dart"
```

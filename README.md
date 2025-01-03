# GitHub Action

## Flutter Web App Deployment

### Deploys the Flutter web application to GitHub pages.

#### Usage

```yml
name: "Flutter Web App Deployment"

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@main
      - uses: subosito/flutter-action@main
      - uses: g1j0shi/flutter-web-app-deployment@main
```

#### Input

```yml
      ...
      - uses: g1j0shi/flutter-web-app-deployment@main
        with:
          branch: "gh-pages" # The branch where the web app will be deployed.
          href: "/" # The base href for the Flutter web application.
```

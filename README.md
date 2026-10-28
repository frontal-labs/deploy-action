# Frontal Deploy Action

![Frontal Banner](./banner.jpg)

---

## About
This action deploys your feature pipelines to Frontal from GitHub's hosted Actions runners.

This action can be run on `ubuntu-latest` and `macos-latest` 
GitHub Actions runners, and will install and expose a specified version of the 
`frontal` CLI on the runner environment.

---

## Usage

```yaml
steps:
- uses: frontal-labs/deploy-action@v2
  with:
    client-id: ...
    client-secret: ...
```

You can also deploy to branches with this workflow:

```yaml
steps:
- uses: frontal-labs/deploy-action@v2
  with:
    branch: ${{ GITHUB_REF_NAME }}
    client-id: ...
    client-secret: ...
```

---

## Inputs
The action supports the following inputs:

- `client-id`: The Frontal Client ID from the tokens page in your settings.
- `client-secret`: The Frontal Client Secret from the tokens page in your settings.
- `await` (optional): Should this step block until it completes? Defaults to true.
- `branch` (optional): By default, Frontal will deploy to your production environment. With `branch`, your pipelines will deploy to a Frontal branch.
- `version` (optional): The version of `frontal` to install, defaulting to `latest`.
- `api-host` (optional): If you're using a self-hosted deployment, the API host where Frontal is hosted.
- `environment` (optional): The Frontal environment to use. Your token is typically scoped to a single environment, and you won't need to use this parameter.
- `no-promote` (deprecated): By default, Frontal will deploy to your production environment. With `no-promote`, your pipelines will deploy to a preview environment.

---

## License
Apache 2.0

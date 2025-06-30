# Setup Ciao action

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![Release](https://img.shields.io/github/v/release/fabasoad/setup-ciao-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-ciao-action/actions/workflows/functional-tests.yml/badge.svg)
![security](https://github.com/fabasoad/setup-ciao-action/actions/workflows/security.yml/badge.svg)
![linting](https://github.com/fabasoad/setup-ciao-action/actions/workflows/linting.yml/badge.svg)

This action installs [Ciao](http://ciao-lang.org) CLI tool.

## Supported OS

<!-- prettier-ignore-start -->
| OS      |                    |
|---------|--------------------|
| Windows | :x:                |
| Linux   | :white_check_mark: |
| macOS   | :white_check_mark: |
<!-- prettier-ignore-end -->

## Prerequisites

None.

## Inputs

```yaml
- uses: fabasoad/setup-ciao-action@v0
  with:
    # (Optional) Ciao version. Defaults to the latest version.
    version: "1.25.0-m1"
    # (Optional) If "false" skips installation if ciao is already installed. If
    # "true" installs ciao in any case. Defaults to "false".
    force: "false"
    # (Optional) GitHub token that is used to send requests to GitHub API such
    # as getting latest release. Defaults to the token provided by GitHub Actions
    # environment.
    github-token: "${{ github.token }}"
```

## Outputs

<!-- prettier-ignore-start -->
| Name      | Description                       | Example |
|-----------|-----------------------------------|---------|
| installed | Whether ciao was installed or not | `true`  |
<!-- prettier-ignore-end -->

## Example usage

### Workflow configuration

```yaml
name: Test

on: push

jobs:
  setup:
    name: Ciao
    runs-on: ubuntu-latest
    steps:
      - uses: fabasoad/setup-ciao-action@v0
      - name: Run command
        run: ciao list
```

### Result

```shell
Run ciao list
builder
core
```

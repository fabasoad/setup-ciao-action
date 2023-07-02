# Setup Ciao action

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![Release](https://img.shields.io/github/v/release/fabasoad/setup-ciao-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-ciao-action/actions/workflows/functional-tests.yml/badge.svg)
![pre-commit](https://github.com/fabasoad/setup-ciao-action/actions/workflows/pre-commit.yml/badge.svg)

This action installs [Ciao](http://ciao-lang.org) CLI tool.

Supported OS: Linux and macOS.

## Inputs

<!-- prettier-ignore-start -->
| Name    | Required | Description                                                                                 | Default     | Possible values |
|---------|----------|---------------------------------------------------------------------------------------------|-------------|-----------------|
| version | No       | Version of `Ciao` tool that can be found [here](https://github.com/ciao-lang/ciao/releases) | `1.22.0-m5` | &lt;String&gt;  |
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
      - uses: actions/checkout@main
      - uses: fabasoad/setup-ciao-action@main
      - name: Run command
        run: ciao list
```

### Result

```shell
Run ciao list
builder
core
```

# Setup Ciao action

![Release](https://img.shields.io/github/v/release/fabasoad/setup-ciao-action?include_prereleases)
![Functional Tests](https://github.com/fabasoad/setup-ciao-action/workflows/Functional%20Tests/badge.svg)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/fabasoad/setup-ciao-action/main.svg)](https://results.pre-commit.ci/latest/github/fabasoad/setup-ciao-action/main)

This action installs [Ciao](http://ciao-lang.org) CLI tool.

Supported OS: Linux and macOS.

## Inputs

| Name    | Required | Description                                                                                 | Default     | Possible values |
|---------|----------|---------------------------------------------------------------------------------------------|-------------|-----------------|
| version | No       | Version of `Ciao` tool that can be found [here](https://github.com/ciao-lang/ciao/releases) | `1.22.0-m1` | &lt;String&gt;  |

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
        with:
          version: 1.22.0-m1
      - name: Run command
        run: ciao list
```

### Result

```shell
Run ciao list
builder
core
```

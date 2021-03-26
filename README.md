# pre-commit-golang

[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

Pre-commit hooks for Golang

## About

This repository was inspired by [dnephin/pre-commit-golang](https://github.com/dnephin/pre-commit-golang) which was not being maintained.

Most hooks were being centralized into [`golangci-lint`](https://github.com/golangci/golangci-lint) and therefore this repository does not contain all the hooks from the source repository.

## Setup

These pre-commit hooks require [`golangci-lint`](https://github.com/golangci/golangci-lint) and `golang`

## Usage

To use these hooks, add a `.pre-commit-config.yaml` to your repository:

```yaml
repos:
  - repo: git://github.com/bellese/pre-commit-golang
    rev: master
    hooks:
      - id: go-mod-tidy
      - id: golangci-lint
```

### Available Hooks

- `go-mod-tidy` - run `go mod tidy -v`, requires golang
- `golangci-lint` - run `golangci-lint run`, requires [`golangci-lint`](https://github.com/golangci/golangci-lint)
  - Can be configured via `args` documented here: [`golangci-lint` Configuration](https://golangci-lint.run/usage/configuration/). See the [Examples](/examples) directory for an example configuration.

# Example

One usage pattern would be to include `.golangci.yaml` configuration files in your repository and configure the `golangci-lint` hook to use them:

```yaml
repos:
  - repo: https://github.com/bellese/pre-commit-golang
    rev: master
    hooks:
      - id: go-mod-tidy
      - id: golangci-lint
        name: WARNING-ONLY golangci-lint findings
        verbose: true
        args: [-c, .golangci.warn.yaml]
      - id: golangci-lint
        name: REQUIRED golangci-lint findings
        args: [-c, .golangci.yaml]
```

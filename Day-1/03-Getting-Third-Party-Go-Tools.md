# Getting Third-Party Go tools 
---
# Key concepts

## Go Tool Installation Method
- In Go, external tools are often distributed and installed directly from there soource code repositories (like GitHub), not from a centralized package registry.
- The `go install` command fetches, builds, and installs the tool in your workspace specifically in the `$GOPATH/bin` directory.
- Syntax to install a tool (e.g., The HTTP load testing tool "hey"):
    ```bash
    go install github.com/rakyll/hey@latest
    ```
    This downloads all dependencies, compiles, and places the binary in `$GOPATH/bin`.
- Once installed, you can run the tool directly --- for example:
    ```bash
    hey https://www.golang.org
    ```

## Version Management
- Add `@latest` to get the newest version, or specify a particular version (like `@v1.4.0`).
- To update a tool, rerun `go install` with a newer version or `@latest` as the suffix

## What happens during Installation
- The Go tool may download code either from a proxy server or directly from the repository (like GitHub), depending on your configuration.
- If downloading directly, you will need git or or other relevant tools installed on your system.
- Installed excutable are just regular binaries --- you can move them or distribute them like any other compiled program.

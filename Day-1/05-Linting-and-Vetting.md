# Linting and vetting 
---
# Key Concepts

## Linting with golint
- **golint** is a tool that checks Go code for style guide violations and suggests improvements, such as naming conventions, proper error message formatting, and required comments for exported types or methods.
- These are not errors --- golint's suggestions won't prevent compilation or break the program; however, following them makes code more idiomatic and easier for other Go developers to read.
- golint may sometimes be inaccurate (false positives/negatives), so use its advice but don’t always treat it as a requirement.
- Install golint:
    ```bash
    go install golang.org/x/lint/golint@latest
    ```
    Run it on your project:
    ```bash
    golint ./...
    ```

## Vetting with go vet
- go vet looks for suspicious code that compiles but is likely incorrect—such as wrong arguments in formatting strings or unused variables.
- These issues aren't always syntax errors, but they do often reflect bugs or misunderstandings.
- Run go vet with:
    ```bash
    go vet ./...
    ```

## Combined Tools: golangci-lint
- golangci-lint lets you run multiple linters (including golint and go vet) and other analysis tools simultaneously.
- You can customize which linters to use and their settings by creating a `.golangci.yml` configuration file in your project root.
- Run golangci-lint:
    ```bash
    golangci-lint run
    ```
- Running many tools at once can slow your build, and team members may disagree on which rules are necessary—adjust your `.golangci.yml` accordingly.



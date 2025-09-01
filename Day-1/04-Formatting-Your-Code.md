# Formaatting your code
---
# Key Concepts

## Standardized code formatting 
- Go was designed for efficient and consistent code writing, leading to a single official code style.
- Unlike most languages, Go does not allow flexibility in formatting: tabs are mandatory and braces must be on the same line as the statement that opens a block.

## go fmt Command
- The built-in `go fmt` tool automatically reformats code to match the Go standard style --- for indentation, spacing, and lining up struct feilds.
- Developers don't need to argue over formatting conventions, saving time and avoiding format wars.

## goimports Tool
- An imporved tool, goimports, not only formats code but also sorts and cleans up import statements -- putting them in alphbatical order and removing unused imports.
- Install goimports with:
    ```bash
    go install golang.org/x/tools/cmd/goimports@latest
    ```
    Run it accross your project with:
    ```bash
    goimports -l -w .
    ```
    * `-l` prints which files are incorrectly formatted.
    * `-w` rewrites files in place.
    * `.` covers all files in the current and nested directories.

## Semicolon Insertion Rule
- Semicolon are required at the end of every statement in Go, but the compiler inserts them automatically based on simple rules.
- If a line ends with an identifier, literal or certain keywords or brackets, Go adds a semicolon.
- If you place a brace `{` on a new line, the automatic insertion creates a syntax error. Braces must be on the same line as function or block declarations.


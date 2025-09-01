# Makefile
---
# Key Concepts

## What is a Makefile?
- A Makefile is a script used by the make tool to define and automate build and development tasks.
- It helps avoid “works on my machine” problems by standardizing steps so anyone can run the same commands consistently.

## Sample Makefile Breakdown
- The example Makefile defines several targets (tasks):

    * `fmt` (runs go fmt to format code),

    * `lint` (runs formatting then golint),

    * `vet` (runs formatting then go vet),

    * `build` (runs vet then compiles with go build).

- `.DEFAULT_GOAL := build` means make runs the build target by default if no target is specified.

- Targets can depend on other targets (e.g., build depends on vet), so dependencies run first.

- Commands under each target must be indented with a tab—spaces won’t work.

- `.PHONY` declares targets that aren’t real files/directories to avoid confusion.

## Running the Makefile
- Run simply by typing:
    ```bash
    make
    ```
    This runs formatting, vetting, and building in order.
- Or run specific tasks like:
    ```bash
    make lint
    make vet
    make fmt
    ```
- This ensures essential checks run every time you build, reducing human error.

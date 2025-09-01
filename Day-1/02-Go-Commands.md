# Key Concepts

## The go Command
- The `go` command provides various built-in tools: **compiler, formatter, linter, dependency manager, and test runner**, all accessible from your terminal.
- You use `go` followed by specific subcommands (like `run`, `build`, `fmt`, etc.) to interact with these tools.

## go run
- `go run` compiles and runs your go code immediately, similar to running a script.
- It does not leave a binary (executable) file behind; the compiled file is stored in a temporary location and deleted after execution.
- Example usage:
    ```bash
    go run hello.go
    ```
    This prints "Hello, World" in the terminal, provided your code is in `hello.go` as shown.

    ```go
    package main
    import "fmt"

    func main(){
        fmt.Println("Hello, World")
    }
    ```
- Use `go run` for quick testing or script like usage.

## go build
- `go build` compiles your Go code and creates an executable binary in your current directory --- The file stays until you delete it.
- Example Usage:
    ```bash
    go build hello.go
    ```
    This creates a binary named `hello` (`hello.exe` on Windows) that you can run later.
- You can specify a name and location with `-o` flag:
    ```bash
    go build -o hello_world hello.go
    ```
- Use `go build` when you want to distribute or reuse the compiled application.
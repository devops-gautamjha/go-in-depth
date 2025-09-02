# Unused Variables

- Go requires that every declared local variable must be read at least once; otherwise, it triggers a compile-time error.
- This rule helps catch bugs and dead code early, making it easier for teams to maintain clean, readable code.
- The Go compiler’s check only ensures that a variable is read, not that every value assigned to it is used.
- For example:
```go
func main() {
    x := 10   // assigned but value not used yet
    x = 20    // value assigned and then read below
    fmt.Println(x)
    x = 30    // assigned value never read
}
```
This program compiles because `x` is read once, but tools like `golangci-lint` can report warnings about ignored assignments (`ineffassign`).
- Package-level unused variables are not reported as errors by the compiler, which reinforces avoiding mutable package-level variables to keep code maintainable.


## Unused Constants Behavior
- Unlike variables, unused constants are allowed by the compiler and do not cause any errors.
- Since constants are evaluated at compile-time and have no side effects, unused constants are simply omitted from the compiled binary.
- This makes unused constants harmless compared to unread variables.


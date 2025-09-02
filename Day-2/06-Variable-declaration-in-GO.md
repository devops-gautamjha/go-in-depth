# Variable Declaration Styles in Go
---
1. `var` with Explicit Type and Assignment
    * The most explicit form:
    ```go
    var x int = 10
    ```
    * Declares variable `x` of type `int`, assigned value `10`.

2. var with Type Inference
    * If the type matches the literal, you can omit the explicit type:
    ```go
    var x = 10  // x is int by default
    ```
   * You can declare a variable with just the type (zero value assigned):

3. Multiple Variable Declarations
    * Same type:
    ```go
    var x, y int = 10, 20
    ```
    * All zero Value
    ```go
    var x, y int
    ```
    * Different Types
    ```go
    var x, y = 10, "hello"
    ```
    * Declaration list for multiple variables:
    ```go
    var (
    x int
    y = 20
    z int = 30
    d, e = 40, "hello"
    f, g string
    )
    ```
4. Short Variable Declaration (`:=`)
    * Used within functions:
    ```go
    x := 10
    ```
    * Equivalent to `var x = 10`.
    * Can declare multiple variables:
    ```go
    x, y := 10, "hello"
    ```
    * Can assign values to existing variables as long as at least one variable is new:
    ```go
    x := 10
    x, y := 30, "hello"  // y is new, x is reassigned
    ```
    * Limit: Short declaration `:=` is not allowed at package level (outside functions).


## When to Use Each Style
- Use `:=` inside functions for concise variable declarations.
- Use `var` at package level or when you want to:
    * Declare a variable with zero value explicitly (`var x int`).
    * Specify a type explicitly different from the default inferred type.
- Avoid `:=` when initializing variables to zero values to clarify intent.
- When assigning to both new and existing variables where shadowing could be a problem, prefer explicit `var` declarations and normal assignment `=`.
- Avoid declaring package-level variables that change value, as this can complicate data flow and lead to subtle bugs.
- Use package-level variables only for effectively immutable values.

## Important Notes
- Declaring variables inside functions maintains clearer data flow.
- Go’s philosophy encourages clear intent and simplicity in variable declarations.




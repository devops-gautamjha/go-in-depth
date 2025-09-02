# Constants

- Use `const` to declare values that cannot be changed after declaration.
- Constants can be declared:
    * At the package level,
    * Inside functions,
    * Or grouped together for related constants with parentheses.
- Attempting to assign a new value to a constant results in a compile-time error (as constants are immutable):
```go
const x int64 = 10
x = x + 1  // compilation error: cannot assign to x
```

## Limitations of Constants
- Constants in Go can only hold values known at compile-time, such as:
    * Numeric literals,
    * Boolean values true and false,
    * Strings,
    * Runes,
    * Certain built-in functions like complex, real, imag, len, and cap,
    * Expressions composed of the above values and operators.
- Go does not support immutable variables whose values are calculated or determined at runtime.
- There are no immutable arrays, slices, maps, or struct fields in Go.
- Go’s approach relies on the language's value semantics to help prevent unwanted modifications.

## Typed vs Untyped Constants
- Untyped constants behave like literals with no fixed type until assigned:
```go
const x = 10  // untyped
var y int = x
var z float64 = x
var d byte = x  // all legal
```
- Typed constants have a fixed type and can only be assigned to variables of the same type:
```go
const typedX int = 10
var f float64 = typedX  // compile error: cannot use typedX (type int) as float64
```
- Use untyped constants for flexibility and typed constants when you want to enforce type constraints (for example, with enumerations using iota, covered later).

## Practical Takeaways
- Use const to give names to fixed literals that should not change.
- Understand that Go’s const is limited to compile-time known values, no runtime immutability enforcement.
- Prefer untyped constants for general use for flexibility.
- Use typed constants to enforce specific type usage when needed.


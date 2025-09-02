# Explicit Type Conversion
---

- Unlike many languages, Go does not automatically convert between numeric types or other mismatched types during operations. Instead, you must explicitly convert variables to the same type to perform operations between them.

- Even variables with different integer sizes (e.g., `int` vs `int64`) or between integers and floats (e.g., `int` and `float64`) require explicit conversion.

- Example:
```go
var x int = 10
var y float64 = 30.2
var z float64 = float64(x) + y     // convert int to float64
var d int = x + int(y)             // convert float64 to int
```
- This explicitness ensures clear intent and prevents subtle bugs caused by implicit conversions or unexpected type promotions.


## Boolean Type Conversion Restrictions
- Go does not allow any kind of conversion to or from booleans besides the boolean type itself.

- No other types (numbers, strings, etc.) can be implicitly or explicitly converted to a boolean.

- Instead of using “truthy” or “falsy” values like other languages, Go requires explicit boolean expressions using comparison operators:
    * To check if an integer `x` is zero: `x == 0`
    * To check if a string `s` is empty: `s == ""`

## Philosophy Behind This Design
- Go prioritizes clarity and simplicity over conciseness.
- Explicit type conversions make the code easier to understand, maintain, and less prone to errors by avoiding hidden or automatic behavior.
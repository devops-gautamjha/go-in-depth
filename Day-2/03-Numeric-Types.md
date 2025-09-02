# Numeric Types
---
# Key Concepts
---
## Integer Types
- Go supports 12 numeric types group broasly with integers divided by:
    * Signed integers (`int8`, `int16`, `int32`, `int64`) with negative and positive ranges.
    * Unsigned integers (`uint8`, `uint16`, `uint32`, `uint64`) represnting zero and positive numbers only.
- The zero value of any integer type is always `0`.

## Special Integer Type Names
- `byte` is an alias for `uint8`, commonly used instead of `uint8`.
- `int` is platform-dependent:
    * On 32-bit CPUs: same as `int32`.
    * On 64-bit CPUs: same as `int64`.
    * Mixing `int` with specific sizes (`int32`, `int64`) without conversion causes compile-time errors.
- `uint` behaves the same as `int` but only holds non-negative values.
- Other special types
    * `rune` (alias for `int32`) for Unicode code points.
    * `uintptr` for unsigned integers large enough to store pointer values.

## Choosing Integer Types
- Use specific integer types (`int8`, `uint16`, etc.) when working with fixed-size data like network protocols or binary file formats.

- For writing generic library functions that should handle any integer size, use `int64` and `uint64` as parameters and variables since Go does not have generics or function overloading.

- In general applications, prefer using int unless there’s a reason to optimize or use a specific size.

## Integer Operators 
- Standard arithmetic operators supported: `+`, `-`, `*`, `/`, and `%` (modulus).

- Integer division truncates towards zero; to get floating point results, a type conversion is needed.

- Division by zero causes a runtime panic.

- Compound assignment operators exist: `+=`, `-=`, `*=`, `/=`, `%=`.

- Comparison operators: `==`, `!=`, `>`, `>=`, `<`, `<=`.

- Bitwise operators: shift left/right (`<<`, `>>`), AND (`&`), OR (`|`), XOR (`^`), AND NOT (`&^`).

- Bitwise compound assignments: `&=`, `|=`, `^=`, `&^=`, `<<=`, `>>=`.


---
## Floating Point Types in Go
- Go offers two floating point types:
    * `float32` with about 6-7 decimal digits precision and a smaller range.
    * `float64` with higher precision (about 15-16 digits) and a much larger range.
- The zero value for floating point types is 0.
- Floating point literals in Go default to float64, and it’s usually recommended to use float64 unless compatibility with a specific format requires otherwise.
- Despite their wide range, floating points cannot represent every value exactly; they store the nearest approximation.

## Important Characteristics and Recommendations
- Go implements floating points according to the IEEE 754 standard, a widely-adopted specification for binary floating point representation used across most languages.
- Floating points break down into:
    * 1 bit for the sign (positive/negative)
    * 11 bits for exponent (base 2)
    * 52 bits for the mantissa (normalized significant digits)
- Because of this representation, floating point numbers cannot exactly represent many decimal values (for example, `-3.1415` is stored as approximately `-3.141500000000000181...`).

## Usage Recommendations
- Avoid using floating point numbers for exact decimal values, such as representing money or other values requiring high precision.
- Floating point math is best suited for fields allowing approximation, like graphics or scientific computations.
- Division behaviors:
    * Dividing a nonzero float by zero results in positive or negative infinity (+Inf or -Inf).
    * Dividing zero by zero yields NaN (Not a Number).
- Although Go allows equality comparisons (==, !=) on floats, it is discouraged because floating point precision issues can make exact comparison unreliable.
- Instead, compare floats by checking if their difference is smaller than a small threshold called epsilon, which depends on the application’s accuracy requirements.

---
## Complex Number Types in Go
- Go has two complex types:
    * `complex64`: uses two `float32` values (for real and imaginary parts).
    * `complex128`: uses two `float64` values.
- Complex numbers are created using the built-in `complex` function, e.g., `complex(2.5, 3.1)` for a number with real part 2.5 and imaginary part 3.1.
- The type of a complex literal depends on the types of its components and literals passed:
    * Untyped constants/default create `complex128`.
    * Float32 values result in `complex64`.
    * Mixed float32 and untyped fitting float32 values create `complex64`.
    * Otherwise, it defaults to complex128.
- Both complex64 and complex128 have a zero value where both real and imaginary parts are 0.

## Working with Complex Numbers
- Supported arithmetic operators: addition, subtraction, multiplication, division, just like other numeric types.
- Equality operators (`==`, `!=`) can be used but have floating point precision limitations; using an epsilon threshold is recommended.
- Extract real and imaginary parts using built-in functions: `real()` and `imag()`.
- The   math/cmplx   package offers additional utilities for complex number operations.
- Complex literals support an imaginary suffix  `i` (e.g., `5i`).

## Usage Notes
- Complex numbers are rarely used in typical Go programming outside specific scientific or mathematical domains.
- Go was not designed for advanced numerical computing; other languages or libraries specialize better here.
- The Go creator Ken Thompson included complex numbers out of interest rather than wide practical use.
- If serious numerical computing is needed, third-party packages like Gonum provide extensive support for operations on complex numbers, matrices, linear algebra, and statistics.

## Example 
```go
x := complex(2.5, 3.1)
y := complex(10.2, 2)
fmt.Println(x + y)          // (12.7+5.1i)
fmt.Println(real(x))        // 2.5
fmt.Println(imag(x))        // 3.1
fmt.Println(cmplx.Abs(x))   // magnitude of x
```




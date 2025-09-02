# Literals
---
# Key Concept

1. Integer Literals
- Represent whole numbers.
- Usually base 10 (decimal), but Go supports other bases:
    * Binary with prefix `0b` or `0B`
    * octal with prefix `0o` or `0O` (preferred over lending zero `0` style which is confusing)
    * Hexadecimal with prefix `0x` or `0X`
- Underscores (_) can be used inside numbers to improve readability (e.e., `1_234`), but not at the start, end or consecutively. 

2. Floating-Point Literals
- Numbers with decimal points and optional exponent (e.g., 6.03e23).
- Can be written in hexadecimal form with `0x` prefix and use `p` to indicate exponent.
- Underscores also allowed for readability.

3. Rune Literals
- Represent single characters enclosed in single quotes (`'a'`)
- Supports Unicode characters in various formats such as octal, hex, and Unicode code points.
- Includes escapse sequences like newline (`'\n`), tab (`'\t'`), quote characters, and backslash

4. String Literals
- Two forms:
    * **Interpreted strings:** double quotes (`"text"`) where escape sequences are interpreted (for newlines, quotes, etc.).
    * **Raw strings:** backquotes (`text`), preserving literal content including newlines without processing escape sequences.

## Practical Usage Guidance
- Prefer base-10 for numbers unless working with networking or bitmasking where binary, hex, or octal are more meaningful.
- Avoid old-style leading-zero octal literals because they are confusing
- Use underscores in literals sparingly to enhance readability, like grouping digits in thousands or breaking binary/hex into byte-sized chunks.
- For strings, use interpreted strings the majority of the time; use raw strings when you want to include literal newlines or escape characters easily.

## Untyped Literals and Type Conversion
- Literals in Go are untyped; they do not have a fixed type until assigned or used in an expression.

- Being untyped lets literals be flexible, working with any compatible variable type without explicit conversion (e.g., integer literals can be used in floating-point expressions).

- However, Go enforces type safety—you cannot mix incompatible literal types (e.g., assign a string literal to a number variable).

- There are limits: assigning a literal to a variable with insufficient capacity (e.g., the literal 1000 to a byte) causes a compile-time error.

- When no explicit type is declared, Go assigns a default type to the literal depending on context and built-in type rules.


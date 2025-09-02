# Go’s Rules for Naming Identifiers

- Names must start with a letter or underscore.
- Names can contain letters, digits, and underscores.
- Letters and digits include all Unicode letters and digits, not just ASCII.
- Examples like `_0`, Unicode subscripts (`_𝟙`), Greek letters (`π`), or fullwidth characters (`ａ`) are valid but not recommended because they:
    *  Are confusing or hard to type on some keyboards,
    *  Can easily be confused with similar-looking characters,
    *  Hurt code readability and maintenance.



## Idiomatic Naming Conventions
- Avoid confusing Unicode characters or unusual symbols for variable names.
- Avoid snake_case (`index_counter`, `number_tries`), which is rare in Go.
- Prefer camelCase for multi-word variable names (`indexCounter`, `numberTries`).
- The underscore `_` by itself is a special identifier with unique use (covered later).

## Naming Constants
- Unlike many languages that use uppercase snake_case for constants, Go does not use all uppercase for constants.

- Case sensitivity in Go also impacts package-level visibility: names starting with uppercase letters are exported outside the package, while lowercase names are package-private.

## Variable Naming Scope and Style
- Inside functions (small scope), use short variable names, often single letters:
    * Common loop variables: i, j (indices), k, v (key, value).

    * Use the first letter of the type as variable names: i for integers, f for floats, b for booleans.

- Short names keep code concise and serve as a signal for code complexity—if short names become confusing, the code may be doing too much.
- At the package level (wider scope), use more descriptive names (without type hints) so that the purpose is clear.

## Example of Problematic Naming
Different-looking Unicode characters can create confusing code:
```go
ａ := "hello"  // fullwidth 'a' (U+FF41)
a := "goodbye" // regular 'a' (U+0061)
fmt.Println(ａ)
fmt.Println(a)
```

Output:
```
hello
goodbye
```
Though these look similar, they are different variables, which can cause maintenance headaches.
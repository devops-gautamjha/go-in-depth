# A Taste of Strings and Runes
---

# Key Concepts

- Strings are a built-in type that holds sequences of characters and support Unicode, allowing any Unicode character to be included.
- The zero value of a string is the empty string (`""`).
- Strings are compared using `==` for equality, `!=` for difference, and order comparisons (`>`, `<`, `>=`, `<=`) are also supported.
- Strings are concatenated using the `+` operator.
- Strings are immutable—once a string is assigned a value, that value cannot be changed. Instead, you can reassign the variable to a new string.
- The `rune` type represents a single Unicode code point and is an alias for `int32`.
- Runes are best used when referring to individual characters to clarify intent, even though they are technically the same as `int32`.
- String literals default to type `string`; rune literals default to type `rune`.



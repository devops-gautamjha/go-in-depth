# Intro
When choosing how to use language features or syntax, clarity -- making your code easy to understand and maintain -- should guide your decisions.
---
# key Concepts
---
## Built-in Types in Go
- Go provides all the standard data types you might expect: booleans (true/false), integers (like 1,2,3), floating-point numbers (decimals) and strings (text).
- The way Go uses these types is similar to other languages, but there are subtle differences -- especially in defaults and best practices.

## Writing Clear Code
- Go encourages you to write code so anyone can easily tell what you mean -- clarity is valued over cleverness.
- When learning Go, focus on simple and direct solutions rather than complicated or obscure tricks from other languages.

## The zero value
- Every variable in Go, when declared but not given a value, automatically gets a zero value.
- The zero value is a safe default:
    * `0` for numbers (like `int`, `float64`)
    * `""` for strings (empty string)
    * `false` for booleans
- This avoids bugs common in languages like C/C++ where uninitilized variables can contain random ("garbage") data.


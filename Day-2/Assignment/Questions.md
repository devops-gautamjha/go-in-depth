## Theoretical Questions

1. What is the zero value of a boolean, integer, floating point, and string in Go?  
2. What are the four common kinds of literals in Go?  
3. How does Go allow underscores in numeric literals, and what are the rules for their placement?  
4. Why should floating point numbers not be used for representing money values in Go?  
5. What are the two floating point types in Go and which one is recommended for use?  
6. What is IEEE 754, and how does it relate to floating point types in Go?  
7. What is the difference between typed and untyped constants in Go?  
8. Why does Go require explicit type conversion instead of automatic type promotion?  
9. What are the integer types available in Go and how do int and uint behave on different platforms?  
10. What is the difference between `var` and `:=` for variable declarations in Go?  
11. Can the short variable declaration `:=` be used at package level? Why or why not?  
12. How does Go handle unused local variables during compilation?  
13. Can constants in Go be unread or unused without causing compile errors? Why?  
14. What naming conventions does Go use for variables and constants?  
15. Why are some Unicode characters discouraged for use as variable names in Go?  
16. What is a rune in Go, and how does it differ from a string?  
17. How does Go treat strings with respect to mutability?  
18. What are complex numbers in Go, and when would you use complex64 versus complex128?  
19. Why does Go forbid converting between other types and booleans?  
20. What is the effect of the case (uppercase vs lowercase) in Go variable or constant names with package visibility?

## Practical (Coding) Questions

1. Declare variables of types int, float64, bool, and string without initializing and print their zero values.  
2. Write integer literals in Go using base 2, base 8, base 10, and base 16.  
3. Use underscores to declare a large integer literal in Go to improve readability.  
4. Write a code snippet declaring and printing a rune variable with a Unicode character, including an escaped newline and tab.  
5. Create a float64 variable, assign a literal to it, and print its value.  
6. Show how to convert an int variable to float64 and add it to a float64 variable.  
7. Declare multiple variables of different types in one statement using `var`.  
8. Declare variables using the short declaration `:=` inside a function and print them.  
9. Show how to declare a constant string and print it.  
10. Write code that tries to reassign a constant and explain the compile error.  
11. Write a Go program that calculates with complex numbers: add, subtract, multiply, and divide two complex numbers.  
12. Extract and print the real and imaginary parts of a complex128 number using built-in functions.  
13. Demonstrate the behavior of unused local variables by declaring one that is not read and observing the compile-time error.  
14. Write a Go function showing variable shadowing using `:=` and explain the behavior.  
15. Declare package-level variables and constants, and explain scoping and initialization.  
16. Create a string variable and show that strings are immutable by attempting to modify one of its characters.  
17. Write a function to compare two floating point numbers using an epsilon to determine equality.  
18. Use `var` with explicit type versus inferred type variables and explain the difference in your comments.  
19. Declare and print variables using camelCase naming convention and try an invalid variable name with a Unicode look-alike character.  
20. Write a program that uses boolean variables and explicit boolean expressions instead of truthy/falsy checks.
# Python Foundations

## Lesson 1: Python Syntax, Output, Comments, and Variables
We'll learn each topic in a beginner-friendly format: 
`definition → examples → explanation → advanced concepts → practice.`
### Topic 1 — Python Syntax
Syntax means the rules for writing Python code. Just as English has grammar, Python has rules that your code must follow.
**Example 1: Your first Python program**
```code
print("Hello, World!")
```
Output:
```text
Hello, World!
```
Explanation:
* `print()` is a built-in Python function.
* `"Hello, World!"` is a string (text).
* `Parentheses ()` contain the value passed to the function.

## Example 2: Python is indentation-sensitive
Python uses indentation (spaces at the beginning of a line) to define code blocks.
```code
age = 20

if age >= 18:
    print("You are an adult")
    print("You can vote")
```

Both `print()` statements belong to the `if` block because they are indented.

***Incorrect Syntax***

```code
if age >= 18:
print("You are an adult")
```

This causes an `IndentationError`.

**Important rules**

- Python is case-sensitive: name and Name are different.
- Use indentation consistently; four spaces is the standard.
- A colon : introduces a block after statements such as if, for, while, and def.
- A semicolon at the end of a normal statement is usually unnecessary.

Advanced example — multiple assignments:

```code
x, y = 10, 20
x, y = y, x

print(x)  # 20
print(y)  # 10
```
Python can swap two variables without a temporary variable.

## Topic 2 — Python Output

Use print() to display information on the screen.

```code
print("Hello")
print(100)
print(10 + 20)
print("Python", "JavaScript", "SQL")
```

Output
```
Hello
100
30
Python JavaScript SQL
```

`Using sep and end`

```code
print("2026", "10", "23", sep="-")

print("Hello", end=" ")

print("Python")
```

Output:

```
2026-10-23
Hello Python
```
- sep controls the separator between multiple values.
- end controls what is printed after the output. By default, it is a newline ("\n").


### Advance example: Formatting output

```
name = "Ali"
age = 25

print(f"My name is {name} and I am {age} years old.")
```

• f-strings (Formatted string literals) look for variables or expressions directly inside the {} to evaluate them.

• In your original snippet, leaving {} empty causes a SyntaxError because f-strings do not accept empty braces.

• If you want to pass variables at the end of the string like you did, you would use the `.format()` method instead: `print("My name is {} and I am {} years old.".format(name, age))`.


## Topic 3 — Python Comments

```code
# This program calculates
# the total price of
# two products

price1 = 100
price2 = 200

print(price1 + price2)
```

**Best practice: Write comments to explain why something is done, not merely repeat what the code already says.**

## Topic 4 — Python Variables

A variable is a name that refers to a value.

```
name = "Ali"
age = 25
salary = 50000

print(name)
print(age)
print(salary)
```

**Variable naming rules**
|Valid|	Invalid|
|-----|--------|
|user_name|	user-name|
|age2|	2age|
|_price|	user name|
|total_price|	class|

Python variable names can contain letters, digits, and underscores, but cannot begin with a digit. They are case-sensitive, and reserved keywords such as class cannot be used as variable names.

**Changing variable**

```
score = 10
print(score)

score = 50
print(score)
```

Output
```output
10
50
```

**Multiple assignment**

```
a, b, c = 10, 20, 30

x = y = z = 100

print(a, b, c)
print(x, y, z)
```

**Advanced concept: Python is dynamically typed**

You don't need to declare a variable's type explicitly.

```
value = 100
print(type(value))

value = "Hello"
print(type(value))
```
The first value is an integer; the second is a string.

***Python variables are names bound to objects. This distinction becomes important when working with lists, dictionaries, and mutable objects.***
















<br>

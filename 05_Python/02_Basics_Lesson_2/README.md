# Python Basics — Lesson 2

Today we'll continue your one-day Python roadmap. This lesson covers six important topics, from beginner concepts to more advanced examples.
- Topic 5: Python Data Types
- Topic 6: Python Numbers
- Topic 7: Python Casting
- Topic 8: Python Strings
- Topic 9: Python Booleans
- Topic 10: Python Operators


## Topic 5 — Python Data Types

A **data type** tells Python what kind of value you are working with.

For example, a person's name is text, their age is an integer, and their height might be a decimal number.

**5.1 Main Python data types**

|Data type|	Example|	Meaning|
|---------|:--------:|---------|
|str|	"Ali"	|Text|
|int|	25|	Whole number|
|float|	5.8|	Decimal number|
|complex|	2 + 3j	|Complex number|
|bool|	True|	True or false|
|list|	[10, 20, 30]	|Ordered, changeable collection|
|tuple|	(10, 20, 30)	|Ordered, unchangeable collection|
|set|	{10, 20, 30}	|Collection of unique values|
|dict|	{"name": "Ali"}	|Key-value pairs|
|NoneType|	None|	Absence of a value|

## 5.2 Use type() to check data types

```
name = "Ali"
age = 25
salary = 50000.50
is_employed = True

print(type(name))
print(type(age))
print(type(salary))
print(type(is_employed))
```

Output:

```
<class 'str'>
<class 'int'>
<class 'float'>
<class 'bool'>
```

## 5.3 Mutable vs. immutable data types

This is an important concept for advanced Python.

- Mutable: The object can be changed, such as a list or dictionary.
- Immutable: The object cannot be changed in place, such as a string, integer, or tuple.

 ```
numbers = [10, 20, 30]
numbers[0] = 100

print(numbers)
```

 Output: `[100,20,30]`

 But strings are immutable:

 ```
name = "Ali"
# name[0] = "W"  # TypeError
name = "Wali"     # This is allowed
```

The last line creates a new string value and reassigns the variable.

## Topic 6 — Python Numbers
Python has three main numeric types: int, float, and complex.

### Int 
```
age = 30
price = 200000
temperature = -5
```

### Float

```
price = 199.99
height = 5.8

print(price + 10)
print(height)
```

 ### Complex numbers

 ```
number = 2 + 3j

print(number.real)
print(number.imag)
```

Output:

```
2.0
3.0
```

### Important numeric functions

```
print(abs(-20))       # 20
print(round(3.14159, 2))  # 3.14
print(pow(2, 3))      # 8
print(divmod(17, 5))  # (3, 2)
```

- `abs()` returns the absolute value.
- `round()` rounds a number.
- `pow()` raises a number to a power.

## Topic 7 — Python Casting

Casting means converting a value from one data type to another.
### Basic casting

```
# String to integer
age = int("30")
print(age)        # 30
print(type(age))  # <class 'int'>

# Integer to float
price = float(100)
print(price)      # 100.0

# Number to string
number = str(500)
print(number)     # "500"

# Integer to boolean
print(bool(1))    # True
print(bool(0))    # False
```

## Important casting rules

```
print(int(5.9))      # 5
print(float("3.5"))  # 3.5
print(str(100))      # "100"
```

```Notice that int(5.9) truncates the decimal part; it doesn't round to the nearest integer.```

```
age = int("hello")
```

Python raises a ValueError because "hello" is not a valid integer representation.

### Advanced example: safe casting

```
user_input = "25"

try:
    age = int(user_input)
    print("Your age is:", age)
except ValueError:
    print("Please enter a valid whole number.")
```

This program handles invalid input instead of crashing.

## String

```
name = "Muhammad"
city = 'Pakpattan'

print(name)
print(city)
```

## Indexing and slicing
Python indexes start from 0.

```
word = "Python"

print(word[0])    # P
print(word[1])    # y
print(word[-1])   # n
print(word[0:3])  # Pyt
print(word[2:])   # thon
print(word[::-1]) # nohtyP
```
***Remember: the ending index in a slice is excluded.***

### Common string methods

```
text = "  Learn Python  "

print(text.upper())          # LEARN PYTHON  converts every lowercase letter in the string to uppercase, resulting in " LEARN PYTHON "
print(text.lower())          # learn python  converts every uppercase letter in the string to lowercase, resulting in " learn python "
print(text.strip())          # Learn Python  removes all leading (front) and trailing (back) whitespaces, resulting in "Learn Python"
print(text.replace("Python", "NumPy"))   Substitutes the substring "Python" with "NumPy", while preserving the leading and trailing spaces.
print(text.count("n"))   • Returns 2 because it counts the two lowercase "n" characters (one in "Learn", one in "Python"). It is case-sensitive, so the uppercase "P" is ignored.
print(text.startswith("  Learn")) Returns False because the original string begins with only one space (" Learn Python "), not two.
print(text.find("Python"))  • Returns 7 because the substring "Python" starts at index 7 of the string (counting from 0, including the initial space).
```
Other useful methods include:

```
print("hello world".title())          # Hello World   Capitalizes the first letter of every word in the string.
print("a,b,c".split(","))             # ['a', 'b', 'c']   • Breaks a string into a list using the specified comma separator.
print("-".join(["2026", "10", "24"])) # 2026-10-24   Combines a list of strings into one single string, gluing them together with a hyphen.
print("123".isdigit())                # True   The .isdigit() method returns True because every character in the string "123" is a numeric digit (0 through 9).
print("hello".isalpha())              # True   The str.isalpha() method in Python checks whether all characters in a string are alphabetic letters and the string contains at least one character.
```

### Strings are immutable

```
name = "python"

# name[0] = "P"  # TypeError

name = "P" + name[1:]
print(name)      # Python
```

You create a new string rather than modifying an existing character.

## Advanced example: clean user input

```
email = "  USER@EXAMPLE.COM  "

clean_email = email.strip().lower()  # will remove all spaces or extra

print(clean_email)
```

```Output: user@example.com```

***.strip(): Removes the leading and trailing whitespace. If want to remove (-) then use .strip("-")***

**This is useful when processing form data in applications.**

## Python Booleans
Booleans have only two values: True and False.
```
is_logged_in = True
is_admin = False

print(is_logged_in)
print(is_admin)
```

### Comparison expressions

```
age = 30

print(age > 18)    # True
print(age < 18)    # False
print(age == 30)   # True
print(age != 20)   # True
print(age >= 30)   # True
print(age <= 25)   # False
```

### Truthy and falsy values
Python treats some values as false in conditions.

```
print(bool(0))       # False
print(bool(""))      # False
print(bool([]))      # False
print(bool(None))    # False

print(bool(10))      # True
print(bool("Hello")) # True
print(bool([1, 2]))  # True
```

**Common falsy values include False, None, numeric zero, and empty collections.**

### Advanced example: login condition
```
username = "admin"
password_correct = True

if username == "admin" and password_correct:
    print("Login successful")
else:
    print("Login failed")
```

## Python Operators
Operators perform calculations, comparisons, and logical operations.
10.1 Arithmetic operators

|Operator|	Meaning|	Example|	Result|
|--------|---------|---------|--------|
|+|	Addition|	10 + 3|	13|
|-|	Subtraction|	10 - 3|	7|
|*|	Multiplication|	10 * 3|	30|
|/|	Division|	10 / 3|	3.333...|
|//|	Floor division|	10 // 3|	3|
|%|	Remainder|	10 % 3|	1|
|**|	Exponentiation|	2 ** 3|	8|

### Comparison operators
```
x = 10
y = 20

print(x == y)  # False
print(x != y)  # True
print(x < y)   # True
print(x > y)   # False
print(x <= y)  # True
print(x >= y)  # False
```

### Logical Operator
```
age = 25
has_license = True

print(age >= 18 and has_license)  # True
print(age < 18 or has_license)    # True
print(not has_license)            # False
```

- `and:` Both conditions must be true.
- `or:` At least one condition must be true.
- `not:` Reverses the truth value.

### Assignment operator

```
score = 10

score += 5   # score = score + 5
print(score) # 15

score *= 2
print(score) # 30

score -= 10
print(score) # 20
```

Other assignment operators include `-=`, `/=`, `//=`, `%=`, and `**=`.

### Membership operators

```
languages = ["Python", "JavaScript", "Java"]

print("Python" in languages)      # True
print("PHP" not in languages)     # True
```

Membership tests also work with strings:

```print("Py" in "Python")  # True```

### Identity operators

`is` and `is not` check whether two references point to the same object, not merely whether their values are equal.
```
a = [1, 2]
b = [1, 2]

print(a == b)  # True: same contents
print(a is b)  # False: different list objects
```

### Operator precedence
Python evaluates some operators before others
```
result = 2 + 3 * 4
print(result)  # 14
```

Multiplication occurs before addition. Use parentheses to make your intention clear:
```
result = (2 + 3) * 4
print(result)  # 20
```

## Precedence & BODMAS
**BODMAS Rule is a standard way to define the order of precedence and sequence for solving mathematical expressions.**

What BODMAS Stands For and Precedence Order

• B — Brackets (Innermost first: (), {}, [])<br>
• O — Orders / Of (Powers, indices, and roots)<br>
• D — Division (From left to right)<br>
• M — Multiplication (From left to right, equal precedence with division)<br>
• A — Addition (From left to right, equal precedence with subtraction)<br>
• S — Subtraction (From left to right<br>

<br>

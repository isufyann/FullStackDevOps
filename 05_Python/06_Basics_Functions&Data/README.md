# Python Basics — Lesson 4: Functions, Arrays, Iterators, Modules, Dates, Math, JSON & RegEx

oday's lesson roadmap

|Lesson|-|
|-----|-----|
|**1. Python Functions**|Create reusable code with parameters, return values, and advanced arguments.|
|**2. Python Arrays**|Store and process multiple values efficiently.|
|**3. Python Iterators**|Understand iteration, iter(), next(), and generators.|
|**4. Python Modules**|Import reusable code and organize multi-file projects.|
|**5. Python Dates**|Work with dates, times, and date calculations.|
|**6. Python Math**|Use mathematical functions and numeric operations.|
|**7. Python JSON**|Read and write structured data used by APIs.|
|**8. Python RegEx**|Find, validate, and extract patterns from text.|

## Python Functions

### 1. What is a function?
A function is a reusable block of code that performs a specific task.

Imagine you calculate the total price of products every day. Instead of writing the same calculation repeatedly, you can create a function once and reuse it.

Without a function
```
price = 100
quantity = 3
print(price * quantity)

price = 200
quantity = 2
print(price * quantity)
```

With Function:
```
def calculate_total(price, quantity):
    return price * quantity

print(calculate_total(100, 3))
print(calculate_total(200, 2))
```
The second approach is easier to maintain and reuse.

### Function syntax

```
def function_name(parameters):
    # Function body
    return result
```

|Keyword or term|	Meaning|
|-|-|
|def|	Defines a function|
|function_name|	The name you choose|
|parameters|	Inputs the function accepts|
|Indented body|	Instructions to execute|
|return|	Sends a result back to the caller|

### Functions without parameters

```
def greet():
    print("Welcome to Python!")

greet()
greet()
```

***Only defining a function does not execute its body. Calling greet() executes it.***

### 4. Parameters and arguments
A parameter is a variable in the function definition. An argument is the value you pass when calling the function.

```
def greet(name):
    print(f"Hello, {name}!")

greet("Ali")
greet("Sara")
```

Output:
```
Hello, Ali!
Hello, Sara!
```

Here, `name` is a parameter; `"Ali"` and `"Sara"` are arguments.

### 5. Return vs. print
This is one of the most important concepts.

```
def add_print(a, b):
    print(a + b)

def add_return(a, b):
    return a + b

result = add_return(10, 20)
print(result * 2)

Output:
60
```

- print() displays a value.
- return gives the value back to the caller so it can be stored, calculated with, or passed to another function.

***A function without an explicit return returns None.***

## 6. Default parameters
You can provide default values for parameters.
```code
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()
greet("Ali")
```
Output:
```
Hello Sufyan
Hello Ali

```

## 7. Keyword arguments
You can specify arguments by parameter name.
```
def student(name,age,city):
  print(f"{name} {age} {city}")

student(
    name="Sufyan",
    age=25,
    city="Pakpattan"
)
```
***This is useful when functions have multiple parameters and you want calls to be clear.***

## 8. Advanced arguments: *args and **kwargs
Use *args when a function should accept a variable number of positional arguments.

```
def calculate_sum(*num):
  return sum(num)
print(calculate_sum(1,2,3))
print(calculate_sum(1,2,3,4,5,6,7))
```
***Use **kwargs to accept a variable number of keyword arguments.***

## 9. Scope: local and global variables
A variable created inside a function is normally local to that function.
A function can read a global variable:

## 10. Lambda functions
A lambda is a small anonymous function containing one expression.

```
square = lambda number: number ** 2

print(square(5))  # 25
```
A lambda can also be used with sorting:

```
students = [
    {"name": "Ali", "marks": 75},
    {"name": "Sara", "marks": 92},
    {"name": "Ahmed", "marks": 65}
]

students.sort(key=lambda student: student["marks"])

print(students)
```

This sorts the students by marks in ascending order. For more complex logic, a regular def function is usually clearer.

# Topic 21 — Python Arrays
## 1. What is an array?
An array stores multiple values under one variable name. In Python, you'll commonly encounter three related tools:
- List: General-purpose collection that can contain different data types.
- array module: Provides compact arrays whose elements share a numeric type.
- NumPy array: Designed for efficient numerical computing, mathematical operations, and data analysis.

### 1.1 Python list vs. array

```
numbers = [10, 20, 30, 40]

print(numbers[0])  # 10
numbers.append(50)
```
### 1.2 Using Python's built-in array module

```
import array

numbers = array.array("i", [10, 20, 30, 40])

numbers.append(50)

print(numbers)
print(numbers[0])
```
***Here, "i" specifies a signed integer element type. All elements must be compatible with that type.***

### Python's built-in array doesn't support element-wise arithmetic in the same way NumPy does.

For example, adding 10 to every element is simple with a list comprehension:

```
numbers = [10, 20, 30, 40]

result = [n + 10 for n in numbers]

print(result)
```

### 1.4 NumPy arrays — connection to your next step
When you learn NumPy, you'll be able to perform numerical operations directly on arrays.

```
# Install NumPy in your terminal:
# python -m pip install numpy

import numpy as np

numbers = np.array([10, 20, 30, 40])

print(numbers + 10)
print(numbers * 2)
print(numbers.mean())
```

***Important:*** NumPy operations such as numbers + 10 apply to each element. Python lists behave differently: [10, 20] * 2 repeats the list rather than multiplying each element.

## Topic 22 — Python Iterators

### 1. What is an iterator?
An iterator gives you values one at a time. Iterators are useful when processing sequences, files, streams, or large amounts of data.

An iterable is an object you can loop over. An iterator is an object that produces the next value when requested.

```
numbers = [10, 20, 30]

iterator = iter(numbers)

print(next(iterator))
print(next(iterator))
print(next(iterator))
```

### To learn topics later
1. How for loops use iterators
2. Build your own iterator
3. Generators — a simpler approach
4. Practical example: generate squares

## Topic 23 — Python Modules

### 1. What is a module?
A module is a Python file containing reusable code, such as functions, classes, and variables.

Python provides built-in modules, and you can create your own modules.

### 2. Import a built-in module

```
import math

print(math.sqrt(64))
print(math.pi)
```

Output:
```
8.0
3.141592653589793
```

The `math` module provides mathematical functions and constants.


### 3. Import selected functions

```
from math import sqrt, ceil

print(sqrt(81))
print(ceil(4.2))
```

**We can use an alias**
```
import math as m

print(m.factorial(5))

Output: 120
```

***Avoid from module import * in most application code because it can make names unclear and create conflicts.***

### 4. Create your own module
Create two files in the same folder.

```</> calculator.py```

```
def add(a, b):
    return a + b

def multiply(a, b):
    return a * b
```

```</> main.py```

```
import calculator

print(calculator.add(10, 20))
print(calculator.multiply(5, 4))
```

Run `main.py` from the terminal:

```python main.py```

Output:
```
30
20
```

Python finds `calculator.py` because it is in the same project folder.



### 6. Module vs. package

- Module: Usually one .py file.
- Package: A way to organize related modules into a directory structure.

Example:
```
my_project/
    main.py
    utilities/
        __init__.py
        calculator.py
        formatting.py
```

This organization is useful when your applications become larger.

## Topic 24 — Python Dates

Python's built-in datetime module lets you work with dates and times.

```
from datetime import date

today = date.today()

print(today)
print(today.year)
print(today.month)
print(today.day)
```
The displayed date depends on your computer's local date.

### 2. Create a specific date
```
from datetime import date

birthday = date(1996, 5, 15)

print(birthday)
print(birthday.year)
```

Dates use the format year, month, day when constructed.

### 3. Get current date and time

```
from datetime import datetime

now = datetime.now()

print(now)
print(now.year)
print(now.hour)
print(now.minute)
```
`datetime.now()` uses the local system's time zone unless a time zone is supplied.

### 4. Format dates with strftime()

```
from datetime import datetime

now = datetime.now()

print(now.strftime("%d-%m-%Y"))
print(now.strftime("%B %d, %Y"))
print(now.strftime("%I:%M %p"))
```

Common formatting codes:

|Code|	Meaning|
|-|-|
|%Y|	Four-digit year|
|%m|	Month number|
|%d|	Day of month|
|%B|	Full month name|
|%A|	Full weekday name|
|%H|	Hour, 24-hour clock|
|%I|	Hour, 12-hour clock|
|%M|	Minutes|
|%S|	Seconds|
|%p|	AM or PM|

### 5. Convert text into a date
Use strptime() when a date arrives as a string.

```
from datetime import datetime

date_text = "30-10-2026"

parsed_date = datetime.strptime(date_text, "%d-%m-%Y")

print(parsed_date.date())
```

### 6. Date calculations with timedelta

```
from datetime import date, timedelta

today = date.today()

tomorrow = today + timedelta(days=1)
next_week = today + timedelta(days=7)
last_week = today - timedelta(days=7)

print(tomorrow)
print(next_week)
print(last_week)
```

Calculate the number of days between dates:

```
from datetime import date

start = date(2026, 1, 1)
end = date(2026, 12, 31)

difference = end - start

print(difference.days)
```

### 7. Advanced concept: time zones
For applications involving international users, use timezone-aware datetimes.

```
from datetime import datetime, timezone

now_utc = datetime.now(timezone.utc)

print(now_utc)
```












<br>

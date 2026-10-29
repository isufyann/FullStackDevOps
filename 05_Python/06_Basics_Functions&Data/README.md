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










<br>

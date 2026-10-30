# Python Basics — Lesson 5: Math, JSON & RegEx

|Lesson|-|
|-|-|
|**1. Python Math**|Use mathematical functions and numeric operations.|
|**2. Python JSON**|Read and write structured data used by APIs.|
|**3. Python RegEx**|Find, validate, and extract patterns from text.|


## Topic 1 — Python Math
Python provides built-in numeric operations and a math module for more advanced calculations.

### 1. Basic mathematical operations

```
print(10 + 5)   # 15
print(10 - 5)   # 5
print(10 * 5)   # 50
print(10 / 5)   # 2.0
print(10 // 3)  # 3
print(10 % 3)   # 1
print(2 ** 3)   # 8
```

### 2. Common `math` function

```
import math

print(math.sqrt(64))       # 8.0
print(math.ceil(4.2))      # 5
print(math.floor(4.9))     # 4
print(math.factorial(5))   # 120
print(math.gcd(12, 18))    # 6 (Greater Common Division)
print(math.pi)             # Pi constant
print(math.e)              # Euler's number
```

|Function|	Purpose|
|-|-|
|math.sqrt(x)|	Square root|
|math.ceil(x)|	Round upward to an integer|
|math.floor(x)|	Round downward to an integer|
|math.factorial(x)|	Factorial of a nonnegative integer|
|math.gcd(a, b)|	Greatest common divisor|
|math.pow(a, b)|	Floating-point exponentiation|
|math.isqrt(x)|	Integer square root|
|math.isfinite(x)|	Check whether a value is finite|

### 3. Calculate a circle's area

`Area=pi r square (Area=pi*r*^2)`

<img width="152" height="68" alt="areaFind" src="https://github.com/user-attachments/assets/20f3270c-efe3-443e-8260-2d831224aeab" />


```
import math

radius = 7

area = math.pi * radius ** 2

print(f"Area: {area:.2f}")
print(math.floor(area))
```
The `:.2f` format displays two digits after the decimal point.

### 4. Calculate compound interest

<img width="270" height="101" alt="principleAmount" src="https://github.com/user-attachments/assets/c6d4c39e-5d65-49cd-800b-c4c2af4550fc" />

```
principal = int(input("Enter Principal amount"))
rate = 5
years = 3

amount = principal * (1 + rate / 100) ** years

print(f"Final amount: Rs. {amount:.2f}")
```

Output:
If entered: 10000 ->
`Final amount: Rs. 11576.25`

### 5. Advanced: rounding and precision

```
import math

value = 3.14159

print(round(value, 2))       # 3.14
print(math.isclose(0.1 + 0.2, 0.3))  # True
```
Use `math.isclose()` when comparing floating-point results where tiny rounding differences are expected.

## Topic 2 - Python JSON

### 1. What is JSON?
JSON stands for JavaScript Object Notation. It's a text format for exchanging structured data between applications.

For example, a web API might send this data:

```
{
  "name": "Ali",
  "age": 25,
  "skills": ["Python", "SQL"],
  "is_student": true
}
```

JSON is commonly used in APIs, web applications, configuration files, and automation workflows.

### 2. Python data vs. JSON data

|Python|	JSON|
|-|-|
|dict|	Object|
|list|	Array|
|str|	String|
|int / float|	Number|
|True / False|	true / false|
|None|	null|

JSON uses double quotes around strings and keys. It does not support Python-specific values such as tuples, sets, or None as written in Python source code.

### 3. Convert Python data to JSON: dumps()

```
import json

student = {
    "name": "Ali",
    "age": 25,
    "skills": ["Python", "SQL"],
    "is_student": True
}

json_text = json.dumps(student, indent=4)

print(json_text)
```

Output:
```
{
    "name": "Ali",
    "age": 25,
    "skills": [
        "Python",
        "SQL"
    ],
    "is_student": true
}
```
The output is a JSON-formatted string:

***dumps() returns a string. The indent=4 option makes the output readable.***

### 4. Convert JSON to Python: loads()

```
import json

json_text = '{"name": "Ali", "age": 25, "is_student": true}'

student = json.loads(json_text)

print(student["name"])
print(student["age"])
print(type(student))
```

```
Ali
25
<class 'dict'>
```

#### Remember:
- dumps() converts Python data into a JSON string.
- loads() parses a JSON string into Python data.

### 5. Read and write JSON files
Use dump() and load() when working with files.

**Save data**

```
import json

student = {
    "name": "Sara",
    "marks": 92
}

with open("student.json", "w", encoding="utf-8") as file:
    json.dump(student, file, indent=4)
```

**Read data**

```
import json

with open("student.json", "r", encoding="utf-8") as file:
    student = json.load(file)

print(student["name"])
print(student["marks"])
```

The with statement closes the file automatically when the block finishes.

### 6. Handle invalid JSON

```
import json

text = '{"name": "Ali",}'

try:
    data = json.loads(text)
    print(data)
except json.JSONDecodeError:
    print("Invalid JSON format")
```

This catches a common error: a trailing comma is not valid JSON syntax.

##3 7. Advanced example: API-style data

```
import json

response = """
{
    "status": "success",
    "data": {
        "user_id": 101,
        "name": "Ali"
    }
}
"""

result = json.loads(response)

if result["status"] == "success":
    user = result["data"]
    print(f"User: {user['name']}")
    print(f"ID: {user['user_id']}")
```

This is similar to how you process a JSON response from a web API. In real applications, validate external data and handle missing fields safely.




<br>

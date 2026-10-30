# Python – Lesson 5: Final Core Topics
## 6 Topics: Beginner to Practical

---

### 1. PIP – Python Package Installer
#### What is PIP?
**PIP** allows you to install external Python libraries and packages. For example:
* **NumPy** – numerical calculations
* **Pandas** – data analysis
* **Requests** – API requests
* **Matplotlib** – charts and graphs

#### Common PIP Commands
* **Check PIP version:**
  ```bash
  python -m pip --version
  ```
* **Install a package:**
  ```bash
  python -m pip install numpy
  ```
* **Install a specific version:**
  ```bash
  python -m pip install numpy==2.0.0
  ```
* **See installed packages:**
  ```bash
  python -m pip list
  ```
* **Uninstall a package:**
  ```bash
  python -m pip uninstall numpy
  ```
* **Save installed packages:**
  ```bash
  python -m pip freeze > requirements.txt
  ```
* **Install all packages from that file:**
  ```bash
  python -m pip install -r requirements.txt
  ```

---

### 2. Try...Except – Error Handling
Sometimes Python code produces errors. We use `try...except` to handle them without crashing the program unexpectedly.

#### Without error handling:
```python
number = int(input("Enter a number: "))
print(number)
```
*If the user enters `abc`, Python raises a **ValueError**.*

#### With error handling:
```python
try:
    number = int(input("Enter a number: "))
    print("Your number:", number)
except ValueError:
    print("Please enter a valid number.")
```

#### Multiple exceptions:
```python
try:
    a = int(input("Enter first number: "))
    b = int(input("Enter second number: "))
    result = a / b
    print(result)
except ValueError:
    print("Please enter numbers only.")
except ZeroDivisionError:
    print("Cannot divide by zero.")
finally:
    print("Program finished.")
```

#### Understand these four keywords:
| Keyword | Purpose |
| :--- | :--- |
| `try` | Code that might cause an error |
| `except` | Handles an error |
| `else` | Runs if no exception occurs |
| `finally` | Runs whether an error occurs or not |

#### Raise your own error:
```python
age = -5
if age < 0:
    raise ValueError("Age cannot be negative")
```

---

### 3. String Formatting
String formatting allows us to insert variables into text.

#### Method 1: f-strings (recommended)
```python
name = "Ali"
age = 25
salary = 50000
print(f"My name is {name}.")
print(f"My age is {age}.")
print(f"My salary is {salary}.")
```

#### Method 2: format()
```python
name = "Ali"
age = 25
print("My name is {} and age is {}".format(name, age))
```

#### Method 3: % formatting
```python
name = "Ali"
age = 25
print("My name is %s and age is %d" % (name, age))
```

#### Formatting numbers:
```python
price = 1250.5678
print(f"Price: {price:.2f}")
# Output: Price: 1250.57
```

#### Other useful examples:
```python
number = 1500000
print(f"{number:,}")     # 1,500,000 (comma separator)
print(f"{number:.2%}")   # percentage formatting
print(f"{25:05}")        # 00025 (zero padding)
```

---

### 4. None – Absence of a Value
`None` represents the absence of a value.

```python
name = None
print(name)
print(type(name))
# Output: None <class 'NoneType'>
```

#### Checking None:
```python
user = None
if user is None:
    print("No user found")
else:
    print("User found")
```

#### None in functions:
```python
def greet():
    print("Hello")

result = greet()
print(result)
# Output: 
# Hello
# None
```
*Why? Because the function doesn't explicitly return a value.*

#### Remember:
* `None` is not the same as `0`.
* `None` is not the same as an empty string `""`.
* `None` is not the same as `False`.
* Use `is None` to check for `None`.

---

### 5. User Input
The `input()` function allows users to enter information while a program is running.

#### Basic example:
```python
name = input("Enter your name: ")
print(f"Welcome, {name}!")
```
*Important: `input()` always returns a **string**.*

#### For numbers, convert the input:
```python
age = int(input("Enter your age: "))
print(f"Next year you will be {age + 1}")
```

#### Taking decimal input:
```python
price = float(input("Enter product price: "))
print(price)
```

#### Multiple inputs:
```python
name = input("Name: ")
age = int(input("Age: "))
city = input("City: ")
print(f"{name} is {age} years old and lives in {city}.")
```

#### Input with error handling:
```python
try:
    age = int(input("Enter your age: "))
    if age >= 18:
        print("Adult")
    else:
        print("Minor")
except ValueError:
    print("Please enter a valid age.")
```

---

### 6. Virtual Environment (venv)
A virtual environment creates an isolated Python environment for each project. 

Imagine you have two projects:
* **Project A** needs NumPy version 1.
* **Project B** needs NumPy version 2.

Virtual environments help keep their dependencies separate.

#### Step-by-Step Implementation:
1. **Create a project folder**
   ```bash
   mkdir python-project
   cd python-project
   ```
2. **Create virtual environment**
   ```bash
   python -m venv venv
   ```
3. **Activate it**
   * *Windows CMD:* `venv\Scripts ctivate`
   * *Windows PowerShell:* `.
env\Scripts\Activate.ps1`
4. **Install packages**
   ```bash
   python -m pip install numpy
   ```
5. **Check installed packages**
   ```bash
   python -m pip list
   ```
6. **Deactivate environment**
   ```bash
   deactivate
   ```
7. **Create requirements file**
   ```bash
   python -m pip freeze > requirements.txt
   ```

#### Recommended project structure:
```text
python-project/
│
├── venv/
├── main.py
├── requirements.txt
└── README.md
```
*Tip: Add `venv/` to `.gitignore` so you don't upload the virtual environment files to GitHub.*

---

## Practice Projects
Now apply all six topics. 

**Your project progress: 0/6**
- [ ] **1. Smart Calculator**  
  Take two numbers from the user. Handle invalid input and division by zero.
- [ ] **2. Student Registration**  
  Take name, age, marks and city. Display a formatted student profile.
- [ ] **3. ATM Simulator**  
  Take a PIN and amount. Handle incorrect input and insufficient balance.
- [ ] **4. Expense Tracker**  
  Take expenses from the user, calculate the total and format the result.
- [ ] **5. Package Manager Practice**  
  Create a virtual environment, install NumPy and save requirements.txt.
- [ ] **6. User Account System**  
  Use None to represent a missing user and handle invalid registration data.

---

## Final Knowledge Test
*Try these questions without looking at the lesson.*

1. What command do you use to see all external libraries installed in your environment?
2. What exception blocks should you write if you expect a division by zero or a text-to-integer conversion failure?
3. How do you print `45.6789` as exactly `45.68` using an f-string?
4. What data type evaluates to true when checking `type(None)`?
5. Why does `input("Enter age: ") + 5` cause an error, and how do you fix it?
6. Why is it bad practice to commit your `venv/` folder to Git?

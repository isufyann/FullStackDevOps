# Part B — Conditions

## Topic 15 — Python If...Else

Conditions let a program make decisions.

### 15.1 if

```
age = 20

if age >= 18:
    print("You are an adult")
```

The indented code executes only when the condition is true.

### 15.2 if...else

```age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

### 15.3 if...elif...else
Use elif when you need to test several conditions.
```
marks = 78

if marks >= 90:
    grade = "A"
elif marks >= 80:
    grade = "B"
elif marks >= 70:
    grade = "C"
else:
    grade = "Needs improvement"

print(grade)
```

Output: `C`

Python checks the conditions from top to bottom and executes the first matching branch.

### 15.4 Combine conditions

```
age = 25
has_license = True

if age >= 18 and has_license:
    print("Can drive")
else:
    print("Cannot drive")
```
### 15.5 Nested conditions

```
username = "admin"
password_correct = True

if username == "admin":
    if password_correct:
        print("Login successful")
    else:
        print("Incorrect password")
else:
    print("Unknown user")
```

In real applications, authentication must be handled securely; this is just a basic demonstration of nested conditions.

### 15.6 Ternary expression
For a simple decision, use a conditional expression:
```
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```
This is useful for short assignments, but ordinary `if...else` is clearer for complex logic.

## Topic 16 — Python Match

match is Python's pattern-matching statement, introduced in Python 3.10. It can select behavior based on a value or pattern.

### 16.1 Basic example

```
day = 2

match day:
    case 1:
        print("Monday")
    case 2:
        print("Tuesday")
    case 3:
        print("Wednesday")
    case _:
        print("Unknown day")
```

Output: `Tuesday`

The underscore `_` is a wildcard pattern that matches anything.

### 16.2 Match multiple values

```
day = "Saturday"

match day:
    case "Saturday" | "Sunday":
        print("Weekend")
    case "Monday" | "Tuesday" | "Wednesday" | "Thursday" | "Friday":
        print("Working day")
    case _:
        print("Invalid day")
```

The `|` in a pattern means “match either alternative.”

### 16.3 Match with conditions

```
marks = 85

match marks:
    case n if n >= 90:
        print("Grade A")
    case n if n >= 70:
        print("Grade B")
    case n if n >= 50:
        print("Grade C")
    case _:
        print("Needs improvement")
```

### 16.4 When to use match vs. if...else

|Use if...else	|Use match|
|-|-|
|Ranges and complex Boolean conditions|	Multiple value or structural patterns|
|Comparisons such as age >= 18|	Commands, fixed options, and data shapes|
|General decision-making|	Cases that are easier to read as patterns|

You don't need to replace every `if...else` with `match`. Choose whichever makes the code clearer.






<br>

# Project Practice

### 10 Python Practice Projects — Beginner to Intermediate
These 10 projects are based only on the topics you've learned so far: Python syntax, variables, data types, casting, strings, booleans, operators, lists, tuples, sets, dictionaries, conditions, match, loops, and range().

***Your rule: Try to solve each project yourself before asking me for the solution. I've included requirements, hints, and sample outputs, but no complete solutions.***

**Progress: 25/31 Completed**

- [x] 1. Student Result System — Easy

- [ ] 2. Simple Calculator — Easy

- [ ] 3. Number Guessing Game — Easy

- [ ] 4. Multiplication Table Generator — Easy

- [ ] 5. Shopping Cart and Bill — Easy

- [ ] 6. Password Strength Checker — Easy–Medium

- [ ] 7. Duplicate Remover — Medium

- [ ] 8. Student Management System — Medium

- [ ] 9. Bank Account Simulator — Medium

- [ ] 10. Quiz Application — Medium



## Mini-projects

### Project 1 - Student Result Management System
Build this program using the concepts from today's lesson.

Requirements:
1. Store several students and their marks in a dictionary.
2. Loop through all students.
3. Use if...else to determine pass or fail, with 40 marks as the passing score.
4. Print each student's name, marks, and result.
5. Calculate the class average.

```code
students = {
    "Ali": 75,
    "Sara": 92,
    "Ahmed": 35,
    "Usman": 60
}
for key,value in students.items():
  print(f"{key} | {value}")
print("\nNext Result...\n")
for name, marks in students.items():
  if marks>40:
    print(f"{name} Passed")
  else:
    print(f"{name} Failed")
    print("\nNext Result...\n")
for name, marks in students. items():
  print(f"{name} | {marks}")

length_of_students=len(students)
sum_of_students=sum(students.values())
avg_students=sum_of_students/length_of_students

print(f"Length of students is {length_of_students}")
print(f"Sum of students is {sum_of_students}")
print(f"Average of students is {avg_students}")
```

## Project 2 — Simple Calculator

Concepts: Operators, user input, casting, match, conditions.

Create a calculator that performs addition, subtraction, multiplication, and division.

Requirements
- Ask for two numbers.
- Ask the user to choose an operator: +, -, *, or /.
- Use match to select the operation.
- Handle division by zero.
- Display an error for an invalid operator.

```code
firstNumber=int(input("Enter first number"))
secondNumber=int(input("Enter 2nd number"))

operator = input("Choose an operator (+, -, *, /,//,&,**): ")

match operator:
  case "+":
    print(f"The Sum is: {firstNumber+secondNumber}")
  case "-":
    print(f"The Minus is: {firstNumber-secondNumber}")
  case "*":
    print(f"The Mulitply is: {firstNumber*secondNumber}")
  case "/":
    print(f"The Division is: {firstNumber/secondNumber}")
  case "//":
    print(f"The FloorDivision is: {firstNumber//secondNumber}")
  case "%":
    print(f"The Modulous is: {firstNumber%secondNumber}")
  case "**":
    print(f"The Modulous is: {firstNumber**secondNumber}")
  case _:
    print("Enter valid number")
```



















<br>

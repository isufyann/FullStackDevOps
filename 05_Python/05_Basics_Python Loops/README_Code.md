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

## Project 3 — Number Guessing Game

Concepts: Variables, while, if...elif...else, comparison operators, break.

Create a game where the player guesses a secret number.

Requirements
- Choose a secret number between 1 and 20.
- Allow repeated guesses.
- If the guess is too low, print Too low!.
- If too high, print Too high!.
- Stop when the correct number is guessed.
- Count the number of attempts.

```code
import random
secret_number=random.randint(1,20)
attempts=0
# x=0
while True: # Infinite loop
  try:
    guess=int(input("Enter  your guess:😁"))
    attempts=attempts+1
    # x=x+132

    if guess < secret_number:
      print("Too low!")
    elif guess > secret_number:
      print("Too high!")
    else:
      print(f"Correct! You guessed the number in {attempts} attempts.")
      break
  except ValueError:
    print("Please enter a valid number.")
```

## Project 4 — Multiplication Table Generator

Concepts: for, range(), arithmetic, user input, string formatting.

Create a program that generates the multiplication table for any number.

Requirements
- Ask the user for a number.
- Generate its table from 1 to 10.
- Format each line as a multiplication equation.

```code
num=int(input("Enter Table for print: "))

for i in range(1,11):
  product=num*i
  print(f"{num} x {i} = {product}")
```

**Challenge: Ask the user for the starting and ending multipliers, then generate only that range.**

```
num=int(input("Enter Table for print: "))
numFrom=int(input("Enter Table from: "))
numTill=int(input("Enter Table till: "))


for numFrom in range(numFrom, numTill):
  product=num*numFrom
  print(f"{num} x {numFrom} = {product}")
```

## Project 5 — Shopping Cart and Bill

Concepts: Lists, dictionaries, loops, arithmetic, conditions, f-strings.

Build a simple shopping bill generator.

Requirements
1. Create a dictionary of products and their prices.
2. Let the user select products.
3. Store selected items in a shopping cart.
4. Calculate the subtotal.
5. Apply a 10% discount if the subtotal is at least Rs. 5,000.
6. Display the final bill.

```code
product_prices = {
    "Laptop": 999.99,
    "Smartphone": 699.50,
    "Headphones": 149.99,
    "Smartwatch": 249.00,
    "Tablet": 449.99
}

for product, price in product_prices.items():
  print(f"Product: {product} & Price: ${price}")

userSelectionBefore=input("Enter you product: ")
userSelection=userSelectionBefore.title()
print(f"You selected: {userSelection} : ${product_prices[userSelection]}")

choiceBefore=input("A:Add - U:Update - D:Delete")
choice=choiceBefore.title()
if choice=="A":
  nameProduct=input("Enter product name")
  priceProduct=float(input("Enter product price"))
  product_prices[nameProduct]=priceProduct
elif choice=="U":
  nameProduct=input("Enter product name")
  priceProduct=float(input("Enter product price"))
  product_prices[nameProduct]=priceProduct
elif choice=="D":
  nameProduct=input("Enter product name")
  del product_prices[nameProduct]
else:
  print("Enter valid choice...")

for product, price in product_prices.items():
  totalPrice=sum(product_prices.values())
  discount=totalPrice/10
  afterDiscount=totalPrice-(totalPrice/10)
  print(f"Product: {product} & Price: ${price}")
print(f"Sub Total of Products: ${totalPrice:.2f}")
print(f"10% discount of Products: ${discount:.2f}")
print(f"After 10% Discount: ${afterDiscount:.2f}")
```

Output:
```output
Product: Laptop & Price: $999.99
Product: Smartphone & Price: $699.5
Product: Headphones & Price: $149.99
Product: Smartwatch & Price: $249.0
Product: Tablet & Price: $449.99
Enter you product: laptop
You selected: Laptop : $999.99
A:Add - U:Update - D:Deletea
Enter product nameskin
Enter product price44.33
Product: Laptop & Price: $999.99
Product: Smartphone & Price: $699.5
Product: Headphones & Price: $149.99
Product: Smartwatch & Price: $249.0
Product: Tablet & Price: $449.99
Product: skin & Price: $44.33
Sub Total of Products: $2592.80
10% discount of Products: $259.28
After 10% Discount: $2333.52
```

## Project 6 — Password Strength Checker

Concepts: Strings, Boolean operators, conditions, loops.

Create a basic password strength checker. This is a learning exercise, not a complete security validator.

Requirements

Check whether the password:
- Has at least eight characters.
- Contains at least one uppercase letter.
- Contains at least one lowercase letter.
- Contains at least one digit.
Display Strong if all four conditions are met; otherwise, tell the user which requirements are missing.

```code

```











## Running on

### Project 7 — Duplicate Remover
Medium
Concepts: Lists, sets, loops, operators, membership testing.

Create a program that removes duplicate numbers from a list.

Requirements
- Start with a list containing repeated numbers.
- Create a list of unique numbers.
- Preserve the original order.
- Display the original and cleaned lists.
Example:
Original: [10, 20, 10, 30, 20, 40, 30]
Unique:   [10, 20, 30, 40]


Challenge: Also display how many duplicate occurrences were removed.

Hint: Try solving it first with a loop and if number not in unique_numbers, then solve it with sets. Remember that converting directly to a set does not guarantee the original order.

### Project 8 — Student Management System
Medium
Concepts: Dictionaries, lists, loops, conditions, arithmetic, nested data.

Create a simple student management system.

Requirements
- Store multiple students and their marks in a dictionary.
- Display all student records.
- Calculate each student's average.
- Display pass/fail status.
- Find the student with the highest marks.
- Calculate the class average.
Example data:
students = {    "Ali": [75, 80, 90],    "Sara": [90, 95, 92],    "Ahmed": [35, 45, 40],    "Usman": [60, 70, 65]}



Example output:
Ali: Average = 81.67, PASS
Sara: Average = 92.33, PASS
Ahmed: Average = 40.00, FAIL
Usman: Average = 65.00, PASS

Top Student: Sara


Use the rule that a student must score at least 40 in every subject to pass.

Challenge: Add a new student or update an existing student's marks using dictionary operations.

### Project 9 — Bank Account Simulator
Medium
Concepts: Variables, loops, match, conditions, arithmetic, Boolean logic.

Create a command-line banking simulator.

Requirements
- Start with a balance of Rs. 10,000.
- Show a menu with four options: check balance, deposit, withdraw, and exit.
- Use while to keep displaying the menu.
- Use match to handle the selected option.
- Prevent deposits of zero or negative amounts.
- Prevent withdrawals exceeding the available balance.
Example:
1. Check Balance
2. Deposit
3. Withdraw
4. Exit

Choose option: 2
Deposit amount: 2000
Deposit successful.

Current balance: Rs. 12000


Challenge: Keep a list of transaction descriptions and display transaction history.

### Project 10 — Quiz Application
Medium
Concepts: Lists, tuples, dictionaries, loops, conditions, operators, variables.

Build a multiple-choice quiz application.

Requirements
- Store at least five questions.
- Provide four answer choices per question.
- Accept the user's answer.
- Award one point for each correct answer.
- Display whether each answer is correct.
- Show the final score and percentage.
Example:
Question 1: Which type stores key-value pairs?
A. List
B. Tuple
C. Dictionary
D. Set

Your answer: C
Correct!

Final Score: 4/5
Percentage: 80%


Challenge: Add a grade based on the percentage and allow the user to play again.

How to solve these projects successfully
Follow this workflow for each project:
1. Understand the requirements. Write down the inputs, processing steps, and expected output.
2. Plan your logic. Use comments or pseudocode before writing the actual program.
3. Write the code yourself. Avoid looking at complete solutions immediately.
4. Test different cases. Try normal inputs, invalid inputs, zero values, and boundary conditions where applicable.
5. Improve the project. Complete the challenge only after the basic version works.
My recommendation: Solve Projects 1–4 first to strengthen your basics, then Projects 5–10 to combine collections and control flow into complete programs.

When you finish Project 1, send me your code. I'll review it, identify errors, explain improvements, and help you write cleaner Python without simply replacing your work with my own solution







<br>

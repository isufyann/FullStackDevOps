# Project Practice

## Mini-project — Student Management Program
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


# 1. Loop through the dictionary
# 2. Check each student's result
# 3. Print the result
# 4. Calculate the class average
```


<br>

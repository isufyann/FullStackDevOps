# Mini-project: Student Result Calculator
Build this program yourself using today's concepts.

Requirements:
1. Store a student's name.
2. Store marks for three subjects.
3. Calculate the total and average.
4. Display whether the student passed, assuming 40 marks is the minimum in each subject.
5. Print the result in a readable format.

```
This is
```

```code
name = "Ali"

math = 75
english = 65
computer = 90

sum_marks=math+english+computer
avg=sum_marks/3
passed_all=math>=40 and english>=40 and computer>=40

if math >= 40 and english >= 40 and computer >= 40:
    result = "Passed"
    if avg >= 90:
        result += " and Grade A"
    elif avg >= 80:
        result += " and Grade B"
    elif avg >= 70:
        result += " and Grade C"
else:
    result = "Failed"

print(f"Sum is: {sum_marks}")
print(f"Average is: {avg}")
print(f"All students passed:{passed_all}")
print(result)
```

Output:
```text
Sum is: 230
Average is: 76.66666666666667
All students passed:True
Passed and Grade C
```






**Next lesson: Lists, Tuples, Sets, Dictionaries, if...else, match, while loops, for loops, and range().**

<br>

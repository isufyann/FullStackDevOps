# Part C — Python Loops

Loops let you execute code repeatedly without writing the same statements again and again.

## Topic 17 — Python While Loops

A `while` loop repeats while its condition remains true.

### 17.1 Basic while loop

```
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:
```
1
2
3
4
5
```

How it works:
1.	Set `count` to `1`.
2.	Check whether `count <= 5`.
3.	Print the value.
4.	Increase it by one.
5.	Stop when the condition becomes false.

### 17.2 Avoid infinite loops
This loop never ends on its own:
```
# Don't run this example as written!
# count = 1
# while count <= 5:
#     print(count)
``` 
The value never changes, so the condition remains true. Always make sure your loop can eventually stop.

### 17.3 Use break
break immediately exits the loop.
```
count = 1
while count <= 10:
    if count == 5:
        break
    print(count)
    count += 1
```
Output: `1 2 3 4` (each on a separate line).

### 17.4 Use continue
continue skips the remaining statements in the current iteration.
```
count = 0

while count < 10:
    count += 1

    if count == 3:
        continue

    print(count)
```
Output:
```
1
2
4
5
6
7
8
9
```

### 17.5 The while...else pattern
The else block runs if the loop finishes normally, without being stopped by break.

```
count = 1

while count <= 3:
    print(count)
    count += 1
else:
    print("Loop completed")
```
This pattern is useful in some searching and validation tasks, although it is less common than a simple `while` loop.
## Topic 18 — Python For Loops
A for loop iterates over the items in an iterable, such as a list, string, tuple, set, dictionary, or range.
### 18.1 Loop through a list

```
fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)
```

### 18.2 Loop through a string
```
letters="Python"
for letter in letters:
  print(letter)
```
Output:
```
P
y
t
h
o
n
```
### 18.3 Loop through a dictionary
```
student={
    "name":"Ali",
    "age":20,
    "skills":["Python","Java","C++"]
}
for key, value in student.items():
  print(f"{key} | {value}")
```

### 18.4 Use enumerate()
Use enumerate() when you need both the index and value.

```
fruits = ["apple", "banana", "mango"]

for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)
```

Output:
```
1 apple
2 banana
3 mango
```




<br>



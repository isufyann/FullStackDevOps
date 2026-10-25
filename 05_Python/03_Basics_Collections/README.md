# Python Basics — Lesson 3: Collections

In this lesson, we'll cover nine topics from your roadmap. These concepts are essential for building real Python programs and will also help you understand NumPy arrays and data processing later.

Today's learning objectives

- Topic 11: Python Lists
- Topic 12: Python Tuples
- Topic 13: Python Sets
- Topic 14: Python Dictionaries


In Python, lists, tuples, sets, and dictionaries are the four built-in data structures used to store collections of data. Each has unique properties regarding ordering, mutability, and how elements are accessed.

|Data Structure	|Syntax	|Ordered?	|Mutable? (Modifiable)	|Allows Duplicates?	|Core Use Case|
|-|-|-|-|-|-|
|List|	[a, b, c] |	Yes|	Yes|	Yes|	General data storage, stacks, and sequential loops. |
|Tuple|	(a, b, c) |	Yes|	No|	Yes|	Fixed coordinates, dictionary keys, and read-only records. |
|Set|	{a, b, c}|	No|	Yes|	No|	Removing duplicates and fast membership testing (in). |
|Dictionary|	{k: v}|	Yes (3.7+)|	Yes|	Keys: No / Values: Yes|	JSON parsing, databases, and lightning-fast key lookups. |

## 📋 Lists

Lists are dynamic arrays, making them highly flexible for collections where order matters and data might change. 

•	Syntax: fruits = ["apple", "banana", "cherry"] <br>
•	Key Feature: Accessed via numerical indices starting at 0. <br>
•	Common Methods: .append() (add to end), .pop() (remove last), and .sort(). <br>

## 🔒 Tuples

Tuples are essentially "locked" lists. Once created, their items cannot be changed, added, or removed.

•	Syntax: point = (10, 20) (Note: A single-item tuple needs a trailing comma: (5,)). [1, 2] <br>
•	Key Feature: Because they are immutable, they are "hashable" and can be used as keys in a dictionary. [1, 2] <br>
•	Common Methods: Only supports .count() and .index().<br>

## ⚡ Sets

Sets store unordered collections of entirely unique items.

•	Syntax: unique_ids = {1, 2, 3} <br>
•	Key Feature: Finding out if an item is inside a set happens almost instantly (O(1) time complexity), regardless of size. <br>
•	Common Methods: .add(), .remove(), and mathematical operations like .union() and .intersection(). <br>

## 🔑 Dictionaries

Dictionaries store data in key: value pairs, operating like a real-world phonebook or database record. 

•	Syntax: user = {"name": "Alice", "age": 25} <br>
•	Key Feature: You retrieve values using their unique keys rather than an index number. <br>
•	Common Methods: .keys(), .values(), .items(), and .get() <br>


## Part A — Python Collections
Collections let you store multiple values in a single variable.

## Topic 11 — Python Lists
A list stores multiple items in a single variable. Lists are ordered, mutable (changeable), and allow duplicate values.
### 11.1 Create a list
```
fruits = ["apple", "banana", "mango"]

print(fruits)
print(fruits[0])   # apple
print(fruits[-1])  # mango
```

### 11.2 Change, add, and remove items

```
fruits = ["apple", "banana", "mango"]

# Change an item
fruits[1] = "orange"

# Add an item at the end
fruits.append("grapes")

# Insert at a specific index
fruits.insert(1, "kiwi")

# Remove by value
fruits.remove("apple")

# Remove the last item and return it
last_fruit = fruits.pop()

print(fruits)
print(last_fruit)
```
**Important list methods:**

|Method|	Purpose|
|------|---------|
|append(x)|	Add one item at the end|
|extend(items)|	Add multiple items|
|insert(i, x)|	Insert at an index|
|remove(x)|	Remove the first matching value|
|pop(i)|	Remove and return an item|
|sort()|	Sort the list in place|
|reverse()|	Reverse the list in place|
|index(x)|	Find the first matching index|
|count(x)|	Count occurrences|

### 11.3 Slicing lists

```
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])  # [20, 30, 40]
print(numbers[:3])   # [10, 20, 30]
print(numbers[::2])  # [10, 30, 50]
print(numbers[::-1]) # [50, 40, 30, 20, 10]
```

The ending index is excluded.

### 11.4 Loop through a list

```
students = ["Ali", "Sara", "Ahmed"]

for student in students:
    print(student)
```

### 11.5 List comprehension — advanced
A list comprehension creates a new list concisely.
```
numbers = [1, 2, 3, 4, 5]

squares = [n ** 2 for n in numbers]
evens = [n for n in numbers if n % 2 == 0]

print(squares)  # [1, 4, 9, 16, 25]
print(evens)    # [2, 4]
```
***This is particularly useful when cleaning or transforming data.***

### 11.6 Copying lists correctly
```
original = [10, 20, 30]
copy_list = original.copy()

copy_list.append(40)

print(original)   # [10, 20, 30]
print(copy_list)  # [10, 20, 30, 40]
```
Using copy() creates a separate shallow copy. For nested collections, a shallow copy still shares nested objects.


## Topic 12 — Python Tuples
A tuple is an ordered collection that cannot be changed after creation.
### 12.1 Create tuples
```
colors = ("red", "green", "blue")

print(colors[0])
print(colors[-1])
print(len(colors))
```

You can access and slice tuple items just like list items, but you cannot assign new values to their positions.

```
# This raises TypeError:
# colors[0] = "yellow"
```
### 12.2 The single-item tuple rule

```
a = (10)
b = (10,)

print(type(a))  # int
print(type(b))  # tuple
```

The comma creates the single-item tuple.

### 12.3 Tuple unpacking

```person = ("Ali", 30, "Pakistan")

name, age, country = person

print(name)
print(age)
print(country)
```

The number of variables must normally match the number of unpacked items.

You can use * to collect remaining items:

```
numbers = (10, 20, 30, 40, 50)

first, *middle, last = numbers

print(first)   # 10
print(middle)  # [20, 30, 40]
print(last)    # 50
```

### 12.4 When should you use a tuple?
Use a tuple for a fixed group of values, such as coordinates:

```
point = (10, 25)
```

A tuple is immutable, but if it contains a mutable object such as a list, that nested object may still change.

## Topic 13 — Python Sets

A set is a collection of unique items. Sets do not support indexing, and they are useful for removing duplicates and performing mathematical set operations.

### 13.1 Create a set

```
numbers = {10, 20, 30, 20, 10}

print(numbers)
```

Output contains only the unique values:

Output:
```
{10, 20, 30}
```

Set display order is not guaranteed.

An empty set must be created with `set():`

```
empty_set = set()
empty_dict = {}

print(type(empty_set))  # <class 'set'>
print(type(empty_dict)) # <class 'dict'>
```

### 13.2 Add and remove items

```
fruits = {"apple", "banana"}

fruits.add("mango")
fruits.update(["orange", "grapes"])

fruits.discard("banana")

print(fruits)
```

- add() adds one item.
- update() adds items from an iterable.
- discard() removes an item if it exists without raising an error if it's missing.
- remove() raises KeyError if the item does not exist.
- pop() removes and returns an arbitrary item.
  
### 13.3 Set operations — important

```
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

print(a | b)  # Union: {1, 2, 3, 4, 5, 6}
print(a & b)  # Intersection: {3, 4}
print(a - b)  # Difference: {1, 2}
print(a ^ b)  # Symmetric difference: {1, 2, 5, 6}
```


**Remember the difference**

`| All unique items from both sets.`

`&  Only items shared by both sets.`

`-  Items in the first set but not the second.`

### 13.4 Practical example: remove duplicate values

```
student_ids = [101, 102, 101, 103, 102, 104]

unique_ids = set(student_ids)

print(unique_ids)
```

Use sets when you need uniqueness or fast membership checks. If you need to preserve the original order while removing duplicates, use dict.fromkeys() instead:

```
unique_ids = list(dict.fromkeys(student_ids))
print(unique_ids)  # [101, 102, 103, 104]
```
## Topic 14 — Python Dictionaries

A **dictionary** stores data as key-value pairs.

For example, one student might have a name, age, and marks.

### 14.1 Create a dictionary
```
student = {
    "name": "Ali",
    "age": 20,
    "marks": 85
}

print(student["name"])
print(student["marks"])
```

Output:

```
Ali
85
```

Keys must be unique. Dictionaries preserve insertion order in modern Python.

### 14.2 Access and change values

```
student = {
    "name": "Ali",
    "age": 20
}

student["age"] = 21
student["city"] = "Pakpattan"

print(student)
```

Use `get()` to access a key safely:

```
print(student.get("name"))             # Ali
print(student.get("grade", "Not set")) # Not set
```

Unlike `student["grade"]`, which raises `KeyError` if missing, `get()` returns its default value.

### 14.3 Add and remove values

```
student = {"name": "Ali", "age": 20}

student.update({"age": 21, "marks": 90})

removed_age = student.pop("age")

del student["name"]

print(student)     # {'marks': 90}
print(removed_age) # 21
```

Other useful methods include `keys()`, `values()`, `items()`, and `clear()`.


### 14.4 Loop through a dictionary

```
student = {
    "name": "Ali",
    "age": 20,
    "marks": 85
}

for key, value in student.items():
    print(key, ":", value)
```

### 14.5 Nested dictionaries — advanced

```
students = {
    "S101": {"name": "Ali", "marks": 85},
    "S102": {"name": "Sara", "marks": 92}
}

print(students["S102"]["name"])
print(students["S101"]["marks"])
```

Nested dictionaries are useful for representing structured records and API data.

### 14.6 Dictionary comprehension

```
numbers = [1, 2, 3, 4, 5]

squares = {n: n ** 2 for n in numbers}

print(squares)
```
Output:
```
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```








<br>

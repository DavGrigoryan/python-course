<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 19: Sets and Tuples in Python

link to presentation:

- https://www.canva.com/design/DAF1Nm2abNg/JH-b7sK-i0hQTdWYHPST_Q/edit

---

# 1️⃣ Sets in Python

A set is an unordered collection of unique elements.

### 🧠 Example:

```python
my_set = {12, 23, "11", "hello"}
print(my_set)
```

---

### ✳️ Looping through a set

```python
fruits = {'apple', 'banana', 'cherry'}
for f in fruits:
    print(f)
```

---

### ✳️ Combining Sets (Combine sets without duplicates)

```python
a = {'apple', 'banana', 'cherry', 'a'}
b = {'a', 'b', 'c'}
result = a.union(b)
print(result)
```

---

### ✳️ Check if value exists

```python
x = input("Write something: ")
set1 = {'12', '23', '11', 'hello'}
if x in set1:
    print("True")
else:
    print("False")
```

---

### ✳️ Removing elements

```python
set1 = {12, '23', '11', 'hello'}
set1.discard('11')  # չի վերադարձնի error, եթե չգտնի
set1.remove('hello')  # կվերադարձնի error, եթե չգտնի
print(set1)
```

---

### Removing Duplicates

```python
def remove_duplicates(lst):
    return list(set(lst))


print(remove_duplicates([1, 2, 2, 3, 1, 4]))
```

---

### ### ✳️ Sorting Sets

```python
my_set = {'meri', 'ann', 'ann', 'sona', 'anna'}
print(my_set)
print(sorted(my_set))
```

---

---

# 2️⃣ Tuples in Python

A tuple is an ordered and immutable collection (cannot be changed).

### 🧠 Example:

```python
my_tuple = ("apple", "banana", "cherry")
print(my_tuple[0])  # apple
```

---

### ✳️ Looping through a tuple

```python
my_tuple = ("apple", "banana", "cherry")

for x in my_tuple:
    print(x)
```

---

### ✳️ Combining Tuples

```python
tuple1 = ('a', 'b', 'c')
tuple2 = (1, 2, 3, "k")
tuple3 = tuple1 + tuple2
print(tuple3)
```

---

### ✳️ Tuple Slicing

```python
t = ("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")
print(t[-4:-1])  # ('orange', 'kiwi', 'melon')
print(t[::-1])  # reversed order
```

---

### ✳️ Convert Tuple to String

```python
tup = ('e', 'x', 'e', 'r', 'c', 'i', 's', 'e', 's')
mystr = ','.join(tup)
print(mystr)
```

---

### ✳️ Find Unique Numbers in Tuple

```python
x = (5, 4, 6, 4, 6, 7, 5, 8, 9, 9, 9)
for i in x:
    if x.count(i) == 1:
        print(i)
```

---

### ✳️ Reverse Tuple

```python
x = (5, 10, 15, 20)
print(tuple(reversed(x)))  # Reverse version 1
print(x[::-1])  # Reverse version 2
```

---

### ✳️ Sorting Tuples

```python
my_tuple = ('meri', 'ann', 'ann', 'sona', 'anna')
print(my_tuple)
print(sorted(my_tuple))
```

---

# LIST vs TUPLE vs SET

|           | **Mutable** | **Ordered** | **Indexing / Slicing** | **Duplicate Elements** |
|:----------|:-----------:|:-----------:|:----------------------:|:----------------------:|
| **List**  |     🟢      |     🟢      |           🟢           |           🟢           |
| **Tuple** |     🔴      |     🟢      |           🟢           |           🟢           |
| **Set**   |     🟢      |     🔴      |           🔴           |           🔴           |

---

---

# Exercises

### Ex. 1

Ստեղծեք մրգերի SET։ Ավելացրեք նոր միրգ և հեռացրեք մեկը։

---

### Ex. 2

Գրեք ֆունկցիա, որը կստուգի, թե արդյոք TUPLES֊ը պարունակում է դուպլիկատ էլեմենտներ։

---

### Ex. 3

Միավորեք երկու TUPLES և տպեք դրանք հակառակ հերթականությամբ։

---

### Ex. 4

Գրեք ծրագիր, որը դուպլիկատ էլեմենտներով LIST֊ը կվերածի եզակի TUPLES֊ի։

---

### Ex. 5

Հաշվեք, թե քանի անգամ է յուրաքանչյուր տառը հանդիպում TUPLES մեջ։

```python
letters = ('a', 'b', 'a', 'c', 'b', 'a')
```

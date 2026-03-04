<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 📘 Lesson 10: Nested For Loops & Practical Examples

link to presentation:

- https://www.canva.com/design/DAG0zxId2yk/fPEA8ZakVfxOh8Awz84ivQ/edit

---

## 🔹 1. Nested For Loops

A **nested loop** means a loop inside another loop.  
Example:

```python
for i in range(2):  # outer loop
    for j in range(3):  # inner loop
        print(f"i = {i}, j = {j}")
```

---

## 🔹 2. Password Generator Project

### Easy Level (letters → symbols → numbers in order)

```python
import random

letters = list("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ")
numbers = list("0123456789")
symbols = list("!#$%&()*+")

print("Welcome to the PyPassword Generator!")
nr_letters = int(input("How many letters would you like?\n"))
nr_symbols = int(input("How many symbols would you like?\n"))
nr_numbers = int(input("How many numbers would you like?\n"))

password = ""

for _ in range(nr_letters):
    password += random.choice(letters)

for _ in range(nr_symbols):
    password += random.choice(symbols)

for _ in range(nr_numbers):
    password += random.choice(numbers)

print("Your password (easy level):", password)
```

### Hard Level (randomized order)

```python
password_list = []

for _ in range(nr_letters):
    password_list.append(random.choice(letters))

for _ in range(nr_symbols):
    password_list.append(random.choice(symbols))

for _ in range(nr_numbers):
    password_list.append(random.choice(numbers))

random.shuffle(password_list)

password = "".join(password_list)
print("Your password (hard level):", password)
```

---

## 🔹 3. Prime Numbers with Nested Loops

```python
for num in range(2, 20):
    is_prime = True
    for i in range(2, num):
        if num % i == 0:
            is_prime = False
            break
    if is_prime:
        print(num, "is a prime number")
```

---

## 🔹 4. Patterns with Nested Loops

### Rectangle with border

```python
rows = 5
cols = 8

for i in range(rows):
    for j in range(cols):
        if i == 0 or i == rows - 1 or j == 0 or j == cols - 1:
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```

---

## 🔹 5. Lists with Loops

### Find common elements

```python
list1 = [1, 2, 3, 4, 5]
list2 = [3, 4, 5, 6, 7]
common = []

for element in list1:
    if element in list2:
        common.append(element)

print("Common elements:", common)
```

---

# **Exercises 📝**

---

### 1.Ունենք թվերի list(8-10 Էլեմենտ), list-ում այն թվերը որոնք 20ից փոքր են թող գումարվեն 1-ով:

<details> <summary>💡 Solution</summary>

```python
numbers = [5, 12, 25, 18, 30, 7, 40, 19]

for i in range(len(numbers)):
    if numbers[i] < 20:
        numbers[i] += 1

print(numbers)
```

</details>

---

### 2.words = ["apple", "banana", "kiwi", "orange", "mango": target_word = "kiwi" ( գրել կոդ որ կասի մեր target_word-ը կա list-ում թե ոչ

<details> <summary>💡 Solution</summary>

```python
words = ["apple", "banana", "kiwi", "orange", "mango"]
target_word = "kiwi"

if target_word in words:
    print("Yes,", target_word, "is in the list")
else:
    print("No,", target_word, "is not in the list")
```

</details>

---

### 3. Գտնել երկու ցուցակների ընդհանուր էլեմենտները։

<details> <summary>💡 Solution</summary>

```python
list1 = [1, 2, 3, 4, 5]
list2 = [3, 5, 7, 9]
common = []

for el in list1:
    if el in list2:
        common.append(el)

print("Common elements:", common)
```

</details>

---

### 4. Գտնել երկու ցուցակների տարբերությունը (որոնք կան list1-ում, բայց չկան list2-ում)։

<details> <summary>💡 Solution</summary>

```python
list1 = [1, 2, 3, 4, 5]
list2 = [3, 5, 7, 9]
difference = []

for el in list1:
    if el not in list2:
        difference.append(el)

print("Difference (list1 - list2):", difference)
```

</details>

---

### 5. Գտնել, արդյոք ցուցակում կա կրկնվող էլեմենտ։

<details> <summary>💡 Solution</summary>

```python
nums = [1, 2, 3, 4, 2, 5, 6]
duplicate_found = False

for i in range(len(nums)):
    for j in range(i + 1, len(nums)):
        if nums[i] == nums[j]:
            duplicate_found = True

if duplicate_found:
    print("There are duplicates in the list")
else:
    print("No duplicates found")
```

</details>

---

### 6. Հաշվել, թե քանի անգամ է որևէ բառ կրկնվում ցուցակում։

<details> <summary>💡 Solution</summary>

```python
words = ["apple", "banana", "apple", "orange", "apple", "banana"]
target = "apple"
count = 0

for word in words:
    if word == target:
        count += 1

print(f"The word '{target}' appears {count} times")
```

</details>

---

### 7. Գտնել ցուցակի ամենամեծ և ամենափոքր թիվը

<details> <summary>💡 Solution</summary>

```python
nums = [12, 45, 2, 67, 34, 89, 1, 23]

max_num = nums[0]
min_num = nums[0]

for num in nums:
    if num > max_num:
        max_num = num
    if num < min_num:
        min_num = num

print("Max:", max_num)
print("Min:", min_num)
```

</details>

---

### 8.Print անել սովորական եռանկյուն

<details> <summary>💡 Solution</summary>

```python
rows = 5

for i in range(1, rows + 1):
    print("* " * i)
```

</details>

---

### 9.Print անել սովորական լիքը ուղղանկյուն

<details> <summary>💡 Solution</summary>

```python
rows = 4
cols = 6

for i in range(rows):
    print("* " * cols)

```

</details>

---

### 10.Print անել դատարկ ուղղանկյուն եռանկյուն

<details> <summary>💡 Solution</summary>

```python
size = 5
for i in range(size):
    for j in range(size):
        if i == size - 1 or j == 0 or j == i:
            print('*', end=' ')
        else:
            print(' ', end=' ')
    print(" ")
```

or

```python
size = 5
for i in range(size):
    for j in range(size):
        if i == size - 1 or j == size - 1 or j == (size - i - 1):
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```

</details>



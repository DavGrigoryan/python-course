<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 2 – Variables, Data Types & Debugging

link to presentation: https://www.canva.com/design/DAFxhnYSkWk/-8YLK79MR2nSmIpdFZXS5Q/edit

---

## 1. Review of Lesson 1

- `print()` and `input()`
- Concatenation
- Band Name Generator mini-project

---

## 2. Debugging Basics

### Common Errors

- **SyntaxError**: broken or missing quotes
- **IndentationError**: wrong indentation
- **NameError**: using a variable that doesn’t exist
- **TypeError**: mixing incompatible types (e.g., string + int)

#### Exercise:

Spot and fix the errors:

```
# 1. Missing parenthesis
print("Hello, World!"

# 2. Block is not properly indented
x = 10
if x > 5:
print("x is greater than 5")

# 3. Using undefined variable
print(anum)

# 4. Mixing types
print("Age: " + 6)
```

<details> <summary>💡 Solution</summary>

```python
# 1. Correct syntax
print("Hello, World!")

# 2. Add the correct indentation
x = 10
if x > 5:
    print("x is greater than 5")

# 3. Define the variable first
anum = "Ani"
print(anum)

# 4. Convert number to string
print("Age: " + str(6))
```

</details>

---

## 3. Comments

```python
# This is a single-line comment
# Comments are ignored by Python
print("Hello!")  # Inline comment

"""
This is a comment
written in
more than just one line
"""

```

---

## 4. Variables

- Variables store data values
- Case-sensitive (name ≠ Name)
- Naming rules: use descriptive names, avoid starting with numbers

#### Example case-sensitive:

```python
name = "Petros"
Name = "Different"

print(name)
print(Name)
```

### Example naming rules:

- 🟢 Legal variable names:

```python
myvar = "John"
my_var = "John"
_my_var = "John"
myVar = "John"
MYVAR = "John"
myvar2 = "John"
```

- 🔴 Illegal variable names:

```python
2 = "text"
2
var = "text"
myvar = "John"
my - var = "John"
my
var = "John"
```

---

## 5. Data Types

#### Main types in Python:

- **String** → `"Hello"`
- **Integer** → `56`
- **Float** → `1.25`
- **Boolean** → `True`, `False`

#### Example:

```python
print(type("Hello"))  # str
print(type(56))  # int
print(type(1.25))  # float
print(type(True))  # bool
```

---

## 6. The len() Function

- len() works on sequences (strings, lists, etc.), not on numbers

#### Example:

```python
word = "Python"
print(len(word))  # 6
```

#### Exercise:

```python
# 1. Ask the user for their name and print how many letters it has.
```

<details> <summary>💡 Solution</summary>

```python
name = input("What is your name? ")
print("Your name has " + str(len(name)) + " letters.")
```

</details>

---

## 7. Type Conversion

- `str()`, `int()`, `float()`, `bool()`
- Used to switch between types

#### Example

```python
age = 25
print("I am " + str(age) + " years old")

print(int(5.9))  # 5
print(float(5))  # 5.0
```

#### Exercise:

```python
# 1. Convert "123" (string) to an integer and add 10
# 2. Convert 7 (integer) to a string and concatenate with " apples"
```

<details> <summary>💡 Solution</summary>

```python
# 1
num = int("123")
print(num + 10)  # 133

# 2
apples = str(7) + " apples"
print(apples)
```

</details>

---

## 8. Errors with Type Conversion

```python
# This will fail (string is not a number)
x = int("hello")  # ValueError
```

---

## 9. Summary

- Comments types
- Variables and naming rules
- Data types: str, int, float, bool
- `len()` function
- Type conversion (`str`, `int`, `float`)
- Common errors and debugging practice

---

# Exercise

## Exercise 1 – Favorite Movie 🎬

- Հարցրու օգտատիրոջ անունը։
- Հարցրու իր սիրելի ֆիլմը։
- Տպիր այսպես՝ `Hello <name>! Your favorite movie is <movie>.`

## Exercise 2 – Name Length 🔤

- Հարցրու օգտատիրոջ անունը։
- Տպիր անունի տառերի քանակը len()-ով։
- Օգտագործիր type conversion (ստացվի string + number concatenation)։

## Exercise 3 – Age in Months 📅

- Հարցրու օգտատիրոջ տարիքը։
- Հաշվիր նրա ամիսներով տարիքը (տարիք × 12)։
- Տպիր արդյունքը։

## Exercise 4 – Debug the Code 🐞

Ուղղել այս կոդը՝

```python
print("Hello, my name is " + name)
name = input("What is your name? ")
```

# Exercise 5 – Fruit Basket 🍎

- Հարցրու օգտատիրոջը՝ իր սիրելի միրգը։
- Հարցրու, թե քանի հատ այդ միրգ ունի (integer)։
- Տպիր այսպես՝ `You have <number> <fruit>(s) in your basket.`

## Exercise 6 – Username & Password Generator 🧩

1. Հարցրու օգտատիրոջը իր անունը և ծննդյան տարեթիվը։
2. Ստեղծել **username** միավորելով անունը և տառերի քանակը
    - Օրինակ՝ `Ani` → `Ani3`
3. Ստեղծել  **գաղտնաբառ**՝ համատեղելով ծննդյան տարեթիվը և անվան առաջին տառը:
    - Օրինակ՝ `2000` and `Ani` → `2000A`
4. Տպել օգտվողի անունը և գաղտնաբառը:

Կոդի աշխատանքի օրինակ՝

```yaml
Enter your first name: Ani
Enter your birth year: 2000

Your username is: Ani3
Your password is: 2000A
```

<details> <summary>💡 Solution</summary>

```python
name = input("Enter your first name: ")
birth_year = input("Enter your birth year: ")

# Username = name + number of letters
username = name + str(len(name))

# Password = birth year + first letter of the name
password = birth_year + name[0].upper()

print("Your username is:", username)
print("Your password is:", password)
```

</details>



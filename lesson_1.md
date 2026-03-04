<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 📘 Lesson 1 - Python Introduction

link to presentation: https://www.canva.com/design/DAFxXLLmm6E/PiB6fciPqR13ORVwFzh8wQ/edit

---

- Created: **1991**
- Creator: **Guido van Rossum**
- Used for:
    - Web development (Վեբ ծրագրավորում)
    - Data science & analytics (Տվյալների գիտություն և վերլուծություն)
    - Artificial intelligence & machine learning (Արհեստական բանականություն և մեքենայական ուսուցում)
    - Automation & testing (Ավտոմատացում և թեստավորում)

### First program:

```python
print("Hello, World!")
```

---

## 2. Printing in Python

- Printing text and numbers:

```python
print(8)
print("Hello")
print("it's your dog")
```

- Special characters:

```python
print("Hello\nHow are you?")
print("Name\tAge")
```

---

## 3. Strings and Concatenation

- Joining words together:

```python
print("Hello" + " " + "World")
```

---

## 4. Input from User

- Basic input:

```python
input()
input("What is your name? ")
print(input("What is your name? "))
```

- Input with variable:

```python
name = input("What is your name? ")
print("Hello, " + name)
```

---

## 5. Variables

- Storing and reusing values:

```python
age = 25
print(age)
```

---

## 6. Common Errors

### A)

- Broken:

```python
print(Welcome
to
the
Name
Generator!)
```

<details>
<summary> 💡 Fix </summary>

```python
print("Welcome to the Name Generator!")
```

</details>

### B)

- Broken:

```python
print("Hello)
```

<details>
<summary> 💡 Fix </summary>

```python
print("Hello")
```

</details>


---

# Exercise

## Exercise 1 – Band Name Generator 🎸

- Create a small program that asks the user two questions (city and pet name).
- Make sure each input prompt shows the input cursor on a new line.
- Print the resulting band name as: `Your band name could be <city> <pet>`.

<details>
<summary> 💡 Solution </summary>

```python
print("Welcome to the Band Name Generator!")

city = input("Which city did you grow up in?\n")
pet = input("What's your pet's name?\n")

print("Your band name could be " + city + " " + pet)
```

#### Alternative solution:

```python
print("Welcome to the Band Name Generator!")

city = input("Which city did you grow up in?\n")
pet = input("What's your pet's name?\n")

print(f"Your band name could be {city} {pet}")
```

</details>

## Exercise 2 – Restaurant Order 🍔

- Հարցրու օգտատիրոջը իր սիրելի ուտելիքի անունը։
- Հարցրու իր սիրելի խմիչքի անունը։
- Տպիր այսպես՝ `Your order is: <food> with <drink>.`

## Exercise 3 – Nickname Maker 😎

- Հարցրու օգտատիրոջը իր անունը։
- Հարցրու իր սիրելի թիվը։
- Տպիր այսպես՝ `Your cool nickname is: <name><number>`

## Exercise 4 – Future Age Calculator ⏳

- Հարցրու օգտատիրոջ անունը։
- Հարցրու իր ներկայիս տարիքը։
- Տպիր այսպես՝ `Hey <name>! In 5 years you will be <age+5> years old.`

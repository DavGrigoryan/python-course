<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 8: Random Numbers and Lists in Python

link to presentation:

- https://www.canva.com/design/DAFzMbjwjZo/Xg3ODzw6I6YUWv6GXe1qOw/edit
- https://www.canva.com/design/DAGO2kpXwPA/eUkpqnxtCvDs68V-DqDcUg/edit

---

**1. Random Numbers**

Python has a built-in module called `random` that lets us generate random numbers or pick random items.

**Example 1: Generate a random integer**

```python
import random

number = random.randint(1, 10)  # random integer between 1 and 10
print("Random number:", number)
```

```python
import random

value = random.random()  # float between [0.0, 1.0)
print("Random float:", value)

value2 = random.random() * 5  # float between [0.0, 5.0)
print("Random float (0-5):", value2)
```

---

**2. Random Choice from a List**  
We can pick a random item from a list using random.choice()

```python
import random

colors = ["red", "blue", "green", "yellow"]
random_color = random.choice(colors)
print("Chosen color:", random_color)
```

---

**3. Working with Lists**

```python
fruits = ["apple", "banana", "cherry"]
print(fruits)
```

**Access elements**

```python
print(fruits[0])  # first element
print(fruits[-1])  # last element
```

**Modify a list**

```python
fruits[1] = "pear"  # change value
fruits.append("orange")  # add at the end
fruits.insert(1, "kiwi")  # insert at index 1
print(fruits)
```

**Remove items**

```python
fruits.remove("pear")  # remove by value
fruits.pop()  # remove last
print(fruits)
```

---

**4. Mini Project – Coin Toss Game**

```python
import random

flip = random.randint(0, 1)
if flip == 0:
    print("Heads")
else:
    print("Tails")
```

---

# **Exercises 📝**

**Exercise 1: Dice Roll**

Գրեք ծրագիր, որը մոդելավորում է զառ գլորելը (պատահական թիվ 1-ից 6 միջակայքում):

<details> <summary>💡 Solution</summary>

```python
import random

dice_roll = random.randint(1, 6)
print(f"You rolled: {dice_roll}")
```

</details>

---

**Exercise 2: Random Fruit Picker**

Create a list of fruits. Program should randomly choose one and print it.


<details> <summary>💡 Solution</summary>

```python
import random

fruits = ["apple", "banana", "cherry", "pear", "orange"]
random_fruit = random.choice(fruits)
print(f"Random fruit: {random_fruit}")
```

</details>

---

**Exercise 3: List Operations**

Start with `["cat", "dog", "rabbit"]`.

- Add `elephant`.

- Remove `dog`.

- Insert `lion` at index `1`.
  Print the final list.

<details> <summary>💡 Solution</summary>

```python
animals = ["cat", "dog", "rabbit"]

# Add "elephant"
animals.append("elephant")

# Remove "dog"
animals.remove("dog")

# Insert "lion" at index 1
animals.insert(1, "lion")

print("Final list:", animals)
```

</details>

---

**Exercise 4: Rock–Paper–Scissors (Challenge 🎮)**

Ask the user to type `0` for Rock, `1` for Paper, `2` for Scissors.  
The computer should also choose randomly.  
Decide who wins.


<details> <summary>💡 Solution</summary>

```python
import random

# 0 = Rock, 1 = Paper, 2 = Scissors
choices = ["Rock", "Paper", "Scissors"]

user_choice = int(input("Type 0 for Rock, 1 for Paper, or 2 for Scissors: "))
computer_choice = random.randint(0, 2)

print(f"You chose: {choices[user_choice]}")
print(f"Computer chose: {choices[computer_choice]}")

if user_choice == computer_choice:
    print("It's a draw!")
elif (user_choice == 0 and computer_choice == 2) or
        (user_choice == 1 and computer_choice == 0) or
        (user_choice == 2 and computer_choice == 1):
    print("You win! 🎉")
else:
    print("You lose 😢")
```

</details>




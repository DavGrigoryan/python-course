<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 📘 Lesson 11: While Loop

link to presentation:

- https://www.canva.com/design/DAG0z0fa8y8/75IsZdhOBSVzTJXKRfhBtQ/edit

---

## 🔹 1. Basic While Loop

```python
i = 5
while i > 0:
    print(i)
    i -= 1
print("Done!")
```

🧩 Explanation:

- Starts from `i = 5`
- Prints numbers until `i` becomes 0
- Each time decreases `i` by 1
- Finally prints `Done!`

---

## 🔹 2. Infinite Loop Example

```python
while 5 > 3:
    print("This will run forever!")
```

💡 Be careful! This condition is always true.

---

## 🔹 3. Using If Inside While

```python
num = 1
while num <= 10:
    if num % 2 == 1:
        print(num)
    num += 1
```

📘 Prints all odd numbers between 1 and 10.

---

## 🔹 4. Sum of Numbers Using While

```python
sum = 0
num = 1

while num <= 5:
    sum += num
    num += 1

print("Sum of first 5 numbers:", sum)
```

🧮 Adds numbers from 1 to 5 → Result: 15

---

## 🔹 5. Validate User Input

```python
user_input = input("Enter 'yes' or 'no': ")

while user_input not in ['yes', 'no']:
    print("Invalid input. Please enter 'yes' or 'no'.")
    user_input = input("Enter 'yes' or 'no': ")

print("You entered:", user_input)
```

💡 Keeps asking until user types 'yes' or 'no'.

---

## 🔹 6. Break, Continue, Else Example

```python
i = 1
while i < 6:
    if i == 3:
        print("Skipping number 3")
        i += 1
        continue
    print(i)
    i += 1
```

📘 Skips the number 3 and continues the loop.

---

## 🔹 7. Password Checker

```python
password = "secret"
attempts = 3

while attempts > 0:
    user_password = input("Enter password: ")
    if user_password == password:
        print("Access granted ✅")
        break
    else:
        print("Wrong password! Try again.")
        attempts -= 1
else:
    print("Access denied. Too many incorrect attempts.")
```

🔐 Allows 3 tries to enter the correct password.

---

## 🔹 8. Guess the Number Game

```python
import random

secret_number = random.randint(1, 10)
guess = int(input("Guess a number between 1 and 10: "))

while guess != secret_number:
    print("Try again!")
    guess = int(input("Guess again: "))

print("🎉 Congratulations! The secret number was:", secret_number)
```

🎮 Classic guessing game using while.

---

# Exercises 📝

### 1. Գրիր ծրագիր, որը while ցիկլով կտպի բոլոր զույգ թվերը 1-ից մինչև 20։

<details> <summary>💡 Solution</summary>

```python
num = 1

while num <= 20:
    if num % 2 == 0:
        print(num)
    num += 1
```

</details>

---

### 2. Հարցրու օգտատիրոջից թվեր, մինչև նա գրի "stop"։ <br> Վերջում տպիր բոլոր մուտքագրած թվերի գումարը։

<details> <summary>💡 Solution</summary>

```python
total = 0

while True:
    user_input = input("Մուտքագրիր թիվ կամ 'stop'՝ ավարտելու համար: ")

    if user_input == "stop":
        break
    total += int(user_input)

print("Գումարը =", total)
```

</details>

---

### 3. Գրիր ծրագիր, որը ունի գաղտնաբառ (օր. "python123")։ <br> Օգտատերը ունի 5 փորձ այն ճիշտ մուտքագրելու համար։ <br> Եթե բոլոր փորձերն էլ սխալ են լինում, տպիր "Շատ փորձեր եք արել!"։

<details> <summary>💡 Solution</summary>

```python
correct_password = "python123"
attempts = 0
max_attempts = 5

while attempts < max_attempts:
    password = input("Մուտքագրիր գաղտնաբառը: ")

    if password == correct_password:
        print("✅ Գաղտնաբառը ճիշտ է!")
        break
    else:
        print("❌ Սխալ գաղտնաբառ:")
        attempts += 1

if attempts == max_attempts:
    print("Շատ փորձեր եք արել!")
```

</details>

---

### 4. Հարցրու օգտատիրոջից թվեր այնքան ժամանակ, քանի դեռ նա չի մուտքագրել 0։ <br> Վերջում տպիր, թե քանի թիվ է մուտքագրվել (բացի 0-ից)։

<details> <summary>💡 Solution</summary>

```python
count = 0

while True:
    num = int(input("Մուտքագրիր թիվ (0՝ դադարեցնելու համար): "))

    if num == 0:
        break
    count += 1

print("Դու մուտքագրել ես", count, "թիվ։")
```

</details>

---

### 🔐 Exercise 7 — Guess the Number Game 🎯

Ծրագիրը պետք է ունենա գաղտնի թիվ (օր. secret = 7)։  
Օգտատերը պետք է փորձի գուշակել այն։  
Եթե սխալ է գուշակում, ծրագիրը շարունակում է հարցնել նոր թիվ։  
Երբ ճիշտ է գուշակում, ծրագիրը տպում է՝

`Շնորհավոր, ճիշտ ես գուշակել!`

💡 Հուշում`

Օգտագործիր while `guess != secret:` ցիկլ։

<details> <summary>💡 Solution</summary>

```python
secret = 7
guess = int(input("Գուշակի՛ր թիվը (1-10): "))

while guess != secret:
    print("Սխալ գուշակում, փորձիր նորից!")
    guess = int(input("Գուշակի՛ր թիվը (1-10): "))

print("🎉 Շնորհավոր, ճիշտ ես գուշակել!")
```

</details>

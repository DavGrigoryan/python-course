<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 5: Conditions (if, elif, else)

link to presentation: https://www.canva.com/design/DAFyPLpn-Zo/5dCYie-7z1ILKRccsZTunA/edit

---

**🔹 Checking Strings**

```python
x = input("Enter a word: ")

if x.isupper():
    print("All letters are uppercase")
elif x.islower():
    print("All letters are lowercase")
else:
    print("Mixed letters")
```

**🔹 Traffic Light Example**

```python
light = input("Enter traffic light color (red, yellow, green): ")

if light == "red":
    print("Stop!")
elif light == "yellow":
    print("Get ready")
elif light == "green":
    print("Go!")
else:
    print("Invalid color")
```

**🔹Mini Project – Pizza Order 🍕**

```python
size = input("Choose size (S, M, L): ")
add_cheese = input("Do you want extra cheese? (yes/no): ")

bill = 0

if size == "S":
    bill += 5
elif size == "M":
    bill += 10
elif size == "L":
    bill += 15

if add_cheese == "yes":
    bill += 2

print(f"Your total bill is ${bill}")
```

---

# Exercise

## 1. Even or Odd 🔢

Հարցրու թիվ և տպիր՝ զույգ է թե կենտ։

<details> <summary>💡 Solution</summary>

```python
num = int(input("Enter a number: "))

if num % 2 == 0:
    print("Even")
else:
    print("Odd")
```

</details>

## 2. Positive, Negative or Zero ➕➖0️⃣

Հարցրու թիվ։ Տպիր՝ դրական է, բացասական, թե հավասար է զրոյի։

<details> <summary>💡 Solution</summary>

```python
num = int(input("Enter a number: "))

if num > 0:
    print("Positive")
elif num < 0:
    print("Negative")
else:
    print("Zero")
```

</details>

## 3. Password Strength 🔒

Հարցրու գաղտնաբառ։ Եթե երկարությունը < 5 → “Too weak”, եթե 5-8 → “Medium”, եթե > 8 → “Strong”。

<details> <summary>💡 Solution</summary>

```python
password = input("Enter password: ")

if len(password) < 5:
    print("Too weak")
elif len(password) <= 8:
    print("Medium")
else:
    print("Strong")
```

</details>

## 4. Movie Ticket Price 🎬

Հարցրու տարիքը։ Եթե < 12 → $5, եթե 12–18 → $7, եթե ≥ 18 → $10։

<details> <summary>💡 Solution</summary>

```python
age = int(input("Enter your age: "))

if age < 12:
    price = 5
elif age <= 18:
    price = 7
else:
    price = 10

print(f"Ticket price: ${price}")
```

</details>

## 5. Temperature Check 🌡️

Հարցրու ջերմաստիճան։

- Եթե < 0 → “Freezing”
- Եթե 0–20 → “Cold”
- Եթե 21–30 → “Warm”
- Եթե > 30 → “Hot”

<details> <summary>💡 Solution</summary>

```python
temp = int(input("Enter temperature: "))

if temp < 0:
    print("Freezing")
elif temp <= 20:
    print("Cold")
elif temp <= 30:
    print("Warm")
else:
    print("Hot")
```

</details>

## 6. Simple Calculator ➕➖✖️➗

Հարցրու երկու թիվ և գործողություն (+, -, *, /)։ Կատարիր գործողությունը։

<details> <summary>💡 Solution</summary>

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))
op = input("Enter operation (+, -, *, /): ")

if op == "+":
    print(a + b)
elif op == "-":
    print(a - b)
elif op == "*":
    print(a * b)
elif op == "/":
    if b != 0:
        print(a / b)
    else:
        print("Error: division by zero")
else:
    print("Invalid operation")
```

</details>



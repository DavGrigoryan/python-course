<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 30 – Introduction to Object-Oriented Programming (OOP)

## 1. What is OOP?

- OOP = Object-Oriented Programming
- Focuses on **objects**: things that have **attributes (data)** and **methods (behavior)**
- Real-world example: A **Car**
    - Attributes → color, brand, speed
    - Methods → drive(), stop()

---

## 2. Defining a Class

**Class**֊ը **օբյեկտի (object)** ստեղծելու նախագիծ է։

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

    def drive(self):
        print(f"The {self.color} {self.brand} is driving.")
```

---

## 3. Creating Objects

Մենք կարող ենք նույն class֊ից ստեղծել մի քանի օբյեկտներ

```python
car1 = Car("Toyota", "red")
car2 = Car("BMW", "black")

car1.drive()  # The red Toyota is driving.
car2.drive()  # The black BMW is driving.
```

---

## 4. Attributes and Methods

- **Attributes** → փոփոխականներ, որոնք պատկանում են օբյեկտին (`brand`, `color`)
- **Methods** → ֆունկցիաները class֊ի ներսում (`drive`)

```python
print(car1.brand)  # Toyota
print(car2.color)  # black
```

---

## 5. Adding More Functionality

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print(f"My name is {self.name}, and I am {self.age} years old.")


s1 = Student("Anna", 21)
s2 = Student("Petros", 19)

s1.introduce()
s2.introduce()
```

---

## 6. Exercise

Ստեղծեք class Dog օգտագործելով՝:

- Attributes: name, breed, age
- Methods: `bark()` (prints `Woof!`) and `info()` (prints `My dog’s name is <name>, a <age> year old <breed>.`)

<details> <summary>💡 Solution</summary>

```python
class Dog:
    def __init__(self, name, breed, age):
        self.name = name
        self.breed = breed
        self.age = age

    def bark(self):
        print("Woof!")

    def info(self):
        print(f"My dog's name is {self.name}, a {self.age}-year-old {self.breed}.")


dog1 = Dog("Rex", "German Shepherd", 5)
dog1.bark()
dog1.info()
```

</details>

---

## 7. Why OOP?

- Ավելի լավ է կազմակերպում կոդը
- Վերօգտագործելիություն (կարող է ստեղծել բազմաթիվ օբյեկտներ մեկ class֊ից)
- Ավելի հեշտ է կառավարել ավելի մեծ նախագծեր
- Իրական աշխարհի մոդելավորում

## 8. Homework ✍️

1. Ստեղծեք `BankAccount` class:
    - Attributes: `owner`, `balance`
    - Methods: `deposit(amount)`, `withdraw(amount)`, `display_balance()`
    - Համոզվեք, որ կանխիկացումը (withdraw) ավելի մեծ գումար քան balance֊ն է ցուցադրվում է error message` «Անբավարար միջոցներ» ("Insufficient funds.")

2. Create 2 accounts and test deposits/withdrawals.

<details> <summary>💡 Solution</summary>

#### 1. Create a `BankAccount` class:

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount):
        """Add money to the account"""
        self.balance += amount
        print(f"{amount} deposited. New balance: {self.balance}")

    def withdraw(self, amount):
        """Withdraw money if there are enough funds"""
        if amount > self.balance:
            print("Insufficient funds.")
        else:
            self.balance -= amount
            print(f"{amount} withdrawn. New balance: {self.balance}")

    def display_balance(self):
        """Show current balance"""
        print(f"Owner: {self.owner}, Balance: {self.balance}")
```

#### 2. Create 2 accounts and test deposits/withdrawals

```python
# Create accounts
acc1 = BankAccount("Anna", 100)
acc2 = BankAccount("Petros")

# Check balances
acc1.display_balance()  # Owner: Anna, Balance: 100
acc2.display_balance()  # Owner: Petros, Balance: 0

# Deposit money
acc1.deposit(50)  # 50 deposited. New balance: 150
acc2.deposit(200)  # 200 deposited. New balance: 200

# Withdraw money
acc1.withdraw(70)  # 70 withdrawn. New balance: 80
acc2.withdraw(250)  # Insufficient funds.

# Final balances
acc1.display_balance()
acc2.display_balance()
```

</details>

---


<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 32 – Object-Oriented Programming (OOP) – Part 3

## OOP 4 Principles

- INHERITANCE
- ENCAPSULATION
- ABSTRACTION
- POLYMORPHISM

## 👉 Encapsulation (Կապսուլա 💊)

---

### 1. Simple Class Review

```python
class Person:
    def __init__(self, name, age):
        self.name = name            # public
        self._email = None          # protected
        self.__password = "1234"    # private
```

- public → everyone can access (բոլորը կարող են մուտք գործել)
- _protected → used inside class & subclasses (օգտագործվում է դասի և ենթադասերի ներսում)
- __private → visible only in this class (տեսանելի է միայն տվյալ դասում)

---

### 2. Getters & Setters

```python
class BankAccount:
    def __init__(self, owner, balance):
        self.owner = owner
        self.__balance = balance  # private

    def get_balance(self):
        return self.__balance

    def set_balance(self, amount):
        if amount < 0:
            print("Balance cannot be negative.")
        else:
            self.__balance = amount
```

Usage (Օգտագործում):

```python
acc = BankAccount("Anna", 1000)
print(acc.get_balance())

acc.set_balance(500)
print(acc.get_balance())
```

---

### 3. Preventing Wrong Data (Սխալ տվյալների կանխարգելում)

```python
class Student:
    def __init__(self, name):
        self.name = name
        self.__grade = None

    def set_grade(self, grade):
        if 0 <= grade <= 100:
            self.__grade = grade
        else:
            print("Invalid grade!")

    def get_grade(self):
        return self.__grade
```

---

## Exercise

### 1. Ստեղծեք User class։

- Պետք է ունենա private(անձնական) գաղտնաբառ՝ __password
- Ավելացրեք getter՝ check_password(password)
- Ավելացրեք setter՝ change_password(old, new)

### 2. Ստեղծեք Product class։

- Պետք է ունենա private(անձնական) գին __price
- Ավելացրեք setter՝ որպիսի կանխենք գինը փոքր չլինի 0֊ից
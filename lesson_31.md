<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 31 – Object-Oriented Programming (OOP) – Part 2

## OOP 4 Principles

- INHERITANCE
- ENCAPSULATION
- ABSTRACTION
- POLYMORPHISM

## 👉 INHERITANCE (Ժառանգականություն)

---

## 1. Simple Class Review

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        print("Dog says Woof!")
```

```python
my_dog = Dog("Buddy", 3)
your_dog = Dog("Jeko", 5)

print(f"{my_dog.name} is {my_dog.age} years old.")
my_dog.bark()
your_dog.bark()
```

---

### 2. 🐾 Inheritance (Ժառանգում)

Inheritance նշանակում է՝

- ✔ ստեղծել նոր դաս (child class)
- ✔ որը ժառանգում է ուրիշ class-ից (parent class)

```python
class Animal:
    def __init__(self, name, legs):
        self.name = name
        self.legs = legs

    def eat(self):
        print("All animals eat.")
```

**Child classes (ժառանգվող դասեր)**

```python
class Cat(Animal):
    def speak(self):
        return f"{self.name} says Meow!"


class Dog(Animal):
    def speak(self):
        return f"{self.name} says Woof!"
```

**Usage (օգտագործում)**

```python
my_cat = Cat("Whiskers", 4)
my_dog = Dog("Buddy", 4)

print(my_cat.speak())
my_cat.eat()

print(my_dog.speak())
```

---

### 3. Updating Attributes Dynamically (Ատրիբուտների դինամիկ թարմացում)

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display_details(self):
        print(f"Name: {self.name}, Age: {self.age}")
```

**Create person (Ստեղծել անձ)**

```python
initial_name = input("Enter the name: ")
initial_age = int(input("Enter the age: "))
person = Person(initial_name, initial_age)
```

**Update person (Թարմացնել անձը)**

```python
new_name = input("Enter the new name: ")
new_age = int(input("Enter the new age: "))

person.name = new_name
person.age = new_age

person.display_details()
```

---

### 4. Small User Registration / Login System

**List of existing users (Գոյություն ունեցող օգտատերերի ցանկ)**

```python
users = [
    {
        "name": "John",
        "age": 18,
        "login": "john1234",
        "password": "123456789"
    },
]
```

Person class (Անձի class)

```python
class Person:
    def __init__(self, name, age, login, password):
        self.name = name
        self.age = age
        self.login = login
        self.password = password

    def display_details(self):
        print(f"Name: {self.name}, Age: {self.age}")
```

Register function - creates a new user (Գրանցման ֆունկցիա - ստեղծում է նոր օգտատեր)

```python
def register():
    name = input("Type your name: ")
    age = int(input("Type your age: "))
    login = input("Type your login: ")
    password = input("Type your password: ")

    person = Person(name, age, login, password)
    users.append(vars(person))  # vars() → converts object to dict
```

**Login logic (Մուտքի տրամաբանություն)**

```python
answer = input("Do you already have an account? (y/n)")

if answer.lower() == "n":
    register()

elif answer.lower() == "y":
    login = input("Type your login: ")
    password = input("Type your password: ")

    for user_dict in users:
        person = Person(**user_dict)  # convert dict → Person object
        if person.login == login and person.password == password:
            person.display_details()
            break
    else:
        print("There is no user with these details.")

```

---

## Exercise

### 1. Create a base class Vehicle and two child classes Car and Bike.

- Vehicle has: brand
- Car has: wheels = 4
- Bike has: wheels = 2
- Method: info() → print brand and wheels


### 2. Create an Login system that also checks minimum age (18+)

---


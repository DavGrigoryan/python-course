<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 33 – Object-Oriented Programming (OOP) – Part 4

## OOP 4 Principles

- INHERITANCE
- ENCAPSULATION
- ABSTRACTION
- POLYMORPHISM

## 👉 ABSTRACTION (Աբստրակցիա)

- ✔ Մենք ստեղծում ենք ընդհանուր կառուցվածքով բազային դասեր
- ✔ Ենթադասերը պետք է իրականացնեն բացակայող մասերը
- ✔ Մենք օգտագործում ենք ABC (Abstract Base Class) և abstractmethod

---

### 1. Abstract Class Example (Abstract Class֊ի օրինակ)

```python
from abc import ABC, abstractmethod


class Animal(ABC):
    @abstractmethod
    def sound(self):
        pass  # no implementation
```

---

### 2. Child Classes Must Implement sound() (Child Classes֊ները պետք է իրականացնեն sound()֊ը)

```python
class Dog(Animal):
    def sound(self):
        return "Woof!"


class Cat(Animal):
    def sound(self):
        return "Meow!"
```

Usage (Օգտագործումը):

```python
d = Dog()
print(d.sound())
```

---

### 3. Real Example: Payment System (Իրական օրինակ՝ վճարային համակարգ)

```python
from abc import ABC, abstractmethod


class Payment(ABC):
    @abstractmethod
    def pay(self, amount):
        pass
```

Child(երեխա) classes:

```python
class CardPayment(Payment):
    def pay(self, amount):
        print(f"Paid {amount} with card.")


class CashPayment(Payment):
    def pay(self, amount):
        print(f"Paid {amount} in cash.")
```

---

## Exercise

### 1. Հաշվել շրջանի և  ուղղանկյան մակերեսը

1. Abstract class֊ի հատվածը՝
    - Ստեղծեք abstract class `Shape` (Ձև)
    - Ստեղծել abstract method: `area()` (մակերես)

2. `Circle` class֊ի հատվածը՝
    - Ստեղծել classes `Circle` (Շրջան)
    - Ժառանգիր class `Shape`֊ից
    - Վերցրու և քո ձևով իրականացրու `Shape`֊ի `area()` ֆունկցիան

3. `Rectangle` class֊ի հատվածը՝
    - Ստեղծել classes `Rectangle` (Ուղղանկյուն)
    - Ժառանգիր class `Shape`֊ից
    - Վերցրու և քո ձևով իրականացրու `Shape`֊ի `area()` ֆունկցիան

<details> <summary>💡 Solution</summary>

```python
from abc import ABC, abstractmethod
import math


# 1. Abstract class
class Shape(ABC):
    @abstractmethod
    def area(self):
        pass  # no implementation


# 2. Circle class
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * self.radius ** 2


# 3. Rectangle class
class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height


# Usage examples
c = Circle(5)
print(f"Circle area: {c.area():.2f}")  # Circle area: 78.54

r = Rectangle(4, 6)
print(f"Rectangle area: {r.area()}")  # Rectangle area: 24
```

</details>

## INTERFACE vs ABSTRACT

Մենք կօգտագործենք abc մոդուլը՝ երկու հիմնական կառուցվածք ստեղծելու համար.

### 1. Ինտերֆեյս (CanWork Interface)

Ինտերֆեյսը սահմանում է պարտադիր գործողություններ, բայց բացարձակապես առանց իրականացման (միայն _pass_):

```python
from abc import ABC, abstractmethod


# Ինտերֆեյս: Ցանկացած class, որը ժառանգում է սա, 
# ՊԱՐՏԱԴԻՐ պետք է իրականացնի start_job() և end_job() մեթոդները
class CanWork(ABC):

    @abstractmethod
    def start_job(self):
        """Աշխատանքը սկսելու պարտադիր մեթոդ։"""
        pass

    @abstractmethod
    def end_job(self):
        """Աշխատանքը ավարտելու պարտադիր մեթոդ։"""
        pass
```

### 2. Աբստրակտ Դաս (`Employee` **Abstract Class**)

**Աբստրակտ Դասը** սահմանում է ինչպես պարտադիր (աբստրակտ) մեթոդներ, այնպես էլ կոնկրետ, ընդհանուր իրականացում ունեցող
մեթոդներ։

```python
class Employee(CanWork):  # Ժառանգում է նաև CanWork ինտերֆեյսը

    # Կոնստրուկտոր՝ կոնկրետ դաշտով
    def __init__(self, name, title):
        self.name = name
        self.title = title

    # 🟢 Կոնկրետ մեթոդ (ընդհանուր բոլոր աշխատողների համար)
    def display_info(self):
        print(f"Անուն: {self.name}, Պաշտոն: {self.title}")

    # 🔴 Մնացած մեթոդները ժառանգվել են CanWork-ից և ՊԱՐՏԱԴԻՐ պետք է իրականացվեն
    @abstractmethod
    def calculate_salary(self):
        """Սա պետք է իրականացվի յուրաքանչյուր ենթադասում։"""
        pass
```

> Նշում: Մենք դեռևս չենք իրականացրել `start_job()`, `end_job()` մեթոդները ժառանգված `CanWork`-ից

### 3. Կոնկրետ Ենթադաս (Developer Concrete Class)

Սա այն դասն է, որը կիրականացնի բոլոր բաց թողնված պարտադիր մեթոդները։

```python
class Developer(Employee):

    def __init__(self, name, language):
        super().__init__(name, "Ծրագրավորող")
        self.language = language

    # CanWork Ինտերֆեյսի Պարտադիր Մեթոդները
    def start_job(self):
        print(f"{self.name}: Սկսում է ծածկագիր գրել {self.language}-ով։")

    def end_job(self):
        print(f"{self.name}: Ավարտեց օրվա աշխատանքը։")

    # Employee Աբստրակտ Դասի Պարտադիր Մեթոդը
    def calculate_salary(self):
        return 500000  # Օրինակ


# ----------------- Օգտագործում -----------------

print("### Օգտագործում ###")
dev = Developer("Արմեն", "Python")

# Կանչում ենք կոնկրետ մեթոդը (Employee-ից)
dev.display_info()

# Կանչում ենք ինտերֆեյսի մեթոդները (CanWork-ից)
dev.start_job()
dev.end_job()

# Կանչում ենք աբստրակտ մեթոդը (Employee-ից)
salary = dev.calculate_salary()
print(f"Աշխատավարձը՝ {salary} AMD")

# Փորձում ենք ստեղծել աբստրակտ դասի օբյեկտ (Կձախողվի):
# try:
#     abstract_emp = Employee("Test", "Manager")
# except TypeError as e:
#     print(f"\nՍԽԱԼ: Չենք կարող օբյեկտ ստեղծել աբստրակտ դասից. {e}")
```

1. **Ինտերֆեյս (`CanWork`):** Սա մեր «**Պայմանագիրն**» է։  
   Այն ասում է, որ ցանկացած դաս, որը ցանկանում է լինել «**Աշխատող**», պարտադիր պետք է ունենա `start_job` և `end_job`
   մեթոդները։ Միայն _pass_։

2. **Աբստրակտ Դաս (`Employee`):** Սա «**Կիսա-Պատրաստի**» դաս է։  
   Այն միացնում է _CanWork_-ը (մեթոդները պարտադիր է իրականացնել) և ավելացնում ընդհանուր գործառույթներ (օրինակ՝
   _display_info_):
   Այն նաև ավելացնում է ևս մեկ պարտադիր մեթոդ (_calculate_salary_):

3. **Կոնկրետ Դաս (`Developer`):** Սա «**Վերջնական Ապրանքն**» է։  
   Այն պարտադիր իրականացրել է բոլոր բաց թողնված պարտադիր մեթոդները և ավելացրել իր սեփական մանրամասները (օրինակ՝
   _language_):
   Միայն այս դասից կարող ենք ստեղծել օբյեկտ։

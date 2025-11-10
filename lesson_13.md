<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 📘 Lesson 13: Python Functions

link to presentation:
- https://www.canva.com/design/DAF0pfplY6U/JCUS8Dchy9UVR0HW0yMHfw/edit

### 🎯 Lesson Objective

In this lesson, you will learn:

- What a **function** is and why we use it.
- How to **define** and **call** functions.
- How to use **parameters**, **default** **values**, and **return** statements.
- How to build a **simple calculator project** using functions.

---

## 🔹 1. What Is a Function?

A function is a block of reusable code that runs only when you call it.

### Example 1: Basic Function:

```python
def barevel():
    print("Barev, es Aniin em!")


barevel()
barevel()
```

**🧩 Explanation:**

- `def` is used to define a function.
- The function name is `barevel()`.
- You can call it multiple times.

---

### 🔹 Example 2: Function with Multiple Print Statements

```python
def barevel():
    print("Barev Angela")
    print("Vonc es?")
    print("Lav e che aysorva exanaky?")


barevel()
```

💬 Prints multiple lines when the function is called.

---

### 🔹 Example 3: Function with Parameter

```python
def barevel_parametrov(name):
    print(f"Hello {name}")


barevel_parametrov("Armen")
barevel_parametrov(name="Petros")
```

🧠 You can pass arguments **(values)** to make the function flexible.

---

### 🔹 Example 4: Function with Multiple Parameters

```python
def barevel(anun, tex, tariq):
    print(f"Hello {anun}, es {tariq} tarekan em.")
    print(f"Inchpes ancav {tex}?")


barevel("Armen", "London", "18")
barevel(tex="London", anun="Angela", tariq="15")
```

💡 You can also call the function using **keyword arguments**.

---

### 🔹 Example 5: Example: Youngest Child

```python
def my_function(child2, child1):
    print("The youngest child is " + child2)


my_function(child1="Emma", child2="Hamlet")
```

---

### 🔹 Example 6: Function that Calculates Area

```python
def makeres_calculator(erkarutyun, laynutyun):
    makeres = erkarutyun * laynutyun
    print(f"Pati makeresn e {makeres}")


makeres_calculator(6, 3)
makeres_calculator(8, 5)
```

📏 **Calculates area** using length × width.

---

### 🔹 Example 7: Default Parameter Value

```python
def my_function(country="Armenia"):
    print("I am from " + country)


my_function("Sweden")
my_function("India")
my_function()
my_function("Russia")
```

💡 If you don’t provide a value, the default `Armenia` is used.

---

### 🔹 Example 8: Function That Loops Over Elements

```python
def my_function(a):
    for x in a:
        print(x)


fruits = ['apple', 'banana', 'cherry']
numbers = [1, 2, 3, 4]
word = "Hello"

my_function(fruits)
my_function(numbers)
my_function(word)

```

📘 Works with **lists, strings, or any iterable.**

---

### 🔹 Example 9: Function That Sums Even Numbers

```python
def zuyger_tveri(a, b):
    gumar = 0
    for i in range(a, b):
        if i % 2 == 0:
            gumar += i
    print(gumar)


tiv1 = int(input("Mutqagrel skzbnakan tiv: "))
y = int(input("Mutqagrel verjnakan tiv: "))
zuyger_tveri(tiv1, y)
```

🧮 Adds all even numbers in the given range.

---

### 🔹 Example 10: Function That Returns a Value

```python
def gumarum(x, y):
    return x + y


result = gumarum(3, 5)
print("Gumary =", result)
```

💡 `return` sends the result back to the caller.

---

### 🔹 Example 11: 🧮 Mini Project – Calculator

```python
def gumarum(x, y):
    return x + y


def hanum(x, y):
    return x - y


def multiply(x, y):
    return x * y


def divide(x, y):
    return x / y


print("Yntrel gortsoxutyun:")
print("1. Gumarel")
print("2. Hanum")
print("3. Bazmapatkel")
print("4. Bajanel")

while True:
    choice = input("Yntrir tarberak (1/2/3/4): ")

    if choice in ['1', '2', '3', '4']:
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))

        if choice == '1':
            print("Aresult =", gumarum(num1, num2))
        elif choice == '2':
            print("Aresult =", hanum(num1, num2))
        elif choice == '3':
            print("Aresult =", multiply(num1, num2))
        elif choice == '4':
            print("Aresult =", divide(num1, num2))

        next_calculation = input("Do another? (yes/no): ")
        if next_calculation.lower() == "no":
            break
    else:
        print("Invalid input! Try again.")

```

🧠 This calculator:

- Uses **functions for each operation**
- Uses **while True** to repeat
- Ends when user types `no`

---

# 🧩 Exercises

### Exercise 1:

Ստեղծեք ֆունկցիա, որը վերցնում է անուն և տարիք և print է անում՝

> “Hello Anna, you are 25 years old.”

---

### Exercise 2:

Գրել ֆունկցիա, որը ընդունում է թիվ և վերադարձնում է՝ զույգ է, թե կենտ։

```python
# Օրինակ
print(even_or_odd(10))  # ➜ Even
print(even_or_odd(7))  # ➜ Odd
```

---

### Exercise 4:

Գրել ֆունկցիա, որը ստանում է թվերի ցուցակ և վերադարձնում է դրանց միջին արժեքը։

```python
# Օրինակ
nums = [10, 20, 30, 40]
print(average(nums))  # ➜ 25.0
```

---

### Exercise 5 (Challenge):

Փոփոխեք հաշվիչի կոդը՝

- ավելացնել աստիճան բարձրացում
- եթե փորձում ես բաժանել 0-ի վրա, կստանաս `"Cannot divide by zero"` հաղորդագրություն։

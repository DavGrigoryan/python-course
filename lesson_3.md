<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 3 – Operators, Math & Conditions

link to presentation: https://www.canva.com/design/DAGzfnvdL4E/a9UXh243QdJjmu3PdsScNw/edit

---

**🔹 1. Arithmetic Operators**

In Python we can do math with operators:

```python
print(3 + 5)  # Addition → 8
print(7 - 4)  # Subtraction → 3
print(8 / 4)  # Division → 2.0
print(6 // 3)  # Floor division → 2 (no decimal part)
```

Check types:
```python
print(type(8 / 4))   # <class 'float'>
print(type(8 // 4))  # <class 'int'>
```

**🔹 2. Order of Operations (PEMDAS rule)**

1. Python follows the order:
2. Parentheses `()`
3. Exponents `**`
4. Multiplication / Division
5. Addition / Subtraction

```python
print(3 / 3 + 3 * 3 - 3)     # → 7.0
print(3 * (3 + 3) / 3 - 3)   # → 3.0
```

**🔹 3. Modulo, Floor Division, Power**

```python
x = 8
y = 2
print(x % y)   # Remainder → 0

x = 10
y = 3
print(x // y)  # Floor division → 3

x = 2
y = 5
print(x ** y)  # Power → 32

x = 4
y = 0.5
print(x ** y)  # Square root → 2.0
```

**🔹 4. BMI Calculator (Body Mass Index)**

Formula:
> $BMI = \frac{weight}{height^2}$

```python
height = float(input("Enter your height (m): "))
weight = float(input("Enter your weight (kg): "))

bmi = weight / height ** 2
print("Your BMI is:", int(bmi))
```

**🔹 5. Shortcuts with Variables**

```python
balance = 100
balance += 50   # add 50
balance -= 20   # subtract 20
print(balance)  # → 130
```

```python
balance = 100
deposit = int(input("Enter deposit amount: "))
balance += deposit
print("New balance:", balance)
```

**🔹 6. Rounding Numbers**
```python
print(int(8 / 7))            # → 1
print(round(8 / 3))          # → 3
print(round(8 / 3, 2))       # → 2.67
print(round(2.66664456664, 3)) # → 2.667
```

**🔹 7. String Multiplication**

```python
print(4 * "py" + "thon")     # → pypypypython
print(4 * ("py" + "thon"))   # → python python python python
```

❌ Examples that give errors:
```python
# print(5/"py"+"t"-"on")   # TypeError
# print(5 - "barev")        # TypeError
```

**🔹 8. Comparison Operators (Boolean)**

```python
x = 5
y = 15

print(x > y)   # False
print(x < y)   # True
print(x <= y)  # True
print(x >= y)  # False
print(x == y)  # False
print(x != y)  # True
```

















# Exercise

## 🧩 Simple Calculator

1. Ask the user to enter two numbers.
2. Print their sum, difference, product, and quotient.

Example Run:

```yaml
Enter first number: 8
Enter second number: 2

Sum: 10
Difference: 6
Product: 16
Quotient: 4.0
```

<details> <summary>💡 Solution</summary>

```python
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))

print("Sum:", num1 + num2)
print("Difference:", num1 - num2)
print("Product:", num1 * num2)
print("Quotient:", num1 / num2)
```

</details>

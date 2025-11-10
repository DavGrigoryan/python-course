<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 📘 Lesson 16: Python Recursion Functions

link to presentation:

---

## Basic Recursion

```python
def say_hello():
    print("Hello!")
    say_hello()  # Function calls itself


say_hello()
```

## Safe Recursion with Base Case

```python
def countdown(n):
    if n == 0:
        print("Boom!")
    else:
        print(n)
        countdown(n - 1)


countdown(5)
```

## Factorial Example

```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)


print(factorial(5))  # Output: 120
```

## 🧠 How it works:

```text
factorial(5)
= 5 × factorial(4)
= 5 × 4 × factorial(3)
= 5 × 4 × 3 × factorial(2)
= 5 × 4 × 3 × 2 × factorial(1)
= 5 × 4 × 3 × 2 × 1 = 120
```

# Exercises

## Exercise 1:

Write a recursive function that prints numbers from 1 to n.

## Exercise 2:

Write a recursive function that sums all numbers from 1 to n.

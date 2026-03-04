<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 6: Conditions (If/else/elif hard)

link to presentation: https://www.canva.com/design/DAFyrEmUXpo/rCfS6clhqytxH3aikO-xWg/edit

---

**🔹 And**

```python
a = 200
b = 33
c = 500
if a > b and c > a:
    print("Both conditions are True")
```

**🔹 Or**

```python
a = 200
b = 33
c = 500
if a > b or a > c:
    print("At least one of the conditions is True")
```

**🔹 Not**

```python
a = 33
b = 200
if not a > b:
    print("a is NOT greater than b")
```

**🔹 Nested If**

```python
x = 41

if x > 10:
    print("Above ten,")
    if x > 20:
        print("and also above 20!")
    else:
        print("but not above 20.")
```

**🔹 The pass Statement**

```python
a = 33
b = 200

if b > a:
    pass
```

---

**🔹 Short Hand If**

```python
if a > b: print("a is greater than b")
```

**🔹 Short Hand If ... Else**

```python
a = 2
b = 330
print("A") if a > b else print("B")
```

```python
a = 330
b = 330
print("A") if a > b else print("=") if a == b else print("B")
```

---

# Exercise

**1. Discount Calculator 🛒**  
Հարցրու գնման գումար։

Եթե < 50 → “No discount”  
Եթե 50–100 → 10% զեղչ  
Եթե > 100 → 20% զեղչ 

**2. Speed Check 🚗**  
Հարցրու արագություն։  
Եթե ≤ 60 → “Safe”,  
եթե 61–120 → “Warning”,  
եթե > 120 → “Overspeeding!”։

**3. Day of Week 🗓️**  
Հարցրու օր (1–7)։  
Տպիր շաբաթվա օրը (1 → Երկուշաբթի … 7 → Կիրակի)։
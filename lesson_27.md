<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 27 — Args, Kwargs & Lambda Functions

---

### ✳️ What Is `*args`?

`*args`–ը թույլ է տալիս, որ ձեր ֆունկցիան ընդունի կամայական թվով դիրքային արգումենտներ։

Example:

```python
def show_numbers(*args):
    print(args)


show_numbers(1, 2, 3, 4)
```

Output:

```text
(1, 2, 3, 4)
```

Ինչու՞ օգտագործել `*args`–ը

- Դուք չգիտեք, թե քանի՞ արժեք կփոխանցի օգտատերը
- Ճկուն է (Flexible)
- Իրեն պահում է որպես `tuple`

---

### ✳️ What Is `**kwargs`?

`**kwargs`–ը թույլ է տալիս, որ ձեր ֆունկցիան ընդունի կամայական թվով key-value (կամ՝ անվանական) արգումենտներ։

Example:

```python
def show_data(**kwargs):
    print(kwargs)


show_data(name="Anna", age=22)
```

```text
{'name': 'Anna', 'age': 22}
```

Ինչու՞ օգտագործել `**kwargs`–ը:

- Դուք չգիտեք, թե որ անվանական (named) արգումենտներն եք ստանալու։
- Օգտակար է ըստ ցանկության (optional) տվյալների համար։
- Իրեն պահում է որպես `dictionary`։

---

### ✳️ Lambda Functions

`Lambda` ֆունկցիան փոքր, մեկ տողից բաղկացած և առանց անունի ֆունկցիա է։

Syntax:

```python
lambda arguments: expression
```

**Examples:**

Add 10:

```python
add_ten = lambda x: x + 10
print(add_ten(5))  
```

Multiply:

```python
multiply = lambda a, b: a * b
print(multiply(2, 5))
```

---

### ✳️ Lambdas + Loops Example

```python
double = lambda x: x * 2
for i in range(1, 6):
    print(double(i))
```

---

### ✳️ Lambda inside a Dictionary

```python
operations = {
    "add": lambda x, y: x + y,
    "multiply": lambda x, y: x * y,
    "subtract": lambda x, y: x - y
}

print(operations["add"](10, 5))
```

---

### ✳️ Lambda + Conditions Example

```python
check_equal = lambda t: t[0] == t[1]

tuples = [(1, 1), (3, 4), (5, 5)]
for pair in tuples:
    print(check_equal(pair))
```

---

# Exercises

### ✳️ Exercise 1 — Sum all numbers

Գրեք ֆունկցիա՝ օգտագործելով `*args`, որը վերադարձնում է բոլոր փոխանցված թվերի գումարը

<details> <summary>💡 Solution</summary>

```python
def sum_all(*args):
    return sum(args)


print(sum_all(1, 2, 3, 4))  # 10
```

</details>


---

### ✳️ Exercise 2 — Print all keyword info

Ստեղծեք `show_info(**kwargs)` ֆունկցիա, որը տպում է բոլոր key-value զույգերը

<details> <summary>💡 Solution</summary>

```python
def show_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value")

show_info(name="Ani", age=20, city="Yerevan")
```

</details>

---

### ✳️ Exercise 3 — Double numbers (lambda)

Օգտագործե՛ք լամբդա ֆունկցիա (lambda)՝ թիվը կրկնապատկելու համար՝

```python
double = lambda x: ?
```

Փոխե՛ք `«?»` նշանը՝ արդյունքը ստանալու համար։  
Կանչե՛ք այն ցանկացած թվով։

<details> <summary>💡 Solution</summary>

```python
double = lambda x: x * 2
print(double(5))  # 10
```

</details>

---

### ✳️ Exercise 4 — First letter extractor

Օգտագործե՛ք `List Comprehension`֊ը և `lambda` ֆունկցիա՝ բառերի ցանկից առաջին տառերը կորզելու (ստանալու) համար։

Input:  
`["Apple", "Banana", "Kiwi"]`  
Output:  
`["A", "B", "K"]`

<details> <summary>💡 Solution</summary>

```python
words = ["Apple", "Banana", "Kiwi"]

get_first = lambda w: w[0]
first_letters = [get_first(w) for w in words]

print(first_letters)
```

</details>


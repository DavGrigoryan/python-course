<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 22: Scope & Global Functions

### ✳️ What is “Scope”?

Scope defines where a variable can be accessed in your code.
There are 4 main scopes in Python:

| 🧩 Scope Type | 📝 Description                                                                           | 💡 Example                |
|:--------------|:-----------------------------------------------------------------------------------------|:--------------------------|
| **Local**     | Variable defined **inside a function** — only accessible within that function.           | Inside a function         |
| **Enclosing** | Variable in an **outer function**, accessible to an **inner function** using `nonlocal`. | Nested functions          |
| **Global**    | Variable defined **outside all functions**, accessible anywhere in the same file.        | Top-level variable        |
| **Built-in**  | Predefined names provided by Python (e.g. `print()`, `len()`, `sum()`).                  | Python keywords/functions |

---

### ✳️ Example 1 — Local vs Global Scope

```python
enemies = 1


def increase_enemies():
    enemies = 2  # Local variable
    print(f"Inside function: {enemies}")


increase_enemies()
print(f"Outside function: {enemies}")
```

---

### ✳️ Example 2 — Local Variables

```python
def drink_potion():
    potion_strength = 2
    print("Inside function:", potion_strength)


potion_strength = 3
drink_potion()
print("Outside function:", potion_strength)
```

---

### ✳️ Example 3 — Using Global Variables Inside Functions

```python
player_health = 10


def game():
    print("Inside game:", player_health)


game()
print("Outside game:", player_health)
```

---

### ✳️ Example 4 — Modifying a Global Variable

To modify a global variable inside a function, use the `global` keyword.

```python
counter = 10


def increase():
    global counter
    counter += 5
    print("Inside function:", counter)


increase()
print("Outside function:", counter)
```

---

### ✳️ Example 5 — Global Constants

By convention, constants are written in **UPPERCASE**:

```python
PI = 3.14159
URL = "https://www.google.com"
TWITTER = "@python"
```

These values should not be changed in your program.

---

### ✳️ Example 6 — Global and Local Interaction in Recursion

```python
x = 0


def recursive_function(n):
    global x
    if n > 0:
        n -= 1
        x += 1
        print(f"Local n={n}, Global x={x}")
        recursive_function(n)


recursive_function(5)
print("Final global x:", x)
```

---

### ✳️ Example 7 — Using `nonlocal` Inside Nested Functions

```python
def outer():
    y = 10

    def inner():
        nonlocal y
        y += 5
        print("Inner value:", y)

    inner()
    print("Outer value:", y)


outer()
```

---

### ✳️ Example 8 — Accessing and Modifying Global Variables Dynamically

```python
x = 10
y = 20


def modify_globals():
    globals()['x'] = 100
    globals()['y'] = 200


modify_globals()
print(x, y)  # 100 200
```

---

### ✳️ Example 9 — Local Variables Dictionary

You can inspect local variables using `locals()`:

```python
def func():
    a = 1
    b = 2
    print(locals())


func()
# Output: {'a': 1, 'b': 2}
```

---

# Exercises

### 🧩 Ex. 1 — Ֆունկցիա՝ գլոբալ հաշվիչը հետևելու համար

Գրիր ֆունկցիա `call_counter()` անունով, որը կկանչվի մի քանի անգամ
և յուրաքանչյուր կանչի ժամանակ օգտվելու է մեկ `global` փոփոխականից՝ հաշվելու, թե function-ը քանի անգամ է կանչվել։

- Ստեղծիր գլոբալ փոփոխական՝ count = 0 սկզբում։
- Ֆունկցիայի ներսում օգտվիր global count և ամեն կանչի ժամանակ ավելացրու count-ը մեկով։
- Ֆունկցիան պետք է տպի հաղորդագրություն՝ ինչքան անգամ է կանչվել, օրինակ՝ "Function called 3 times".

<details> <summary>💡 Solution</summary>

```python
count = 0  # global variable


def call_counter():
    global count
    count += 1
    print(f"Function called {count} times")


call_counter()
call_counter()
call_counter()
```

</details>

### 🧩 Ex. 2 — Ֆունկցիաներ (nested) և nonlocal

Գրիր ֆունկցիա `outer()` և նրա ներսում ստեղծիր nested ֆունկցիա `inner()`

- `outer()`-ի մեջ ստեղծիր փոփոխական `value = 0`.
- `inner()`-ը պետք է օգտագործի `nonlocal value`, ավելացնի `value`-ին մի թիվ (օր. `+5`) և տպի վերջին արժեքը։
- `outer()`-ից կանչիր `inner()`֊ը մի քանի անգամ և `inner`-ի մեջ տպիր փոփոխվողի արժեքը։

<details> <summary>💡 Solution</summary>

```python
def outer():
    value = 0

    def inner():
        nonlocal value
        value += 5
        print("Value inside inner:", value)

    inner()
    inner()


outer()
```

</details>

---

### 🧩 Ex. 3 — Ռեկուրսիվ ֆունկցիա՝ countdown + գլոբալ հաշվիչ

Պետք է անել (հարցման/փաստարկ):
Գրիր ռեկուրսիվ ֆունկցիա countdown(n),
որը ընդունում է ամբողջ թիվ n և հաշվարկում է ժամանակավոր գործողություններ՝ մինչև հասնի 0։  
Միաժամանակ պետք է օգտագործվի գլոբալ հաշվիչ counter,
որը կթվարկի, թե function-ը քանի անգամ է կոչվել (բոլոր ռեկուրսիվ կանչերը հաշվում են)։

- Global֊ում սարքիր counter = 0.
- Ֆունկցիայի սկզբում երբ n > 0, բարձրացրու counter-ը և տպիր "Counting down: n" (իր արժեքով), հետո կանչիր countdown(n-1)
- Երբ n == 0, այդ ժամանակ ռեկուրսիան պետք է կանգնացնել, տպեք՝ "Done!" հետո `return` արեք ուղակի կոդը կանգնացնելու համար

<details> <summary>💡 Solution</summary>

```python
counter = 0


def countdown(n):
    global counter
    if n == 0:
        print("Done!")
        return
    counter += 1
    print(f"Counting down: {n}")
    countdown(n - 1)


countdown(5)
print("Global counter =", counter)
```

</details>

---

### 🧩 Ex. 4 — Միավորում (merge) երկու dictionary՝ նույն բանալիների արժեքները գումարելով

Գրիր ֆունկցիա `merge_dicts(d1, d2)`, որը ընդունում է երկու dictionary՝ **d1** և **d2**։   
Ֆունկցիան պետք է վերադարձնի նոր dictionary, որտեղ՝

- Եթե բանալին կա միայն d1-ում կամ միայն d2-ում, այն տեղադրված կլինի նույն արժեքով։
- Եթե բանալին գոյություն ունի երկուսում էլ, ապա դրա արժեքները պետք է գումարվեն (ընդհանուր արժեք = d1[key] + d2[key])։
  Օրինակ՝
- d1 = `{'a': 10, 'b': 20}`
- d2 = `{'b': 5, 'c': 15}`
- Արդյունք՝ `{'a': 10, 'b': 25, 'c': 15}`

---

### 🧩 Ex. 5 — Տպել տեղային (local) փոփոխականները locals()-ով

Գրիր ֆունկցիա `show_locals()` որը ֆունկցիայի ներսում կհայտարարի մի քանի local փոփոխականներ  
(օր. `x = 10`, `y = 20`, `z = x + y`) և հետո կօգտագործի `locals()`՝ այդ local փոփոխականները տպելու կամ ցուցադրելու
համար։

---

### 🧩 Ex. 6 — Տպել տեղային (global) փոփոխականները globals()-ով

Գրիր ֆունկցիա `show_globals()` որը global հայտարարված մի քանի փոփոխականներ կտպի
(օր. `x = 10`, `y = 20`, `z = x + y`) և հետո կօգտագործի `globals()`՝ այդ global փոփոխականները տպելու կամ ցուցադրելու
համար։

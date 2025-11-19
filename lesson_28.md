<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 28 – Error Handling in Python

Սխալների մշակման շնորհիվ ձեր ծրագիրը շարունակում է աշխատել նույնիսկ անսարքությունների դեպքում։  
**Exception**-ները թույլ են տալիս մշակել սխալները։

- **try** : Բլոկը ստուգում է սխալների առկայությունը, իսկ except-ը մշակում է սխալները, եթե դրանք առաջանան։
- **finally** : Միշտ կատարվում է try-except-ից հետո՝ անկախ սխալների առկայությունից՝ ապահովելով մաքրումը։
- **else** : Կատարվում է միայն այն դեպքում, երբ try-ն ավարտվում է առանց սխալի։
- **raise** : Օգտագործվում է նոր սխալ ստեղծելու համար՝ թույլ տալով սահմանել սխալներ առաջացնելու պայմաններ։

---

### ✳️ Basic Try–Except

```python
try:
    print(6 / 0)
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

---

### ✳️ Loop Until Correct Input

```python
while True:
    try:
        number = int(input("Enter a number: "))
        break
    except ValueError:
        print("Please enter only numbers!")
```

---

### ✳️ Handling Index Errors

```python
my_list = [1, 2, 3, 4]

try:
    print(my_list[12])
except IndexError:
    print("Index 12 does not exist!")
```

---

### ✳️ Try–Except–Else

```python
try:
    print("Hello")
except:
    print("Something went wrong")
else:
    print("Everything worked fine!")
```

---

### ✳️ Try–Except–Finally

```python
try:
    print(x)  # x is not defined
except:
    print("Something went wrong!")
finally:
    print("The try-except block is finished.")
```

---

### ❗ Raising Errors Manually

```python
age = int(input("Enter your age: "))
if age < 0:
    raise ValueError("Age cannot be negative!")
```

---

### ❗ Custom Exceptions

```python
class MyCustomError(Exception):
    pass


def check_username(name):
    if name == "":
        raise MyCustomError("Username cannot be empty!")


check_username("")  # Raises MyCustomError
```

---

### ❗ TypeError Example

```python
x = "hello"

if isinstance(x, str):
    raise TypeError("Only integers are allowed!")
```

---

### ❗ Password Validator

```python
def check_password(pw):
    if len(pw) < 8:
        raise ValueError("Password too short!")
    if pw.isalpha() or pw.isdigit():
        raise ValueError("Password must contain letters AND numbers.")
    return "Password accepted!"


try:
    pw = input("Enter password: ")
    print(check_password(pw))
except ValueError as e:
    print("Invalid password:", e)
finally:
    print("Password check complete.")
```

---

### ❗ TypeError Example (String + Int)

```python
try:
    print('a' + 8)
except TypeError:
    print("Type error: You cannot add a string and a number!")
```

---

### 🔄 Random Error Simulation

```python
import random


def risky_divide():
    x = random.choice([2, 10, 0, 5, "b"])
    y = random.choice([5, 10, 0, 7, "a"])

    print(f"Trying to divide {x} by {y}...")

    try:
        result = int(x) / int(y)
    except ZeroDivisionError:
        print("Cannot divide by zero!")
    except ValueError:
        print("One of the values is not a number!")
    except Exception as e:
        print("Unknown error:", e)
    else:
        print("Result:", result)
    finally:
        print("Finished attempt.\n")


for _ in range(5):
    risky_divide()
```

----

## Exercises

### 1. Safe Division (Անվտանգ բաժանում)

- Գրել ծրագիր, որը օգտատերից կընդունի 2 թիվ և կբաժանի մեկը մյուսին։
- Եթե օգտատերը գրի տեքստ կամ փորձի բաժանել զրոյի, պետք է մշակել սխալը։
- Օգտագործելով՝ `ZeroDivisionError` և `ValueError`

---

### 2. List Index Checker (Ցուցակի ինդեքսի ստուգում)

Տրված է ցուցակ `[10, 20, 30]`։ Փորձել տպել այն ինդեքսով, որը գոյություն չունի։  
Մշակել IndexError։ `"Index out of range!"`

---

### 3. Integer Input Loop  (Մինչև ճիշտ թիվ չմուտքագրի)

- Գրել ծրագիր, որը օգտատերից կհարցնի թիվ։
- Շարունակել հարցնել թիվ, մինչև օգտատերը ճիշտ թիվ մուտքագրի։

---

### 4. Convert to Number (Թիվը դարձնել ֆունկցիա)

- Գրել ֆունկցիա, որը փորձում է արժեքը դարձնել int։
- Եթե չի ստացվում, վերադարձնել `"Invalid number"`։

### 5. Key in Dictionary (Բառարանի բանալի)

- Փորձել dictionary-ում գոյություն չունեցող բանալի վերցնել։ Մշակել KeyError։

---

### 6. Custom Error: Negative Age (Բացասական տարիքի սխալ)

Գրել ֆունկցիա, որը բացասական տարիքի դեպքում բացում է `ValueError`։

---

### 7. Even Number Checker (Զույգ թվի ստուգում)

Գրել ֆունկցիա, որը ստուգում է՝ թիվը զույգ է, թե ոչ։  
Եթե ոչ՝ բացել `ValueError`։

---

### 8. Password Validator (Գաղտնաբառի ստուգում)

Պետք է ստուգել, որ գաղտնաբառը՝

- առնվազն 8 սիմվոլ լինի
- պարունակի և տառեր, և թվեր

---

### 9. Random Risky Division (Պատահական վտանգավոր բաժանում)

- Ունենք երկու `list`՝ `[0, 2, 5, "a"]` և `[0, 10, "b", 3]`
- Պատահական վերցնել թվեր/տեքստեր և կատարել բաժանում։
- Մշակել տարբեր սխալներ։

---

### 10. Mini Calculator with Error Handling (Մինի հաշվիչ սխալների մշակավորմամբ)

Ստեղծել հաշվիչ, որը

- ընդունում է 2 թիվ
- ընդունում է գործողություն `(+ - * /)`
- մշակում է սխալները
- `finally`-ում տպում է `"Completed"`

<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 25 — Modules

### What is a module?

Մոդուլը այն ֆայլն է, որը պարունակում է Python կոդ (ֆունկցիաներ, կլասներ, փոփոխականներ), որոնք կարելի է վերօգտագործել։  
Python-ի ստանդարտ գրադարանը ունի բազմաթիվ ներկառուցված մոդուլներ (math, random, time, datetime, os, calendar և այլն)։  
Դուք նաև կարող եք ստեղծել ձեր սեփական մոդուլը (․py ֆայլ) և այն ներմուծել (import անել)։

---

### ✳️ Import styles (examples)

```python
import math  # import the module
import math as m  # alias the module
from math import pi, sqrt  # import specific names
from math import *  # NOT recommended (pollutes namespace)
```

#### Why alias?

import random as rnd shortens names and avoids conflicts.

---

### ✳️ Quick examples of common modules

#### math

```python
import math

print(math.pi)  # 3.14159...
print(math.sqrt(16))  # 4.0
# example: circumference
x = float(input("radius: "))
print(2 * math.pi * x)
```

#### random

```python
import random

print(random.random())  # float 0.0-1.0
print(random.randint(1, 6))  # integer 1-6
print(random.choice("abcde"))  # random character
```

#### time

```python
import time

print("Hello")
time.sleep(2)  # wait 2 seconds
print("World")

start = time.time()  # seconds since epoch
# ... some work ...
end = time.time()
print("Elapsed:", end - start)
```

#### datetime

```python
import datetime

now = datetime.datetime.now()
print(now)  # current date/time
print(now.strftime("%Y-%m-%d"))  # formatted
birthday = datetime.datetime(2000, 4, 15)
print(birthday)
# add days:
future = now + datetime.timedelta(days=10)
print(future)
```

#### calendar

```python
import calendar

print(calendar.month(2025, 5))
print(calendar.isleap(2024))  # True if leap year
print(calendar.leapdays(2000, 2026))
```

#### os

```python
import os

print(os.getcwd())  # current working directory
# list files:
print(os.listdir('.'))
# make dir:
# os.mkdir('test_dir')
```

### ✳️ Good practices with imports

- Նախընտրելի է օգտագործել `import module` կամ `import module as alias`։
- Խուսափեք `from module import *`-ից։
- `import`֊ները գրեք ֆայլի սկզբում (վերևում)։
- Օգտագործեք **կոնկրետ իմպորտներ** ընթեռնելիության համար. օրինակ՝ `from math import pi, sqrt`, երբ Ձեզ անհրաժեշտ են
  միայն մի քանի անուններ։

---

### ✳️ Small practical app: Books manager

Պարզ կոնսոլային հավելված, որն օգտագործում է հիմնական IO և dictionary (լրացուցիչ մոդուլներ անհրաժեշտ չեն, բայց ցուցադրում
է մոդուլի համար պատրաստ կառուցվածք)։

```python
# books_manager.py

books = {}  # title -> bool (read)


def add_book():
    title = input("Enter book title: ").strip()
    if title in books:
        print(f"'{title}' already in list.")
    else:
        books[title] = False
        print(f"Added '{title}'")


def mark_as_read():
    if not books:
        print("No books yet.")
        return
    title = input("Title you read: ").strip()
    if title in books:
        books[title] = True
        print(f"Marked '{title}' as read.")
    else:
        print("Not found.")


def view_books():
    if not books:
        print("No books yet.")
        return
    for idx, (title, read) in enumerate(books.items(), 1):
        status = "Read" if read else "Unread"
        print(f"{idx}. {title} - {status}")


def delete_book():
    if not books:
        print("No books yet.")
        return
    title = input("Title to delete: ").strip()
    if title in books:
        del books[title]
        print(f"Deleted '{title}'")
    else:
        print("Not found.")


def show_menu():
    print("""
1. Add book
2. Mark as read
3. View books
4. Delete book
5. Exit
""")


def main():
    while True:
        show_menu()
        choice = input("Choose (1-5): ").strip()
        if choice == "1":
            add_book()
        elif choice == "2":
            mark_as_read()
        elif choice == "3":
            view_books()
        elif choice == "4":
            delete_book()
        elif choice == "5":
            print("Bye!")
            break
        else:
            print("Invalid choice.")


if __name__ == "__main__":
    main()
```

---

## ✳️ Mini exercises (Փոքր վարժություններ)

### Exercise 1 — random_password()

Գրիր `random_password(n)` անունով ֆունկցիա, որը կվերադարձնի պատահական (random) գաղտնաբառ՝ բաղկացած տառերից և թվերից, որի
երկարությունը կլինի `n`։

📘 Օրինակ՝  
եթե կանչենք random_password(8)  
կարող է վերադարձնել՝ "a9xT2dQp" կամ "P1z8Lm0k"։

👉 Այսինքն՝ յուրաքանչյուր անգամ տարբեր արդյունք։

<details> <summary>💡 Solution</summary>

```python
import random
import string


def random_password(n):
    chars = string.ascii_letters + string.digits
    return ''.join(random.choice(chars) for _ in range(n))


print(random_password(8))
```

</details>

---

### Exercise 2 — days_between(date1, date2)

Գրիր ֆունկցիա, որը կստանա երկու ամսաթվեր `"YYYY-MM-DD"` ձևաչափով (օրինակ `"2025-11-09"`)  
և կվերադարձնի՝ **որքան օր է տարբերությունը այդ երկու ամսաթվերի միջև։**

📘 Օրինակ՝
`days_between("2025-11-01", "2025-11-09")` → պետք է վերադարձնի `8`

<details> <summary>💡 Solution</summary>

```python
import datetime


def days_between(d1, d2):
    fmt = "%Y-%m-%d"
    dt1 = datetime.datetime.strptime(d1, fmt)
    dt2 = datetime.datetime.strptime(d2, fmt)
    return abs((dt2 - dt1).days)


print(days_between("2025-05-01", "2025-05-17"))  # 16
```

</details>

---

### Exercise 3 — List files modified in last N seconds (Վերջին N վայրկյանում փոփոխված ֆայլեր)

Գրիր ծրագիր, որը կօգտագործի os և time մոդուլները  
և կտպի ներկա թղթապանակի (current directory) բոլոր այն ֆայլերի անունները,  
որոնք փոփոխվել են վերջին N վայրկյանների ընթացքում։

📘 Օրինակ՝  
Եթե կանչես ծրագիրը՝ և N = 60  
ապա այն պետք է ցույց տա բոլոր ֆայլերը, որոնք փոփոխվել են վերջին մեկ րոպեի ընթացքում։

<details> <summary>💡 Solution</summary>

```python
import os, time


def recent_files(seconds=60):
    now = time.time()
    for name in os.listdir('.'):
        try:
            m = os.path.getmtime(name)
            if now - m <= seconds:
                print(name)
        except FileNotFoundError:
            pass


recent_files(3600)  # last hour
```

</details>

---

### Exercise Bonus: Create & import your own module (Ստեղծիր և ներմուծիր սեփական մոդուլը)

1. Ստեղծիր նոր ֆայլ՝ utils.py անունով։
2. Ներսում գրիր ֆունկցիա՝

    ```python
    # utils.py
    def greet(name):
        return f"Hello, {name}!"
    ```

3. Հիմա բացիր մեկ այլ Python ֆայլ (օր.՝ main.py)
4. Ներսում փորձիր ներմուծել վերևում գրված `"greet"` ֆունկցիան այսպես՝

    ```python
    from utils import greet
    
    print(greet("Anna"))
    ```

---







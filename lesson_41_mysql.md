<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 41 – Python MySQL WHERE & Filtering

---

## 📌 Ի՞նչ է WHERE Clause

**WHERE**-ը օգտագործվում է table-ից կոնկրետ տվյալներ ընտրելու համար։

Այսինքն մենք filter ենք անում տվյալները։

Օրինակ table

| id | name  | age |
|----|-------|-----|
| 1  | Anna  | 21  |
| 2  | John  | 17  |
| 3  | Emma  | 20  |
| 4  | Dawud | 30  |

Եթե ուզում ենք վերցնել միայն age > 21։

---

### 📌 WHERE Syntax

```mysql
SELECT *
FROM table_name
WHERE condition;
```

---

### 📌 Python Example

```python
import mysql.connector

connection = mysql.connector.connect(
    host="localhost",
    database="school",
    user="root",
    password="your_password"
)

cursor = connection.cursor()

cursor.execute("SELECT * FROM students WHERE age > 21")

for student in cursor.fetchall():
    print(student)

cursor.close()
connection.close()
```

---

## 📌 AND Operator

AND-ը օգտագործվում է մի քանի պայման միացնելու համար։

Երկու պայմանները պետք է ճիշտ լինեն։

### Example

```mysql
SELECT *
FROM students
WHERE age > 20 AND name = 'Anna';
```

---

### Python Example

```python
cursor.execute(
    "SELECT * FROM students WHERE age > %s AND name = %s",
    (20, "Anna")
)

for row in cursor.fetchall():
    print(row)
```

---

## 📌 OR Operator

OR-ը նշանակում է **պայմաններից մեկը բավարար է**

---

### Example

```mysql
SELECT *
FROM students
WHERE age = 20 OR age = 25;
```

---

### Python Example

```python
cursor.execute(
    "SELECT * FROM students WHERE age = %s OR age = %s",
    (20, 25)
)

for row in cursor.fetchall():
    print(row)
```

---

## 📌 NOT Operator

**NOT**-ը օգտագործվում է պայմանը հակառակ դարձնելու համար։

---

### Example

```mysql
SELECT *
FROM students
WHERE NOT age = 21;
```

---

### Python Example

```python
cursor.execute(
    "SELECT * FROM students WHERE NOT age = %s",
    (21,)
)

for row in cursor.fetchall():
    print(row)
```

---

## 📌 NULL Values

**NULL** նշանակում է **դատարկ արժեք**։

**NULL**-ը համեմատվում է միայն **IS NULL** կամ **IS NOT NULL**։

---

### Example

```mysql
SELECT *
FROM students
WHERE age IS NULL;
```

---

### Python Example

```python
cursor.execute("SELECT * FROM students WHERE age IS NULL")

for row in cursor.fetchall():
    print(row)
```

---

## 📌 LIKE Operator

**LIKE**-ը օգտագործվում է տեքստ որոնելու համար։

Այսինքն մենք կարող ենք գտնել տվյալներ՝

- **որոնք սկսվում են ինչ-որ տառով**
- **որոնք ավարտվում են ինչ-որ տառով**
- **որոնք պարունակում են ինչ-որ բառ**
- **որոնք ունեն որոշակի երկարություն**

LIKE operator-ը հիմնականում օգտագործվում է VARCHAR կամ TEXT սյունակների համար։

---

### 📌 LIKE Syntax

```mysql
SELECT column1, column2
FROM table_name
WHERE column_name LIKE pattern;
```

---

### (հատուկ նշաններ)

LIKE operator-ում օգտագործվում են հատուկ նշաններ

| Symbol | Meaning             |
|--------|---------------------|
| `%`    | ցանկացած քանակի նիշ |
| `_`    | մեկ նիշ             |

---

### Example 1 — Սկսվում է A տառով տեքստը

```mysql
SELECT *
FROM students
WHERE name LIKE 'A%';
```

👉 Այսինքն անունը սկսվում է A-ով։

---

### Example 2 — Ավարտվում է n

```mysql
SELECT *
FROM students
WHERE name LIKE '%n';
```

👉 անունը ավարտվում է n-ով։

### Example 3 — Պարունակում է ann

```mysql
SELECT *
FROM students
WHERE name LIKE '%ann%';
```

👉 name column-ը պարունակում է ann։

### 📌 `_` Symbol

`_` նշանակում է մեկ նիշ

### Example 1 — 4 տառանոց անուն

```mysql
SELECT *
FROM students
WHERE name LIKE '____';
```

👉 4 հատ `_` նշանակում է 4 նիշ։

---

### Example 2 — Սկսվում է A-ով և ունի 3 տառ հետո

```mysql
SELECT *
FROM students
WHERE name LIKE 'A___';
```

---

### Python Example

```python
cursor.execute(
    "SELECT * FROM students WHERE name LIKE %s",
    ("A%",)
)

for row in cursor.fetchall():
    print(row)
```

---

### 📌 Useful Patterns

| **Pattern** | **Meaning**       |
|-------------|-------------------|
| `A%`        | սկսվում է A       |
| `%n`        | ավարտվում է n     |
| `%ann%`     | պարունակում է ann |
| `_a%`       | երկրորդ տառը a    |
| `____`      | 4 նիշ             |

---

## 📌 IN Operator

IN-ը օգտագործվում է մի քանի արժեքներից մեկը ստուգելու համար։

### Example

```mysql
SELECT *
FROM students
WHERE age IN (20, 21, 22);
```

---

### Python Example

```python
cursor.execute(
    "SELECT * FROM students WHERE age IN (%s,%s,%s)",
    (20, 21, 22)
)

for row in cursor.fetchall():
    print(row)
```

---

## 📌 Full Example

```python
import mysql.connector

connection = mysql.connector.connect(
    host="localhost",
    database="school",
    user="root",
    password="your_password"
)

cursor = connection.cursor()

query = """
SELECT *
FROM students
WHERE age > %s AND name LIKE %s
"""

cursor.execute(query, (20, "A%"))

for student in cursor.fetchall():
    print(student)

cursor.close()
connection.close()
```

---

## 📌 Important Concepts

| **Concept** | **Meaning**          | 
|-------------|----------------------|
| WHERE       | Filter data          |
| AND         | Both conditions true |
| OR          | One condition true   |
| NOT         | Reverse condition    |
| NULL        | Empty value          |
| LIKE        | Search text pattern  |
| IN          | Multiple values      |


---

## Exercises 📝

### Task 1 — Տպել students որոնց age > 21

### Task 2 — Տպել students որոնց age = 20 կամ age = 25

### Task 3 — Տպել students որոնց name սկսվում է A տառով

### Task 4 — Տպել students որոնց age NOT = 21

### Task 5 — Տպել students որոնց age ∈ (20,21,22)




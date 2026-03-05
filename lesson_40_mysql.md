<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 40 – Python MySQL Insert & Select

---

## ## 📌 Table ի՞նչ է

Table-ը database-ի հիմնական բաղադրիչն է, որտեղ պահվում են տվյալները։

Table-ը նման է Excel աղյուսակի։

| id | name | age |
|----|------|-----|
| 1  | Anna | 21  |
| 2  | John | 22  |

## 📌 Create Table Syntax

```sql
CREATE TABLE table_name
(
    column1 datatype,
    column2 datatype
);
```

## 📌 Python-ից Table ստեղծել

```python
import mysql.connector

connection = mysql.connector.connect(
    host="localhost",
    database="school",
    user="root",
    password="your_password"
)

cursor = connection.cursor()

cursor.execute("""
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    age INT
)
""")

print("Table created successfully ✅")

cursor.close()
connection.close()
```

---

## 📌 Create Table Syntax

```sql
CREATE TABLE table_name
(
    column1 datatype,
    column2 datatype
);

##
📌
Ի
՞նչ է Insert

Insert-ը SQL հրաման է, որը օգտագործվում է **table-ի մեջ նոր տվյալ ավելացնելու համար**
։

👉 Այսինքն մենք **ստեղծում ենք նոր row (տող)** table-ի մեջ
։

---

##
📌 Insert Syntax

```mysql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);
```

---

## 📌 Python-ից Insert անել

```python
import mysql.connector

connection = mysql.connector.connect(
    host="localhost",
    database="school",
    user="root",
    password="your_password"
)

cursor = connection.cursor()

sql = "INSERT INTO students (name, age) VALUES (%s, %s)"
values = ("Anna", 21)

cursor.execute(sql, values)

connection.commit()

print("Student inserted successfully ✅")

cursor.close()
connection.close()
```

---

## 📌 Ինչու է պետք commit()

MySQL-ում փոփոխությունները մինչ commit չանենք չեն պահպանվում։

```python
connection.commit()
```

---

## 📌 Multiple Insert

Միանգամից կարող ենք ավելացնել մի քանի տվյալ։

```python
students = [
    ("John", 22),
    ("Emma", 20),
    ("David", 23)
]

cursor.executemany(
    "INSERT INTO students (name, age) VALUES (%s, %s)",
    students
)

connection.commit()
```

---

## 📌 Ի՞նչ է Select

Select-ը SQL հրաման է, որը օգտագործվում է table-ից տվյալներ ստանալու համար։

---

## 📌 Select Syntax

```mysql
SELECT *
FROM table_name;
```

---

## 📌 Python-ում Select example

```python
cursor.execute("SELECT * FROM students")

results = cursor.fetchall()

for row in results:
    print(row)
```

---

## 📌 fetchall()

fetchall() վերադարձնում է բոլոր rows-ը։

```python
results = cursor.fetchall()
```

Օրինակ արդյունքի՝

```text
(1, 'Anna', 21)
(2, 'John', 22)
(3, 'Emma', 20)
```

---

## 📌 fetchone()

Եթե ուզում ենք միայն մեկ row։

```python
cursor.execute("SELECT * FROM students")

row = cursor.fetchone()

print(row)
```

---

## 📌 Specific Columns Select

Կարող ենք վերցնել միայն որոշ սյունակներ։

```python
cursor.execute("SELECT name, age FROM students")

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

students = [
    ("Anna", 21),
    ("John", 22),
    ("Emma", 20)
]

cursor.executemany(
    "INSERT INTO students (name, age) VALUES (%s, %s)",
    students
)

connection.commit()

cursor.execute("SELECT * FROM students")

for row in cursor.fetchall():
    print(row)

cursor.close()
connection.close()
```

---

## 📌 Important Concepts

| Concept           | Meaning                      |
|-------------------|------------------------------|
| **INSERT**        | Ավելացնում է նոր տվյալ       |
| **SELECT**        | Ստանում է տվյալներ           |
| **execute()**     | Կատարում է SQL query         |
| **executemany()** | Կատարում է մի քանի insert    |
| **fetchall()**    | Վերադարձնում է բոլոր rows    |
| **fetchone()**    | Վերադարձնում է մեկ row       |
| **commit()**      | Պահպանում է փոփոխությունները |

---

## Exercises 📝

---

### ✅ Task 1 — Ավելացնել մեկ student

- Ստեղծել `students` table֊ը
- Ստեղծել student `students` table-ի մեջ

```text
name = Maria
age = 24
```

<details> <summary>💡 Solution</summary>

```python
sql = "INSERT INTO students (name, age) VALUES (%s, %s)"
values = ("Maria", 24)

cursor.execute(sql, values)
connection.commit()
```

</details>

---

### ✅ Task 2 — Ավելացնել 5 students

Ավելացնել հետևյալ տվյալները

```text
Alex 22
Lilit 19
Karen 25
Ani 20
Gor 23
```

<details> <summary>💡 Solution</summary>

```python
students = [
    ("Alex", 22),
    ("Lilit", 19),
    ("Karen", 25),
    ("Ani", 20),
    ("Gor", 23)
]

cursor.executemany(
    "INSERT INTO students (name, age) VALUES (%s, %s)",
    students
)

connection.commit()
```

</details>

---

### ✅ Task 3 — Տպել բոլոր students

Տպել ամբողջ students table-ը։

<details> <summary>💡 Solution</summary>

```python
cursor.execute("SELECT * FROM students")

for student in cursor.fetchall():
    print(student)
```

</details>

---

### ✅ Task 4 — Տպել միայն մեկ student

Տպել միայն առաջին student-ը։

<details> <summary>💡 Solution</summary>

```python
cursor.execute("SELECT * FROM students")

student = cursor.fetchone()

print(student)
```

</details>

### ✅ Task 5 — Տպել միայն անունները

Տպել միայն `name` column-ը։

<details> <summary>💡 Solution</summary>

```python
cursor.execute("SELECT name FROM students")

for name in cursor.fetchall():
    print(name)
```

</details>

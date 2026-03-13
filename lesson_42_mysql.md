<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 42 – Python MySQL Update, Delete & Aggregation

---

## 📌 Ի՞նչ է WHERE Clause

**UPDATE** հրամանը օգտագործվում է table-ի մեջ արդեն գոյություն ունեցող տվյալները **փոփոխելու** համար։

Այսինքն մենք փոխում ենք **row**-ի արժեքները։

Օրինակ table

| id | name | age |
|----|------|-----|
| 1  | Anna | 21  |
| 2  | John | 22  |

Եթե ուզում ենք **Anna-ի age-ը դարձնել 23**։

---

### 📌 UPDATE Syntax

```mysql
UPDATE table_name
SET column1 = value1
WHERE condition;
```

⚠️ Եթե WHERE չգրենք, **կփոխվեն** բոլոր **rows**-ները։

---

### 📌 Python Example

```python
cursor = connection.cursor()

sql = "UPDATE students SET age = %s WHERE name = %s"
values = (23, "Anna")

cursor.execute(sql, values)

connection.commit()
```

---

## 📌 DELETE Statement

**DELETE** հրամանը օգտագործվում է table-ից տվյալ **ջնջելու** համար։

---

### 📌 DELETE Syntax

```mysql
DELETE
FROM table_name
WHERE condition;
```

⚠️ Եթե WHERE չգրենք, **կջնջվեն** բոլոր **rows**-ները։

---

### 📌 Python Example

```python
cursor = connection.cursor()

sql = "DELETE FROM students WHERE name = %s"
value = ("John",)

cursor.execute(sql, value)

connection.commit()
```

---

## 📌 LIMIT Clause

**LIMIT**-ը օգտագործվում է քանի **row** վերադարձնելը սահմանափակելու համար։

---

### 📌 LIMIT Syntax

```mysql
SELECT *
FROM table_name
LIMIT number;
```

---

### 📌 Python Example

```python
cursor.execute("SELECT * FROM students LIMIT 3")

for row in cursor.fetchall():
    print(row)
```

---

## 📌 MIN() Function

**MIN()** ֆունկցիան վերադարձնում է **ամենափոքր** արժեքը column-ից։

---

### Syntax

```mysql
SELECT MIN(column_name)
FROM table_name;
```

---

### Python Example

```python
cursor.execute("SELECT MIN(age) FROM students")

result = cursor.fetchone()

print("Minimum age:", result[0])
```

---

## 📌 MAX() Function

**MAX()** վերադարձնում է **ամենամեծ** արժեքը column-ից։

---

### Syntax

```mysql
SELECT MAX(column_name)
FROM table_name;
```

### Python Example

```python
cursor.execute("SELECT MAX(age) FROM students")

result = cursor.fetchone()

print("Maximum age:", result[0])
```

---

## 📌 GROUP BY Statement

**GROUP BY** օգտագործվում է **նման արժեքները խմբավորելու համար**։

Օրինակ table

| name | age |
|------|-----|
| Anna | 21  |
| John | 21  |
| Emma | 20  |

---

### GROUP BY Syntax

```mysql
SELECT column_name, COUNT(*)
FROM table_name
GROUP BY column_name;
```

---

### Python Example

```python
cursor.execute("""
SELECT age, COUNT(*)
FROM students
GROUP BY age
""")

for row in cursor.fetchall():
    print(row)
```

**Օրինակ արդյունք`**

```text
(20, 1)
(21, 2)
```

**👉 Սա նշանակում է**

- age 20 → 1 student
- age 21 → 2 students

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

# UPDATE
cursor.execute(
    "UPDATE students SET age = %s WHERE name = %s",
    (23, "Anna")
)

# SELECT WITH LIMIT
cursor.execute("SELECT * FROM students LIMIT 5")

for row in cursor.fetchall():
    print(row)

connection.commit()

cursor.close()
connection.close()
```

---

### 📌 Important Concepts

| Concept  | Meaning                   |
|----------|---------------------------|
| UPDATE   | փոփոխում է տվյալները      |
| DELETE   | ջնջում է տվյալները        |
| LIMIT    | սահմանափակում է արդյունքը |
| MIN()    | ամենափոքր արժեք           |
| MAX()    | ամենամեծ արժեք            |
| GROUP BY | խմբավորում է տվյալները    |

---

## Exercises 📝

### ✅ Task 1

Փոխել student-ի age-ը

```text
name = Alex
age = 24
```

---

### ✅ Task 2

Ջնջել student

```text
name = Karen
```

---

### ✅ Task 3

Տպել միայն առաջին 3 students

---

### ✅ Task 4

Տպել students table-ից ամենափոքր age-ը

---

### ✅ Task 5

Տպել students table-ից ամենամեծ age-ը

---

### ✅ Task 6

Խմբավորել students-ը ըստ age-ի և հաշվել նրանց քանակը։


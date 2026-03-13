<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 43 – Python MySQL JOINS

---

## 📌 Ի՞նչ է JOIN

**JOIN**-ը օգտագործվում է մի քանի table-երից տվյալներ միասին ստանալու համար։

Database-ում տվյալները հաճախ պահվում են տարբեր table-երում։

Օրինակ.

**students table**

| id | name | course_id |
|----|------|-----------|
| 1  | Anna | 1         |
| 2  | John | 2         |
| 3  | Emma | 1         |

**courses table**

| id | title  |
|----|--------|
| 1  | Python |
| 2  | SQL    |

Եթե ուզում ենք տեսնել

```text
Student name + Course title
```

պետք է օգտագործենք JOIN։

---

## 📌 JOIN-ի գաղափարը

```text
students.course_id = courses.id
```

Այսինքն մենք կապում ենք երկու table-ները։

---

## 📌 INNER JOIN

**INNER JOIN**-ը վերադարձնում է այն rows-երը որոնք match են երկու table-ներում։

---

### Syntax

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

---

### Example

```sql
SELECT students.name, courses.title
FROM students
INNER JOIN courses
ON students.course_id = courses.id;
```

---

### Python Example

```python
query = """
SELECT students.name, courses.title
FROM students
INNER JOIN courses
ON students.course_id = courses.id
"""

cursor.execute(query)

for row in cursor.fetchall():
    print(row)
```

---

### Example Result

```terminaloutput
('Anna', 'Python')
('John', 'SQL')
('Emma', 'Python')
```

---

## 📌 LEFT JOIN

**LEFT JOIN**-ը վերադարձնում է

- բոլոր rows-ը **ձախ table**-ից
- և match եղած rows-ը աջ table-ից

Եթե match չկա → NULL։

---

### Syntax

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

---

### Example

```sql
SELECT students.name, courses.title
FROM students
LEFT JOIN courses
ON students.course_id = courses.id;
```

---

### Python Example

```python
cursor.execute("""
SELECT students.name, courses.title
FROM students
LEFT JOIN courses
ON students.course_id = courses.id
""")

for row in cursor.fetchall():
    print(row)
```

---

## 📌 RIGHT JOIN

**RIGHT JOIN**-ը վերադարձնում է

- բոլոր rows-ը **աջ table**-ից
- և match եղած rows-ը ձախ table-ից

---

### Syntax

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```

---

### Example

```sql
SELECT students.name, courses.title
FROM students
RIGHT JOIN courses
ON students.course_id = courses.id;
```

---

### Python Example

```python
cursor.execute("""
SELECT students.name, courses.title
FROM students
RIGHT JOIN courses
ON students.course_id = courses.id
""")

for row in cursor.fetchall():
    print(row)
```

---

## 📌 CROSS JOIN

CROSS JOIN-ը ստեղծում է **բոլոր հնարավոր combinations**։

Օրինակ

3 students
2 courses

կստանանք

```text
3 × 2 = 6 rows
```

---

### Syntax

```sql
SELECT *
FROM table1
CROSS JOIN table2;
```

---

### Python Example

```python
cursor.execute("""
SELECT students.name, courses.title
FROM students
CROSS JOIN courses
""")

for row in cursor.fetchall():
    print(row)
```

---

## 📊 JOIN-ի ամենապարզ Visualization

Պատկերացնենք ունենք 2 table։

**students**

| id | name  | course_id |
| -- | ----- | --------- |
| 1  | Anna  | 1         |
| 2  | John  | 2         |
| 3  | Emma  | 1         |
| 4  | David | NULL      |

---

**courses**

| id | title  |
|----|--------|
| 1  | Python |
| 2  | SQL    |
| 3  | Java   |

---

### INNER JOIN

Վերցնում է **միայն match եղած rows-երը**։

Match condition

```sql
students.course_id = courses.id
```

Արդյունք

| name | title  |
| ---- | ------ |
| Anna | Python |
| John | SQL    |
| Emma | Python |

👉 David-ը չի երևում, որովհետև course չունի։

---

### LEFT JOIN

Վերցնում է

- բոլոր rows **ձախ table-ից**
- match եղածները աջ table-ից

Արդյունք

| name  | title  |
| ----- | ------ |
| Anna  | Python |
| John  | SQL    |
| Emma  | Python |
| David | NULL   |

👉 David-ը հայտնվում է, որովհետև LEFT JOIN է։

---

### RIGHT JOIN

Վերցնում է

- բոլոր rows **աջ table-ից**
- match եղածները ձախ table-ից

Արդյունք

| name | title  |
| ---- | ------ |
| Anna | Python |
| John | SQL    |
| Emma | Python |
| NULL | Java   |

👉 Java course-ը երևում է նույնիսկ եթե student չունի։

---

### CROSS JOIN

CROSS JOIN նշանակում է **բոլոր combinations**։

4 students
3 courses

կստանանք 

```text
4 × 3 = 12 rows
```

Արդյունք

| name  | title  |
|-------|--------|
| Anna  | Python |
| Anna  | SQL    |
| Anna  | Java   |
| John  | Python |
| John  | SQL    |
| John  | Java   |
| Emma  | Python |
| Emma  | SQL    |
| Emma  | Java   |
| David | Python |
| David | SQL    |
| David | Java   |

---

### 📌 JOIN Types Summary

| JOIN Type  | Meaning                 |
| ---------- | ----------------------- |
| INNER JOIN | միայն matching rows     |
| LEFT JOIN  | բոլոր rows ձախ table-ից |
| RIGHT JOIN | բոլոր rows աջ table-ից  |
| CROSS JOIN | բոլոր combinations      |

---

## Exercises 📝

### ✅ Task 1

ստանալ

```text
student name + course title
```

օգտագործելով **INNER JOIN**

---

### ✅ Task 2

ստանալ բոլոր students-ը նույնիսկ եթե course չունեն։

օգտագործել **LEFT JOIN**

---

### ✅ Task 3

ստանալ բոլոր courses-ը նույնիսկ եթե student չունեն։

օգտագործել **RIGHT JOIN**

---

### ✅ Task 4

ստանալ students × courses combinations

օգտագործելով **CROSS JOIN**











<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 39 – Python + MySQL Introduction 

## 📌 Ի՞նչ է Database

Database (Տվյալների բազա) = համակարգ, որտեղ պահվում են տվյալներ կազմակերպված ձևով։

**Օրինակ կյանքից**

- Excel ֆայլ → տվյալների աղյուսակ

- Գրադարան → գրքերի համակարգված հավաքածու

- Բանկ → հաճախորդների տվյալների բազա

---

## 📌 Ի՞նչ է MySQL

MySQL-ը Database Management System (DBMS) է։

👉 Այն ծրագիր է, որը թույլ է տալիս ստեղծել, պահպանել, փոփոխել և ջնջել տվյալներ։

---

## 📌 Ինչպե՞ս է աշխատում MySQL-ը

```text
Python
        ↓
MySQL Server
        ↓
Database
        ↓
Tables
        ↓
Rows (տողեր)
```

---

## 📌 Python + MySQL կապը

Python-ը կարող է միանալ MySQL-ին հատուկ library-ի միջոցով։

Մենք կօգտագործենք՝

```shell
pip install mysql-connector-python
```

---

## Ստուգում՝

```shell
pip list
```

---

## 📌 MySQL-ի հետ Connection ստեղծել

```python
import mysql.connector
from mysql.connector import Error

connection = mysql.connector.connect(
    host="localhost",
    user="root",
    password="your_password",
    port="3306",
)

print("Connection successful ✅")
```

---

## 📌 Cursor ի՞նչ է

Cursor-ը object է, որի միջոցով կարող ենք SQL հարցումներ կատարել։

```python
cursor = connection.cursor()
```

---

## 📌 SQL Query կատարել Python-ից

```python
cursor.execute("SHOW DATABASES")

for db in cursor:
    print(db)
```

--- 

## 📌 Connection փակել

```python
cursor.close()
connection.close()
```

👉 Միշտ պետք է փակել connection-ը

---

## 📌 Full Example

```python
import mysql.connector
from mysql.connector import Error

connection = None
cursor = None

try:
    connection = mysql.connector.connect(
        host="localhost",
        database="your_database",
        user="root",
        password="your_password",
        port="3306",
    )

    if connection.is_connected():
        cursor = connection.cursor()
        cursor.execute("SHOW DATABASES")
        for db_name in cursor.fetchall():
            print(db_name)

except Error as e:
    print('Error while connecting to MySQL', e)

finally:
    if cursor is not None:
        cursor.close()
    if connection is not None and connection.is_connected():
        connection.close()
        print('MySQL connection is closed')

```

---

## 📌 Important Terms

| Concept      | Meaning                    |
|--------------|----------------------------|
| **Host**     | Server address (localhost) |
| **User**     | MySQL username             |
| **Password** | MySQL password             |
| **Cursor**   | Executes SQL queries       |
| **Execute**  | Runs SQL command           |
| **Commit**   | Saves changes              |
| **Close**    | Closes connection          |

---

## 📌 Typical Errors

**❌** `Access denied for user` → սխալ password  
**❌** `Can't connect to MySQL server` → MySQL service չի աշխատում

---

# Exercises 📝

## ✅ Task 1 — Միանալ MySQL-ին և տպել բոլոր Databases

---

## ✅ Task 2 — Ստուգել արդյոք connection կա

---

## ✅ Task 3 — Սխալ Password դնել և մշակել error-ը

<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 17: Python Dictionaries

link to presentation:

- https://www.canva.com/design/DAF1M4xA-wI/HIvR5s5jU4SMR4Vrrs76CQ/edit

---

## 🟢 What Is a Dictionary?

A dictionary is used to store data in key–value pairs.
Each key must be unique, and each value can be any data type.

```python
# Example
capital_cities = {
    "France": "Paris",
    "Germany": "Berlin",
    "Armenia": "Yerevan"
}
print(capital_cities)
```

---

## 🟢 Accessing Dictionary Values

You can access values by their **key**:

```python
student = {
    "name": "Aram",
    "age": 20,
    "grade": 85
}

print(student["name"])  # Output: Aram
print(student["age"])  # Output: 20
```

---

## 🟢 Updating and Adding Values

```python
student = {"name": "Davit", "age": 20}
student["age"] = 21
student["course"] = "Math"

print(student)
```

---

## 🟢 Looping Through a Dictionary

### 🔹 Loop through keys:

```python
student = {
    "name": "Aram",
    "age": 20,
    "grade": 85
}

for key in student.keys():
    print(key)

# or 

for key in student:
    print(key)

```

### 🔹 Loop through values:

```python
student = {
    "name": "Aram",
    "age": 20,
    "grade": 85
}

for value in student.values():
    print(value)
```

### 🔹 Loop through items (key–value pairs):

```python
student = {
    "name": "Aram",
    "age": 20,
    "grade": 85
}

for key, value in student.items():
    print(key, ":", value)
```

---

## 🟢 Checking Key Existence

```python
student = {
    "name": "Aram",
    "age": 20,
    "grade": 85
}

if "grade" in student:
    print("Grade exists")
else:
    print("Grade does not exist")
```

---

## 🟢 Removing Key–Value Pairs

```python
student.pop("grade")
print(student)
```

---

## 🟢 Example: Dictionary with Conditions

```python
student_scores = {
    "Armen": 81,
    "Sargis": 100,
    "Ani": 99,
    "Anna": 74,
    "Sona": 62,
}

grade_result = {}

for name in student_scores:
    score = student_scores[name]
    if score > 90:
        grade_result[name] = "Շատ լավ"
    elif score > 80:
        grade_result[name] = "Լավ"
    elif score > 70:
        grade_result[name] = "Միջին"
    else:
        grade_result[name] = "Չհաղթահարեց"

print(grade_result)
```

---

## 🟢 Common Dictionary Methods

Got it ✅ — here’s your **Common Dictionary Methods** table in the same style and format as your string methods example:

| Method               | Description                                        | Example                            | Output                                     |
|:---------------------|:---------------------------------------------------|:-----------------------------------|:-------------------------------------------|
| `.keys()`            | Returns all keys in the dictionary                 | `student.keys()`                   | `dict_keys(['name', 'age', 'course'])`     |
| `.values()`          | Returns all values in the dictionary               | `student.values()`                 | `dict_values(['Aram', 21, 'Math'])`        |
| `.items()`           | Returns all key-value pairs as tuples              | `student.items()`                  | `[('name', 'Aram'), ('age', 21)]`          |
| `.get(key, default)` | Returns the value for a key, or default if missing | `student.get('grade', 'No grade')` | `'No grade'`                               |
| `.pop(key)`          | Removes the key and returns its value              | `student.pop('age')`               | `21`                                       |
| `.update(dict)`      | Updates the dictionary with another dictionary     | `student.update({'grade': 95})`    | `{'name': 'Aram', 'age': 21, 'grade': 95}` |
| `.clear()`           | Removes all items from the dictionary              | `student.clear()`                  | `{}`                                       |
| `len(dict)`          | Returns the number of key-value pairs              | `len(student)`                     | `3`                                        |
| `"key" in dict`      | Checks if a key exists in the dictionary           | `'name' in student`                | `True`                                     |
| `for k in dict`      | Iterates through all keys                          | `for k in student: print(k)`       | `name`, `age`, `course`                    |

# Exercises

## ✅ Ex. 1 — Սիրելի ֆիլմեր

- Ստեղծիր dictionary, որը կոչվում է favorites, որտեղ բանալիները (keys) մարդկանց անուններն են, իսկ արժեքները (values)՝
  նրանց սիրելի ֆիլմերը։
- Տպիր բոլոր այն մարդկանց անունները, ում սիրելի ֆիլմը "Avatar" է։

---

## ✅ Ex. 2 — Ապրանքների գներ

Տրված է՝

```python
products = {"apple": 500, "banana": 300, "mango": 800}

```

- Օգտատիրոջից հարցրու ապրանքի անունը։
- Տպիր նրա գինը։
- Եթե այդ ապրանքը գոյություն չունի, տպիր "Ապրանքը չի գտնվել։"

## ✅ Ex. 3 — Բառերի հաճախականություն

Գրի՛ր ծրագիր, որը կհաշվի, թե քանի անգամ է յուրաքանչյուր բառ հանդիպում այս ցուցակում՝

```python
words = ["apple", "banana", "apple", "orange", "banana", "apple"]
```

Արդյունքը պետք է լինի այս ձևով՝

```python
{'apple': 3, 'banana': 2, 'orange': 1}
```

---

## ✅ Ex. 4 — Ուսանողների գնահատականներ

- Օգտատիրոջից հարցրու 3 ուսանողի անուն և նրանց միավորները։

- Պահպանիր դրանք dictionary-ում։

- Տպիր՝
    - Ամենաբարձր միավորը
    - Ամենացածր միավորը
    - Միջին միավորը

---

## ✅ Ex. 5 — Reverse Lookup

Given a dictionary:

```python
country_capitals = {"France": "Paris", "Germany": "Berlin", "Italy": "Rome"}
```

- Օգտատիրոջից հարցրու մայրաքաղաքի անունը (օրինակ՝ "Berlin")։
- Տպիր՝ որ երկրի մայրաքաղաքն է դա։
- Եթե մայրաքաղաքը չի գտնվել, ապա տպիր "Մայրաքաղաքը չի գտնվել"

---

## ✅ Ex. 6 — Գնացքի ուղևորների տվյալներ

- Ստեղծիր dictionary, որտեղ key֊ը կլինի վագոնի համարը, իսկ value֊ն՝ ուղևորների քանակը։
- Ավելացրու 3 տարբեր վագոնների տվյալներ։
- Տպիր ընդհանուր ուղևորների քանակը։

---

## ✅ Ex. 7 — Աշխատակիցների աշխատավարձեր

Առաջադրանք՝

Ստեղծիր dictionary, որտեղ key֊երը աշխատակիցների անուններն են, իսկ value֊ները՝ նրանց աշխատավարձերը։

Գտիր և տպիր ամենաբարձր աշխատավարձ ունեցող աշխատակցի անունը և գումարը։

---

<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 36 – JSON

- JSON-ը տվյալների պահպանման և փոխանակման ձև է։
- JSON-ը տեքստ է, որը գրված է JavaScript օբյեկտի միջոցով։

### JSON-ը Python-ում

Python-ն ունի ներկառուցված փաթեթ, որը կոչվում է json, և որը կարող է օգտագործվել JSON տվյալների հետ աշխատելու համար։
Ներմուծեք json մոդուլը՝

```python
import json
```

### Parse JSON—Convert from JSON to Python (Փոխակերպում JSON-ից Python)

Եթե դուք ունեք JSON տող, կարող եք այն վերածել՝ օգտագործելով `json.loads()` մեթոդը։
> Արդյունքը կլինի Python-ի բառարան (Python dictionary):

```python
import json

# some JSON:
x = '{ "name":"John", "age":30, "city":"New York"}'

# parse x:
y = json.loads(x)

# the result is a Python dictionary:
print(y["age"])
```

---

### Convert from Python to JSON (Փոխակերպում Python-ից JSON)

Եթե դուք ունեք Python-ի օբյեկտ, կարող եք այն փոխակերպել JSON տողի՝ օգտագործելով `json.dumps()` մեթոդը։  
Փոխակերպում Python-ից JSON՝

```python
import json

# a Python object (dict):
x = {
    "name": "John",
    "age": 30,
    "city": "New York"
}

# convert into JSON:
y = json.dumps(x)

# the result is a JSON string:
print(y)
```

Դուք կարող եք Python-ի հետևյալ տեսակների օբյեկտները փոխակերպել JSON տողերի.

- dict
- list
- tuple
- string
- int
- float
- True
- False
- None

### Օրինակ

Փոխակերպել Python-ի օբյեկտները JSON տողերի և տպել արժեքները:

```python
import json

print(json.dumps({"name": "John", "age": 30}))
print(json.dumps(["apple", "bananas"]))
print(json.dumps(("apple", "bananas")))
print(json.dumps("hello"))
print(json.dumps(42))
print(json.dumps(31.76))
print(json.dumps(True))
print(json.dumps(False))
print(json.dumps(None))
```

---

## Տնային

### Վարժություն 1 — JSON string → Python dict (loads)

Տրված JSON տողը փոխակերպիր Python dictionary-ի, հետո տպիր city արժեքը։

```python
x = '{ "name":"Anna", "age":12, "city":"Yerevan"}'
```

---

### Վարժություն 2 — Python dict → JSON string (dumps)

Ստեղծիր Python dictionary՝ աշակերտի տվյալներով (name, grade, is_student) և այն վերածիր JSON տողի ու տպիր։

---

### Վարժություն 3 — JSON list → Python list և հաշվարկ

Տրված JSON տողը (թվերի ցուցակ) փոխակերպիր Python list-ի և տպիր թվերի գումարը։

```python
nums = '[10, 5, 7, 3]'
```

---

### Վարժություն 4 — JSON-ից արժեքների դուրսբերում (nested)

Տրված JSON տողից ստացիր Python dict, հետո տպիր՝

- `name`
- `scores` ցուցակի առաջին թիվը

```python
data = '{ "name":"Mariam", "scores":[18, 20, 17] }'
```

---

### Վարժություն 5 — Python list of dicts → JSON string

Ստեղծիր Python list, որի մեջ կլինեն 3 dictionary՝
յուրաքանչյուր dictionary-ում լինի `id` և `title`։
Հետո ամբողջ ցուցակը փոխակերպիր JSON-ի և տպիր։

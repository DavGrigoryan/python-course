<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 38 – API

## 📌 Ի՞նչ է API

API = Application Programming Interface

Պարզ լեզվով՝  
👉 API-ը “դռնապան” է, որի միջոցով մի ծրագիր խոսում է ուրիշ ծրագրի հետ։

**Օրինակ կյանքից**

- Դու → հաճախորդ
- Ռեստորան → սերվեր
- Սպասարկող → API

Դու պատվիրում ես (request),  
Սպասարկողը գնում է խոհանոց (backend),  
Բերում է պատասխանը (response)։

---

## 📌 Ինչպե՞ս է աշխատում API-ն

### 🔎 Հիմնական հասկացություններ

| Մաս             | Նշանակություն                                 |
|-----------------|-----------------------------------------------|
| **Endpoint**    | URL, ուր request ենք ուղարկում                |
| **Method**      | GET, POST, PUT, DELETE                        |
| **Request**     | Հարցումը                                      |
| **Response**    | Պատասխանը                                     |
| **Status Code** | 200 (OK), 404 (Not Found), 500 (Server Error) |

---

## 📌 Python-ում request անել (requests library)

Սկզբից պետք է տեղադրել `requests`․

```shell
pip install requests
```

---

## 📌 Public API օրինակներ

### 🟢 Օրինակ 1 — Random Dog API

**Endpoint:** https://dog.ceo/api/breeds/image/random

```python
import requests

url = 'https://dog.ceo/api/breeds/image/random'

response = requests.get(url)

print('Status code:', response.status_code)

data = response.json()

print('Dog image URL:')
print(data['message'])
```

---

### 🟢 Օրինակ 2 — Countries API

**Endpoint:** https://restcountries.com/v3.1/name/france

```python
import requests
import json

url = 'https://restcountries.com/v3.1/name/france'

response = requests.get(url)

data = response.json()
print(json.dumps(data, indent=2, ensure_ascii=False))

country = data[0]

print('Country:', country['name']['common'])
print('Capital:', country['capital'][0])
print('Population:', country['population'])
```

---

### 🟢 Օրինակ 3 — Open Meteo (Weather API)

**Endpoint:** https://api.open-meteo.com/v1/forecast

```python
import requests

url = "https://api.open-meteo.com/v1/forecast"
params = {
    "latitude": 40.18,
    "longitude": 44.51,
    "current_weather": True
}

response = requests.get(url, params=params)

data = response.json()

print("Temperature:", data['current_weather']['temperature'])
```

---

## 📌 GET vs POST օրինակ

```python
import requests

url = 'https://httpbin.org/post'

payload = {
    "name": "Tigran",
    "course": "API lesson"
}

response = requests.post(url, json=payload)

print(response.json())
```

---

## PUT example

```python
import requests

url = 'https://jsonplaceholder.typicode.com/posts/1'

payload = {
    'id': 1,
    'title': 'Updated title',
    'body': 'Updated body text',
    'userId': 1
}

response = requests.put(url, json=payload)

print('Status:', response.status_code)
print(response.json())
```

---

## DELETE example

```python
import requests

url = 'https://jsonplaceholder.typicode.com/posts/1'

response = requests.delete(url)

print('Status:', response.status_code)
print('Response text:', response.text)  # սովորաբար դատարկ է
```

---

## 📌 Status Codes գաղափար

```python
import requests

response = requests.get("https://httpbin.org/status/404")

if response.status_code == 200:
    print("Success")
elif response.status_code == 404:
    print("Not Found")
```

---

## 📌 Ինչ են HTTP Methods

| Method     | Նշանակություն   |
|------------|-----------------|
| **GET**    | Ստանալ տվյալներ |
| **POST**   | Ստեղծել         |
| **PUT**    | Թարմացնել       |
| **DELETE** | Ջնջել           |

---

## Exercises 📝

### ✅ Task 1 — Dog API-ից տպել 5 տարբեր նկարների URL

---

### ✅ Task 2 — Countries API-ից տպել երկրի դրոշի URL

---

### ✅ Task 3 — Ստուգել GitHub username գոյություն ունի՞

<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 20: Nested Data Structures & Recursion

---

### ✳️ Nested Lists

A nested list is a list that contains other lists inside it.

```python
nested = [1, [2, [3, 4], 5], 6]
print(nested)
```

Accessing elements:

```python
print(nested[1])  # [2, [3, 4], 5]
print(nested[1][1])  # [3, 4]
print(nested[1][1][0])  # 3
```

---

### ✳️ Flatten a Nested List (Recursive)

```python
def flatten(list_data):
    flat_list = []
    for i in list_data:
        if isinstance(i, list):
            flat_list.extend(flatten(i))  # recursive call
        else:
            flat_list.append(i)
    return flat_list


nested_list = [
    1,
    [2, [4, 4], 5],
    6,
    [7, 8]
]
print(flatten(nested_list))  # ➜ [1, 2, 4, 4, 5, 6, 7, 8]
```

---

### ✳️ Count Element in Nested List

```python
def count_in_nested(list_data, element):
    count = 0
    for i in list_data:
        if isinstance(i, list):
            count += count_in_nested(i, element)
        elif i == element:
            count += 1
    return count


nested_list = [1, [2, 3, [1, 1], 4], 1, 5]
print(count_in_nested(nested_list, 1))  # ➜ 4
```

---

### ✳️ Creating a list of dictionaries

```python
list_of_dicts = [
    {'a': 1, 'b': 2},
    {'a': 3, 'c': 4},
    {'b': 5, 'a': 6}
]
```

---

### ✳️ Nested Dictionaries & Lists

```python
travel_log = {
    "France": {"cities_visited": ["Paris", "Lille", "Dijon"], "total_visits": 12},
    "Germany": {"cities_visited": ["Berlin", "Hamburg", "Stuttgart"], "total_visits": 5},
}

print(travel_log["France"]["cities_visited"][0])  # ➜ Paris
```

Or as a list of dictionaries:

```python
travel_log = [
    {"country": "France", "cities_visited": ["Paris", "Lille"], "total_visits": 12},
    {"country": "Germany", "cities_visited": ["Berlin", "Hamburg"], "total_visits": 5},
]
```

---

# Exercises

### 🧩 Ex. 1 - Հարթեցնել ներդրված ցուցակը

Գրիր ֆունկցիա՝ flatten_list(lst), որը վերադարձնում է մեկ մակարդակի LIST՝ տրված nested list֊ից։  
Այսինքն՝ եթե list֊ի մեջ կան այլ ցուցակներ, ֆունկցիան պետք է դրանք բացի և վերադարձնի մեկ ընդհանուր list բոլոր արժեքներով։

Օրինակ՝

```python
flatten_list([1, [2, 3], [4, [5, 6]]])
```

պետք է վերադարձնի՝

```python
[1, 2, 3, 4, 5, 6]
```

---

### 🧩 Ex. 2 - Հաշվել կոնկրետ արժեքի քանակը

Գրիր ռեկուրսիվ ֆունկցիա, որը հաշվում է, թե քանի անգամ է որևէ թիվ հանդիպում փոխանցված list֊ի մեջ։

Օրինակ՝

```python
count_value([1, [2, 3, [1, 1]], 4], 1)
```

պետք է վերադարձնի՝

```text
3
```

քանի որ թիվը 1 հանդիպում է երեք անգամ։
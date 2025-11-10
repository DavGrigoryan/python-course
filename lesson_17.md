<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 17: Python String Methods

link to presentation:

- https://www.canva.com/design/DAF1Msgm34U/KBS94njGyl_1qPL3fElzFw/edit

---

## 🟢 Common String Methods

| Method           | Description                                        | Example                     | Output            |
|:-----------------|:---------------------------------------------------|:----------------------------|:------------------|
| `.upper()`       | Converts all letters to uppercase                  | `"hello".upper()`           | `"HELLO"`         |
| `.lower()`       | Converts all letters to lowercase                  | `"HeLLo".lower()`           | `"hello"`         |
| `.capitalize()`  | Capitalizes only the first letter                  | `"python".capitalize()`     | `"Python"`        |
| `.title()`       | Capitalizes the first letter of every word         | `"hello world".title()`     | `"Hello World"`   |
| `.strip()`       | Removes spaces from both ends                      | `"  hi  ".strip()`          | `"hi"`            |
| `.replace(a, b)` | Replaces substring `a` with `b`                    | `"hello".replace("h", "y")` | `"yello"`         |
| `.split()`       | Splits the string into a list by spaces (default)  | `"a b c".split()`           | `["a", "b", "c"]` |
| `.join()`        | Joins list elements into one string                | `", ".join(["a","b","c"])`  | `"a, b, c"`       |
| `.startswith()`  | Checks if string starts with a given prefix        | `"hello".startswith("he")`  | `True`            |
| `.endswith()`    | Checks if string ends with a given suffix          | `"hello".endswith("lo")`    | `True`            |
| `.count()`       | Counts how many times a substring appears          | `"banana".count("a")`       | `3`               |
| `.find()`        | Returns index of first occurrence                  | `"hello".find("l")`         | `2`               |
| `.index()`       | Same as `.find()` but raises an error if not found | `"hello".index("l")`        | `2`               |
| `.isupper()`     | Checks if all letters are uppercase                | `"HELLO".isupper()`         | `True`            |
| `.islower()`     | Checks if all letters are lowercase                | `"hello".islower()`         | `True`            |
| `.isdigit()`     | Checks if string contains only digits              | `"123".isdigit()`           | `True`            |
| `.isalpha()`     | Checks if string contains only letters             | `"abc".isalpha()`           | `True`            |
| `.isalnum()`     | Checks if string contains only letters or digits   | `"abc123".isalnum()`        | `True`            |
| `.swapcase()`    | Switches lowercase to uppercase and vice versa     | `"PyThOn".swapcase()`       | `"pYtHoN"`        |
| `.center(width)` | Centers text with spaces                           | `"hi".center(6)`            | `"  hi  "`        |

### Practice Examples

```python
word = "python is fun"

print(word.upper())  # PYTHON IS FUN
print(word.capitalize())  # Python is fun
print(word.replace("fun", "awesome"))  # python is awesome
```

### Combining Methods with Lists

```python
words = ["apple", "banana", "kiwi"]
uppercased = [w.upper() for w in words]
print(uppercased)
# ['APPLE', 'BANANA', 'KIWI']
```

### Count Words in a Sentence

```python
sentence = "Python is fun to learn"
words = sentence.split()
print("Words:", words)
print("Word count:", len(words))
```

### Join Words Back

```python
joined = "-".join(words)
print(joined)  # Python-is-fun-to-learn
```

### structure of list comprehension

```text
[new_item for item in iterable if condition]
```

### Filter Names That Start With 'A'

```python
names = ["Aram", "Ani", "Sona", "Albert", "Lilit"]
a_names = [n for n in names if n.startswith("A")]
print(a_names)
```

### Capitalize Each Word

```python
sentence = "hello world of python"
capitalized = ' '.join([w.capitalize() for w in sentence.split()])
print(capitalized)  # Output: "Hello World Of Python"
```

## Exercises 📝

### 🟢 Exercise 1 — Upper and Lower

Ask the user for a sentence.
Print it in:

- բոլորը մեծատառ (uppercase)
- բոլորը փոքրատար (lowercase)
- capitalized (միայն առաջին տառը)

### 🟢 Exercise 2 — Replace Word

- Հարցրեք օգտատիրոջը նախադասություն
- Հարցրեք փոխարինվող բառը։
- Հարցրեք նոր բառը որը փոխարինվող բառի փոխարեն է լինելու
- Տպեք վերջնական նախադասությունը

### 🟢 Exercise 3 — Split and Join

Ask user for a sentence.
Split it into words, then join them back with `-`.

Հարցրեք օգտատիրոջից նախադասություն գրել։
Բաժանեք այն բառերի, ապա միացրեք դրանք «-» նշանով։

### 🟢 Exercise 4 — Starts With ‘A’

Տրված անունների ցանկից ստեղծեք նոր ցանկ, որը կպարունակի միայն «A»-ով սկսվող անուններ։

### 🟢 Exercise 5 — Count Vowels

Գրեք ծրագիր, որը կհաշվի ձայնավորների քանակը յուրաքանչյուր բառում՝ օգտագործելով ցիկլ(loop) կամ comprehension։

### 🟢 Exercise 6 — Longest Word

Այս տեքստից՝ `Python is amazing and powerful`, գտեք և տպեք ամենաերկար բառը։

### 🟢 Exercise 7 — Unique Letters

Հարցնում ենք օգտատիրոջը բառ, տպեք բոլոր տառերը (առանց կրկնելու):

### 🟢 Exercise 8 — Weather Message

Գրեք ֆունկցիա, որը պատահականորեն ընտրում է եղանակի տեսակը (արևոտ, ամպամած, անձրևոտ) և տպում է այն։

> “It’s a sunny day!”  
> օգտագործեք `.capitalize()` տեքստի ֆորմատը փոխելու համար առաջի տառը սարքելով մեծատառ.

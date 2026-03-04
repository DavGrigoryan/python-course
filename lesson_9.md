<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 9: For Loops in Python

link to presentation:

- https://www.canva.com/design/DAG0cAG99S0/i7w733ghRW9OzQ344zOBOA/edit

---

# 🔹 Basic for loop with range

```python
for i in range(1, 6):  # prints numbers from 1 to 5
    print(i)

for i in range(10):  # prints numbers from 0 to 9
    print(i)

for i in range(1, 6, 2):  # step = 2 → prints 1, 3, 5
    print(i)
    
for i in range(5, 0, -1):
    print(i)

# 🔹 Loop with text
for i in range(1, 6):
    print(i, "hello")
```

---

# 🔹 Iterating over a string

```python
name = "Artur"
for letter in name:
    print(letter)
```

---

# 🔹 Sum of numbers

```python
total = 0
for i in range(1, 6):
    total += i
print("Sum:", total)
```

---

# 🔹 Iterating through a list

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

---

# 🔹 Using `break`

```python
numbers = [1, 2, 3, 4, 5, 6]
for n in numbers:
    if n == 4:
        break
    print(n)
```

---

# 🔹 Using `continue`

```python
for i in range(1, 11):
    if i % 2 == 0:  # skip even numbers
        continue
    print(i)

names = ["Albert", "Ani", "Karen"]
for n in names:
    if n == "Ani":
        continue  # skip Ani
    print(n)
```

# 🔹 Even / Odd sum

```python
target = int(input("Enter number: "))
even_sum = 0
odd_sum = 0
is_target_even = target % 2 == 0

for i in range(target + 1):
    if is_target_even and i % 2 == 0:
        even_sum += i
    else:
        if i % 2 == 1:
            odd_sum += i

print(even_sum if is_target_even else odd_sum)
```

# 🔹 Palindrome check

```python
word = input("Enter a word: ").lower()
reversed_word = word[::-1]

if word == reversed_word:
    print(f"{word} is a palindrome!")
else:
    print(f"{word} is not a palindrome.")
```

# **Exercises 📝**

### 1. Թվեր 1-ից մինչև 20

Գրեք ցիկլ, որը կտպի 1-ից մինչև 20 բոլոր թվերը։

<details> <summary>💡 Solution</summary>

```python
for i in range(1, 21):
    print(i)
```

</details>

---

### 2. Թվերի քառակուսիներ

Տպեք 1-ից 10 թվերի քառակուսին։

<details> <summary>💡 Solution</summary>

```python
for i in range(1, 11):
    print(i, "square is", i ** 2)
```

</details>

---

### 3. Հակադարձ հաշվարկ

Տպեք թվերը 10-ից մինչև 1:

<details> <summary>💡 Solution</summary>

```python
for i in range(10, 0, -1):
    print(i)
```

</details>

---

### 4. Տպել նիշերը ինդեքսով

Խնդրեք օգտատիրոջից բառը և տպեք յուրաքանչյուր տառը իր ինդեքսային համարով։

<details> <summary>💡 Solution</summary>

```python
word = input("Enter a word: ")

for index in range(len(word)):
    print("Index:", index, "Letter:", word[index])
```

</details>

---

### 5. Հաշվեք ձայնավորները մեկ բառի մեջ

Գրիր մի ծրագիր, որը ստանում է տող (string) որպես մուտք և հաշվում է, թե քանի հնչյունավոր տառ կա տողում։ Հնչյունավոր
տառերն են՝ a, e, i, o, u։

<details> <summary>💡 Solution</summary>

```python
word = input("Enter a word: ")
vowels = "aeiouAEIOU"
count = 0

for letter in word:
    if letter in vowels:
        count += 1

print("Number of vowels:", count)
```

</details>

---

### 6. Առաջին N թվերի գումարը

Խնդրեք օգտատիրոջից n թիվը և տպեք 1-ից մինչև n թվերի գումարը։

<details> <summary>💡 Solution</summary>

```python
n = int(input("Enter a number: "))
total = 0

for i in range(1, n + 1):
    total += i

print("Sum of numbers from 1 to", n, "is:", total)
```

</details>

---

### 7. Հաշվեք բառերը նախադասության մեջ

Խնդրեք օգտատիրոջը նախադասություն գրել և հաշվել, թե քանի բառ կա այն (հուշում՝ հաշվեք բացատները):

<details> <summary>💡 Solution</summary>

```python
sentence = input("Enter a sentence: ")
words = sentence.split()   # բաժանում է բացատներով
print("Number of words:", len(words))
```

</details>


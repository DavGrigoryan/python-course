<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 4: f-Strings, Indexing & Conditions

link to presentation: https://www.canva.com/design/DAGhQ-3Y4Ds/8eDVMawapVUsYvmnq_UYhA/edit

---

**🔹 1. f-Strings (Formatted Strings)**

Instead of writing like this:

```python
miavor = 5
xax = 2
print("Qo miavorn e " + str(miavor) + ", u xaxacel es " + str(xax))
```

👉 We use f-strings:

```python
miavor = 5
xax = 2
hasak = 1.65
haxtanak = True

print(f"Qo miavorn e {miavor}, du xaxacel es {xax}")
print(f"Qo hasakn e {hasak}, haxtanaky {haxtanak}")
```

**🔹 2. Indexing Strings**

We can access letters of a word by their position:

```python
x = "barev"
print(x[0])  # First letter
print(x[1])  # Second letter
```

**🔹 3. Adding Digits from Input**

```python
erknish = input("Enter a 2-digit number: ")  # e.g. "42"
tiv1 = int(erknish[0])  # First digit → 4
tiv2 = int(erknish[1])  # Second digit → 2
print("Sum =", tiv1 + tiv2)
```

**🔹 4. Practice Exercises**  
1. Convert kilometers to meters
    ```python
    km = float(input("Enter distance in kilometers: "))
    print("Meters:", km * 1000)
    ```
2. Find the square of a number (Գտնել թվի քառակուսին)
    ```python
    num = float(input("Enter a number: "))
    print("Square:", num ** 2)
    ```
3. Check if a number is odd (Ստուգեք, թե արդյոք թիվը կենտ է)
    ```python
    num = int(input("Enter a number: "))
    print("Odd?", num % 2 != 0)
    ```
4. Find the perimeter of a square (Գտեք քառակուսու պարագիծը)
    ```python
    side = float(input("Enter side length: "))
    print("Perimeter:", side * 4)
    ```
5. Check result
    ```python
    number = float(input("Enter a number: "))
    print(number > 100)
    ```



---

# Exercise

## 🧩 Simple Calculator

> * Այնպես արեք որ վերջում տպելուց a-ի և b֊ի տեղերը փոխվեն։
> * Այսինքն վերջում a-ն դառնա 10 իսկ b֊ն դառնա 5։
> * Կոդը գրում ենք **"START CODE"** և **END CODE** հատվածում։
> * Չենք փորձում թիվ գրել, ունեք միայն ավել **c** փոփոխականը որը պետք փորձենք խնդիրը լուծել։

```python

a = 5
b = 10

# START CODE

# END CODE

print("a:", a)  # 10
print("b:", b)  # 5

```

<details> <summary>💡 Solution</summary>

```python

a = 5
b = 10

c = a
a = b
b = c

print("a:", a)
print("b:", b)

```

</details>



## 1. Double Length 🔠

Հարցրու անունը։ Տպիր նրա երկարության կրկնապատիկը։

## 2. Password Checker 🔑

Հարցրու գաղտնաբառ։ Տպիր արդյոք նրա երկարությունը մեծ է 8-ից։ (True/False)


## 3. Word Comparison 🆚

Հարցրու երկու բառ։ Տպիր արդյոք նրանք հավասար են (==)։(True/False)

## 4. Letter Count Equality 🔄

Հարցրու երկու անուն։ Տպիր արդյոք նրանց տառերի քանակները հավասար են։


## 5. Round Float 🔢

Հարցրու ամբողջով թիվ։ Տպիր այն 2 թվանշանի ճշգրտությամբ round()-ով։


## 6. Name vs Age Length 🔠🔢

Հարցրու անուն և տարիքը։ Տպիր արդյոք անունի տառերի քանակը հավասար է տարիքի թվին։


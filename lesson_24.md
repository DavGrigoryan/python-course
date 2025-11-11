<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 24 — Sorting Algorithms (Սորտավորման ալգորիթմներ)

Սորտավորել նշանակում է ինչ-որ բաներ դասավորել ճիշտ հերթականությամբ։  
Օրինակ՝ փոքրից մեծ կամ այբբենական կարգով։

Օրինակ

Պատկերացրու, որ ունես այս թվերը՝

```text
[5, 2, 9, 1, 3]
```

Ու ուզում ես դրանք դասավորես փոքրից մեծ՝

```text
[1, 2, 3, 5, 9]
```

Սրա համար կան տարբեր ձևեր։ Եկ տեսնենք 4 հետաքրքիր սորտավորման տարբերակ 👇

---

### ✳️ Selection Sort — «Գտիր ամենափոքրը»

**Ինչպես է աշխատում՝**

Դու նայում ես բոլոր թվերին, գտնում ես ամենափոքրը և դնում ես առաջին տեղում։  
Հետո նորից գտնում ես հաջորդ ամենափոքրը ու դնում ես երկրորդ տեղում։  
Այսպես՝ մինչև բոլորը լինեն իրենց տեղում։

```python
def selection_sort(numbers):
    for i in range(len(numbers)):
        min_index = i
        for j in range(i + 1, len(numbers)):
            if numbers[j] < numbers[min_index]:
                min_index = j
        numbers[i], numbers[min_index] = numbers[min_index], numbers[i]
    return numbers


print(selection_sort([5, 2, 9, 1, 3]))
```

### ✳️ Insertion Sort — «Դնեմ ճիշտ տեղում»

**Ինչպես է աշխատում՝**

Պատկերացրու՝ խաղում ես քարտերով։  
Ամեն անգամ վերցնում ես նոր քարտ և դնում ես այն ճիշտ տեղում, այնպես որ քարտերը մնան կարգով։

```python
def insertion_sort(numbers):
    for i in range(1, len(numbers)):
        key = numbers[i]
        j = i - 1
        while j >= 0 and key < numbers[j]:
            numbers[j + 1] = numbers[j]
            j -= 1
        numbers[j + 1] = key
    return numbers


print(insertion_sort([7, 4, 5, 2]))
```

### ✳️ Merge Sort — «Թիմային աշխատանք»

**Ինչպես է աշխատում՝**

1. Բաժանիր թվերը երկու մասի։
2. Ամեն կեսը առանձին սորտավորիր։
3. Հետո միացրու այդ երկու սորտավորված մասերը միասին։

```python
def merge_sort(numbers):
    if len(numbers) <= 1:
        return numbers

    middle = len(numbers) // 2
    left = merge_sort(numbers[:middle])
    right = merge_sort(numbers[middle:])

    return merge(left, right)


def merge(left, right):
    sorted_list = []
    while left and right:
        if left[0] < right[0]:
            sorted_list.append(left.pop(0))
        else:
            sorted_list.append(right.pop(0))
    sorted_list += left + right
    return sorted_list


print(merge_sort([38, 27, 43, 3, 9, 82, 10]))
```

### ✳️ Quick Sort — «Ընտրիր առաջնորդին»

**Ինչպես է աշխատում՝**

1. Ընտրիր մի թիվ՝ որպես առաջնորդ (pivot)։
2. Բոլոր փոքր թվերը դիր ձախ կողմում, իսկ մեծերը՝ աջ կողմում։
3. Ապա նույնը արա երկու կողմերի համար էլ։  
   Ահա թե ինչու է այն կոչվում “Quick” — արագ է անում։

```python
def quick_sort(numbers):
    if len(numbers) <= 1:
        return numbers

    length = len(numbers)

    # Եթե զույգ է, վերցնում ենք ձախ կողմի մեջտեղի էլեմենտը
    mid_index = length // 2

    pivot = numbers[mid_index]

    smaller = []
    bigger = []

    # անցնում ենք բոլոր էլեմենտներով բացի pivot-ից
    for i, x in enumerate(numbers):
        if i == mid_index:
            continue  # բաց ենք թողնում pivot-ը
        if x <= pivot:
            smaller.append(x)
        else:
            bigger.append(x)

    return quick_sort(smaller) + [pivot] + quick_sort(bigger)


print(quick_sort([8, 4, 3, 1, 6, 5, 7, 11, 9, 2, 10]))
```

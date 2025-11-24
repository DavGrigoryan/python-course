<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

## 🧩 Lesson 29 – File Handling (Ֆայլերի հետ աշխատանք)

Այս թեմայով կսովորենք, թե ինչպես ստեղծել(create), բացել(open), կարդալ(read), գրել(write), թարմացնել(update) և ջնջել(
delete) ֆայլեր Python-ում։

---

### ✳️ Opening Files (open())

```python
f = open("banastexts.txt", "a")
f.write("Es im anush Hayastani")
f.close()
```

Modes

- `"a"` → append, create if not exists
- `"w"` → write, overwrite if exists
- `"r"` → read, error if file doesn't exist
- `"x"` → creates a new file, error if the file already exists

---

### ✳️ Using with (BEST PRACTICE)

```python
with open('banastexts.txt', 'a') as f:
    f.write("Es im anush Hayastani\n")

print("Text has been added.")
```

✔ File closes automatically  
✔ No need to call close()

### ✳️ Reading Files

```python
f = open('banastexts.txt', 'r')
print(f.read())
f.close()
```

---

### ✳️ Creating or Rewriting Files — "w"

```python
f = open('banastexts.txt', 'w')
f.write("hajox dzez")
f.close()
```

**⚠ "w" deletes old content!**

---

### ✳️ "x" – Exclusive Creation Mode

- Creates a new file, but only if it does NOT already exist.
- If the file already exists → Python raises a FileExistsError.
- Useful for preventing accidental overwriting.

```python
try:
    with open("data.txt", "x") as f:
        f.write("New file created!")
except FileExistsError:
    print("File already exists!")
```

---

### ✳️ Append Without Deleting — `"a"`

```python
with open('hayastan.txt', 'a') as f:
    f.write(" barev dzez")
```

---

### ✳️ Deleting Files — os.remove()

```python
import os

os.remove('banastexts.txt')
```

---

### ✳️ Creating Directories with os

```python
import os

path = f"{os.getcwd()}/fayler"
os.mkdir(path)
```

---

### ✳️ File Not Found Handling

```python
try:
    with open("myfolder12.txt") as fil:
        print("my password is", fil.read())
except FileNotFoundError:
    password = input("my password: ")
    with open("myfolder.txt", "w") as fil:
        fil.write(password)
finally:
    print("Thanks")
```

---

### ✳️ Reading Words & Finding Longest Word

```python
with open("demofile.txt", "r") as fil:
    words = fil.read().split(" ")
    print(max(words, key=len))
```

---

### ✳️ Read 2 Files → Merge into 1

```python
with open("data1.txt", "r") as file:
    c1 = file.read()

with open("data2.txt", "r") as file2:
    c2 = file2.read()

merged = c1 + " " + c2

with open("merged.txt", "w") as out:
    out.write(merged)

print("merged !!!")
```

---

### ✳️ Longest & Shortest Line in File

`readlines()` reads all lines from a file and returns them as a list of strings.

```python
with open("data.txt", "r") as f:
    lines = f.readlines()

longest = max(lines, key=len)
shortest = min(lines, key=len)

print("Longest line:", longest.strip(), "Length:", len(longest))
print("Shortest line:", shortest.strip(), "Length:", len(shortest))
```

---

### ✳️ Replace All Vowels With "#"

```python
vowels = "aeiouAEIOU"

with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()

for v in vowels:
    content = content.replace(v, "#")

with open("data.txt", "w", encoding="utf-8") as file:
    file.write(content)
```

---

### ✳️ Rename Files

```python
import os

old_name = "data.txt"
new_name = "newdata.txt"

if os.path.exists(old_name):
    os.rename(old_name, new_name)
    print(f"File renamed to {new_name}")
else:
    print("File does not exist!")
```

---

## Exercises

### ✳️ Exercise 1 — Create a file

Գրեք Python ծրագիր, որը կստեղծի նոր ֆայլ example1.txt և գրի մեջը "Hello Python"։

---

### ✳️ Exercise 2 — Append text

Գրեք "Hello Again" տեքստը նույն ֆայլին՝ առանց հին տեքստը ջնջելու։

---

### ✳️ Exercise 3 — Read file content

Կարդացեք ֆայլի ամբողջ պարունակությունը և տպեք այն։

---

### ✳️ Exercise 4 — Read lines separately

Կարդացեք բոլոր տողերը readlines()–ով և տպեք list-ով։

---

### ✳️ Exercise 5 — Exclusive file creation

Ստեղծեք ֆայլ "unique.txt" միայն եթե այն դեռ գոյություն չունի, հակառակ դեպքում տպեք "File exists!"։

---

### ✳️ Exercise 6 — Delete a file

Ջնջեք unique.txt ֆայլը, եթե այն գոյություն ունի։

---

### ✳️ Exercise 7 — Create directory

Ստեղծեք նոր թղթապանակ myfolder ծրագրի ընթացիկ working directory-ում։

### ✳️ Exercise 8 — File not found handling

Փորձեք կարդալ ֆայլը "password.txt"։ Եթե չկա՝ հարցրեք օգտատիրոջը գաղտնաբառը և գրեք ֆայլում։

---

### ✳️ Exercise 9 — Merge two files

Կարդացեք "file1.txt" և "file2.txt" և միացրեք պարունակությունը "merged.txt"–ում։

---

### ✳️ Exercise 10 — Replace vowels

ֆաիլի մեջ գտնել բոլոր ձայնավորները և փոխել `"#"`֊ով

---

### ✳️ Exercise 11 — Rename file

Փոխեք ֆայլի անունը "data.txt" → "newdata.txt"։

---

### ✳️ Exercise 12 — Count lines

Հաշվեք, թե քանի տող կա "example1.txt"–ում։

---

### ✳️ Exercise 13 — Count words

Հաշվեք բառերի քանակը "example1.txt"–ում։

---

### ✳️ Exercise 14 — Read first 5 lines

Կարդացեք "example1.txt"–ի առաջին 5 տողերը։

---


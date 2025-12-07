<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 🧩 Lesson 35 – Object-Oriented Programming (OOP) – Part 6

## OOP 4 Principles

- INHERITANCE
- ENCAPSULATION
- ABSTRACTION
- POLYMORPHISM

---

# Exercise 1

## Դպրոցների կառավարման պարզ համակարգ (ընդհանուր OOP֊ի բոլոր թեմաների անփոփում)

### Պետք է գրել փոքր ծրագրի մոդել, որը կառավարվում է հետևյալ տրամաբանությամբ․

- Ծրագիրը կարող է ունենալ շատ դպրոցներ։
- Յուրաքանչյուր դպրոց կարող է ունենալ շատ դասարաններ։
- Յուրաքանչյուր դասարան կարող է ունենալ շատ աշակերտներ (պահվում են list-ում)։
- Պետք է լինի հնարավորություն՝
    - աշակերտ **ավելացնել** դասարան
    - աշակերտ **հեռացնել** դասարանից
    - ցուցադրել դպրոցների, դասարանների և աշակերտների ցանկը։

Այս խնդրի մեջ պետք է օգտագործել OOP-ի հետևյալ գաղափարները՝

- Աբստրակցիա (Abstraction) – բազային աբստրակտ class-եր
- Ժառանգականություն (Inheritance) – ընդհանուր Person → Student, Teacher
- Կապսուլա (Encapsulation) – private դաշտեր, getter/setter
- Բազմաձևություն (Polymorphism) – տարբեր դասեր, որոնք ունեն նույն մեթոդը, բայց տարբեր իրականացում

---

### Մաս 1․ Աշխատողների և աշակերտների մոդել

1. Ստեղծեք `Person` անունով **աբստրակտ class** (`ABC`-ից ժառանգված)․
    - attributes՝ `name`, `age`
    - abstract method՝ `introduce()` → ոչինչ չի իրականացնում (`pass`)
2. Ստեղծեք `Student` class, որը ժառանգում է `Person`-ից․
    - լրացուցիչ attribute՝ `grade` (օր․՝ «5A», «7Բ»)
    - private դաշտ՝ `__average_score` (միջին առաջադիմություն)
    - մեթոդներ՝
        - `set_average_score(score)` → թույլատրել միայն 0-ից 100 արժեք
        - `get_average_score()`
        - `introduce()` → override անի ծնողի մեթոդը և տպի օրինակ
          `"I'm <name>, <age> years old student from <grade> class."`
3. Ստեղծեք `Teacher` class, որը նույնպես ժառանգում է `Person`-ից․
    - լրացուցիչ attribute՝ subject (օր․՝ "Math", "History")
    - override անի `introduce()`՝ օրինակ `"I'm <name>, <age> years old teacher of <subject>."`

---

### Մաս 2․ Դասարանների մոդել

1. Ստեղծեք `Classroom` class, որը ներկայացնում է մեկ դասարան․
    - attributes
        - `name` (օր․՝ "5A")
        - private դաշտ `__students` → աշակերտների `list` (Student օբյեկտներ)
    - methods՝
        - `add_student(student)`
            - ստուգի, որ `student`-ը `Student` տիպի օբյեկտ է
            - ավելացնի նրան `__students` list-ի մեջ
        - `remove_student(student_name)`
            - հեռացնի աշակերտին ըստ անունի (եթե չկա՝ տպի հաղորդագրություն)
        - `list_students()`
            - տպի բոլոր աշակերտների անունները և `grade`-ը

---

### Մաս 3․ Դպրոցի մոդել (Abstraction + Inheritance)

1. Ստեղծեք BaseSchool անունով աբստրակտ class.
    - attributes
        - `name` – դպրոցի անունը
        - protected `_classrooms` – list, որտեղ կպահվեն դասարանների օբյեկտները
    - methods
        - abstract methods՝
            - `add_classroom(classroom)`
            - `remove_classroom(class_name)`
        - կոնկրետ method՝
            - `list_classrooms()` → տպի դպրոցում գրանցված դասարանների անունները
2. Ստեղծեք `School` class, որը ժառանգում է `BaseSchool`-ից և իրականացնում է դրա աբստրակտ մեթոդները․

- `add_classroom(classroom)`
    - ավելացնում է դասարանը `_classrooms` list-ի մեջ
- `remove_classroom(class_name)`
    - հեռացնում է դասարանը ըստ նրա անվան
- `find_classroom(class_name)`
    - վերադարձնի համապատասխան `Classroom` օբյեկտը կամ `None`

---

### Մաս 4․ Օգտագործում

1. Ստեղծեք մի քանի դպրոց՝
    - School 1՝ `"RSoft High School"`
    - School 2՝ `"RSoft Primary School"`

2. Յուրաքանչյուր դպրոցում ստեղծեք մի քանի դասարան՝ օրինակ
    - `"5A"`, `"7B"` Առաջին դպրոցում
    - `"3A"`, `"4A"` Երկրորդ դպրոցում
3. Յուրաքանչյուր դասարանում ստեղծեք մի քանի աշակերտ և ավելացրեք add_student-ով։
4. Ցուցադրեք`
    - դպրոցների դասարանների ցանկը
    - ամեն դասարանի մեջ գրանցված աշակերտների ցանկը
5. Փորձեք նաև`
    - հեռացնել մեկ աշակերտ
    - հեռացնել մեկ դասարան
    - և նորից տպել վիճակը

<details> <summary>💡 Solution</summary>

```python
from abc import ABC, abstractmethod


# -------- Մաս 1․ Person, Student, Teacher --------

class Person(ABC):
    def __init__(self, name: str, age: int):
        self.name = name
        self.age = age

    @abstractmethod
    def introduce(self):
        pass


class Student(Person):
    def __init__(self, name: str, age: int, grade: str):
        super().__init__(name, age)
        self.grade = grade
        self.__average_score = None  # private

    def set_average_score(self, score: float):
        if 0 <= score <= 100:
            self.__average_score = score
        else:
            print("Average score must be between 0 and 100.")

    def get_average_score(self):
        return self.__average_score

    def introduce(self):
        print(
            f"I'm {self.name}, {self.age} years old student from {self.grade} class."
        )


class Teacher(Person):
    def __init__(self, name: str, age: int, subject: str):
        super().__init__(name, age)
        self.subject = subject

    def introduce(self):
        print(
            f"I'm {self.name}, {self.age} years old teacher of {self.subject}."
        )


# -------- Մաս 2․ Classroom --------

class Classroom:
    def __init__(self, name: str):
        self.name = name
        self.__students: list[Student] = []  # private list

    def add_student(self, student: Student):
        if not isinstance(student, Student):
            print("Only Student objects can be added.")
            return

        self.__students.append(student)
        print(f"Student {student.name} added to class {self.name}.")

    def remove_student(self, student_name: str):
        for s in self.__students:
            if s.name == student_name:
                self.__students.remove(s)
                print(f"Student {student_name} removed from class {self.name}.")
                break
        else:
            print(f"Student {student_name} not found in class {self.name}.")

    def list_students(self):
        if not self.__students:
            print(f"Class {self.name} has no students.")
            return

        print(f"Students in class {self.name}:")
        for s in self.__students:
            print(f"  - {s.name} ({s.grade})")

    def count_students(self):
        return len(self.__students)


# -------- Մաս 3․ BaseSchool (Abstract) և School --------

class BaseSchool(ABC):
    def __init__(self, name: str):
        self.name = name
        self._classrooms: list[Classroom] = []

    @abstractmethod
    def add_classroom(self, classroom: Classroom):
        pass

    @abstractmethod
    def remove_classroom(self, class_name: str):
        pass

    def list_classrooms(self):
        if not self._classrooms:
            print(f"School '{self.name}' has no classrooms yet.")
            return

        print(f"Classrooms in school '{self.name}':")
        for c in self._classrooms:
            print(f"  - {c.name}")

    def find_classroom(self, class_name: str) -> Classroom | None:
        for c in self._classrooms:
            if c.name == class_name:
                return c
        return None


class School(BaseSchool):
    def add_classroom(self, classroom: Classroom):
        if self.find_classroom(classroom.name):
            print(f"Class {classroom.name} already exists in school '{self.name}'.")
            return

        self._classrooms.append(classroom)
        print(f"Class {classroom.name} added to school '{self.name}'.")

    def remove_classroom(self, class_name: str):
        classroom = self.find_classroom(class_name)
        if classroom:
            self._classrooms.remove(classroom)
            print(f"Class {class_name} removed from school '{self.name}'.")
        else:
            print(f"Class {class_name} not found in school '{self.name}'.")


# -------- Մաս 4․ Օգտագործման օրինակ --------


# Ստեղծում ենք երկու դպրոց
school1 = School("RSoft High School")
school2 = School("RSoft Primary School")

# Դասարաններ առաջին դպրոցում
class_5a = Classroom("5A")
class_7b = Classroom("7B")

school1.add_classroom(class_5a)
school1.add_classroom(class_7b)

# Դասարաններ երկրորդ դպրոցում
class_3a = Classroom("3A")
class_4a = Classroom("4A")

school2.add_classroom(class_3a)
school2.add_classroom(class_4a)

# Աշակերտներ
s1 = Student("Anna", 12, "5A")
s1.set_average_score(89)

s2 = Student("Petros", 13, "5A")
s2.set_average_score(76)

s3 = Student("Mariam", 14, "7B")
s3.set_average_score(92)

# Ավելացնում ենք աշակերտներին համապատասխան դասարաններ
class_5a.add_student(s1)
class_5a.add_student(s2)
class_7b.add_student(s3)

# Տպում ենք դպրոցների դասարանները
print("\n--- School 1 ---")
school1.list_classrooms()

print("\n--- School 2 ---")
school2.list_classrooms()

# Տպում ենք դասարանների աշակերտների ցուցակը
print("\n--- Students in each classroom (School 1) ---")
class_5a.list_students()
class_7b.list_students()

# Պոլիմորֆիզմի օրինակ (Person → Student, Teacher)
print("\n--- Polymorphism demo ---")
t1 = Teacher("Arman", 35, "Math")

people: list[Person] = [s1, s3, t1]
for p in people:
    p.introduce()

# Հեռացնում ենք աշակերտին դասարանից
print("\n--- Remove student ---")
class_5a.remove_student("Petros")
class_5a.list_students()

# Հեռացնում ենք դասարանը դպրոցից
print("\n--- Remove classroom ---")
school1.remove_classroom("7B")
school1.list_classrooms()

```

</details>





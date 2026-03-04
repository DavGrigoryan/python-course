<h1 align="center" style="color:#2E86C1;">R'SOFT</h1>
<p align="center" style="color:#2E86C1; font-size:20px;">Web Development Company</p>

---

# 📘 Lesson 7:

link to presentation: https://www.canva.com/design/DAFy9A0mNeQ/4inxkvYEJqgzKV7VDhC9Vg/edit

---

# Exercise

Voting Eligibility 🗳️

- Հարցրու տարիքը։
- Եթե <16 → “Not allowed”,
- 16–17 → “With permission”,
- ≥18 → “Allowed to vote”։

---

Letter Case Detector 🔡🔠

- Հարցրու բառ։
- Եթե բոլոր տառերը մեծատառ են → “UPPERCASE”,
- եթե փոքրատառ են → “lowercase”,
- եթե խառը են → “Mixed”։

---

School Shift 🏫

- Հարցրու ժամը։
- Եթե <12 → “Morning classes”,
- եթե 12–17 → “Day classes”,
- ≥17 → “Evening classes”։

---

Discount Card 🛒

- Հարցնել գումարի թիվը,
- հարցնել արդյոք զեղչ ունի թե ոչ
- եթե (գումար ≥10000 դրամը կամ ունի bonus card) → “Discount applied”,
- հակառակ դեպքում՝ “Discount not applied”։

---

Cinema Combo 🎥

- Հարցնել տարիքը
- տոմսի արժեքը 5000 դրամ է
- Եթե (տարիք <12 կամ տարիքը >60) → “Half price ticket։ 2500 AMD”,
- հակառակ դեպքում “Full ticket: 5000 AMD”

---

Sports Access ⚽

- Հարցնել տարիքը
- Հարցնել արդյոք անցել է medical check֊ը
- Եթե (տարիք ≥16 և ունի medical check) → “Can play in team”։

---

Email Rule 📧

- Email֊ի երկարությունը ≥6 և պարունակում է “@” → “Valid email”։
- հակառակ դեպքում “Invalid email”

---

Nested Age Category 👶👧👨

- Եթե age =0 → "The baby is not born yet"
- եթե age >0 կամ age ≤120 → nested if–ով բաժանիր Baby/Child/Teen/Adult/Senior։
- հակառակ դեպքում → “Please enter a valid age.”

---

Coffee Machine ☕

- Հարցրու չափ (S/M/L) և շաքար (yes/no)։
- Հաշվիր գինը և տպիր “You must pay: X amount”։
- S չափսիր արժեքը՝ 300 դրամ է
- M չափսիր արժեքը՝ 500 դրամ է
- L չափսիր արժեքը՝ 750 դրամ է
- Շաքարավազը հավելյալ 50 դրամ է S և M չափի համար, իսկ L֊ի դեպքում անվճար է

---

📝 Registration Validation Task

Գրիր ծրագիր, որը հարցնում է օգտագործողից․

1. Անուն (name)
    - Պետք է լինի ավելի երկար քան 2 տառ
    - Պետք է լինի ավելի կարճ քան 100 տառ

2. Էլ․ փոստ (email)
    - Պետք է լինի ավելի երկար քան 6 նիշ
    - Պետք է լինի ավելի կարճ քան 5000 նիշ
    - Պետք է իր մեջ պարտադիր պարունակի @ և . նշանները

3. Գաղտնաբառ (password)
    - Պետք է լինի ավելի երկար քան 8 նիշ
    - Պետք է լինի ավելի կարճ քան 1,000,000 նիշ

4. Կրկնել գաղտնաբառը (confirm password)
    - Պետք է համընկնի password–ի հետ

✅ Ծրագրի արդյունք

- Եթե բոլոր պայմանները ճիշտ են → Տպի Registration successful!
- Եթե որևէ պայման խախտվում է → Տպի համապատասխան սխալի հաղորդագրություն

```yaml
Enter name: A
❌ Error: Name must be between 2 and 100 characters.

Enter name: Ani
Enter email: aniemail.com
❌ Error: Email must contain '@' and '.'

Enter name: Ani
Enter email: ani@mail.com
Enter password: 12345
❌ Error: Password must be between 9 and 999999 characters.

Enter name: Ani
Enter email: ani@mail.com
Enter password: mypassword123
Enter confirm password: mypassword123

✅ Registration successful!
```
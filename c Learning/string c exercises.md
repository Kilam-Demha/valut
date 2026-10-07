آه، بما أنك باغي **تتمرن مزيان على String قبل ما تدخل لـ Pointer**، أنا ما نعطيكش دابا `strcpy()` و `strcmp()` مباشرة. نبنيو المهارة بالتدريج: **char → array → string → traversal → modification → input → `<string.h>`**.

وما غاديش نعطيك الحلول. 👌

## 🟢 Level 1 — فهم String

### Exercice 1 — Characters

كتب برنامج كيعرّف:

```
char word[] = "Programming";
```

وطبع كل character بوحدو باستعمال `for`.

**ممنوع `%s`.**

الهدف: تفهم أن String هي sequence ديال `char`.

---

### Exercice 2 — Index

عندك:

```
char word[] = "Computer";
```

طبع:

- أول character
- آخر character
- character الموجود فـ index `3`
- طول الـ string

**ممنوع `strlen()`** فهاد التمرين.

---

### Exercice 3 — عدّ الحروف

عندك:

```
char str[] = "Hello World";
```

حسب عدد الـ characters باستعمال loop.

⚠️ ما تحسبش `'\0'`.

---

## 🟡 Level 2 — Traversal

### Exercice 4 — عدّ نوع معين

برنامج ياخذ String ويحسب شحال فيها من:

```
'a'
```

مثلاً:

```
Input:  banana
Output: 3
```

---

### Exercice 5 — Vowels

حسب عدد:

```
a e i o u
```

داخل String.

مثلاً:

```
Input: Ahmed
Output: 2
```

---

### Exercice 6 — Uppercase / Lowercase

عندك String:

```
hello world
```

حوّلها إلى:

```
HELLO WORLD
```

وبالعكس:

```
HELLO WORLD
```

تصبح:

```
hello world
```

حاول تفهم ASCII مزيان هنا.

---

## 🟠 Level 3 — Modification

### Exercice 7 — Replace

عندك:

```
hello world
```

بدّل كل:

```
'o'
```

بـ:

```
'0'
```

النتيجة:

```
hell0 w0rld
```

---

### Exercice 8 — Reverse

عندك:

```
Ahmed
```

حولها إلى:

```
demhA
```

⚠️ ما تستعملش `strrev()`.

---

### Exercice 9 — Remove spaces

عندك:

```
"hello world from C"
```

خرج:

```
"helloworldfromC"
```

هنا غادي تبدأ تفكر مزيان فـ **read position / write position**.

---

# 🔴 Level 4 — Algorithms

### Exercice 10 — Palindrome

تحقق واش String palindrome.

أمثلة:

```
madam  → YES
level  → YES
hello  → NO
```

---

### Exercice 11 — Frequency

عندك:

```
"programming"
```

حسب شحال تكرر كل character.

مثلاً:

```
g → 2
r → 2
m → 2
...
```

حاول ما تستعملش `string.h`.

---

### Exercice 12 — Most frequent character

من String، وجد character اللي تكرر أكثر مرة.

مثلاً:

```
Input: programming
Output: g
```

---

# 🟣 Level 5 — String operations

هنا غادي نبدأو نحاكو functions ديال `<string.h>` ولكن **حنا اللي غادي نبنيو algorithms**.

### Exercice 13

صايب function ديالك:

```
int my_strlen(char str[]);
```

كترد length ديال String.

**ممنوع `strlen()`.**

---

### Exercice 14

صايب:

```
void my_strcpy(char dest[], char src[]);
```

كتنسخ String من `src` لـ `dest`.

**ممنوع `strcpy()`.**

---

### Exercice 15

صايب:

```
int my_strcmp(char str1[], char str2[]);
```

خاصها تقارن جوج Strings.

**ممنوع `strcmp()`.**

---

### Exercice 16

صايب:

```
void my_strcat(char dest[], char src[]);
```

تلصق `src` فآخر `dest`.

**ممنوع `strcat()`.**

---

# 🧠 Level 6 — Pro Challenge

من بعد هادشي:

### Exercice 17 — Word Counter

Input:

```
"I am learning C programming"
```

Output:

```
5 words
```

---

### Exercice 18 — Longest word

Input:

```
"I am learning data structures"
```

Output:

```
structures
```

---

### Exercice 19 — Remove duplicate characters

مثلاً:

```
programming
```

تحاول تخرج String بلا characters مكررين.

---

### Exercice 20 — Mini String Library 🔥

دير ملف:

```
my_string.h
my_string.c
main.c
```

وتبني فيه functions ديالك:

```
my_strlen()
my_strcpy()
my_strcmp()
my_strcat()
my_strchr()
```

ومن بعد تستعملهم من `main.c`.

هنا غادي تربط **String + Functions + Header + Source + Compilation + Linker**.

---

## 🎯 ولكن بالنسبة ليك دابا

ما تديرش 20 كاملين دفعة وحدة.

دير:

```
1 → 2 → 3 → 4 → 5
```

ومن بعد:

```
6 → 7 → 8 → 9 → 10
```

ومن بعد ندوزو للـ **String algorithms**.

**وأنا غادي نعطيك غير تمرين واحد فكل مرحلة، بلا solution حتى تجرب أنت**؛ إلا بغيتي correction، صيفط ليا code ديالك ونصححو بالمنطق ديالو.
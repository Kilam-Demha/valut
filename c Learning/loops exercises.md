
tkdar t3tini tamarin fi loops kamlin

آه، نقدر. وبما أنك باغي تقوّي **logic ديال loops**، نخليو التركيز دابا على:

- `for`
- `while`
- `do while`
- `if / else`
- `break`
- `continue`
- loops داخل loops
- arrays + loops
- functions + loops

وبلا pointers و `struct` دابا.

غادي نعطيك **25 تمرين** من الساهل حتى لـ mini-projects، ولكن **بلا solutions**.

---

# 🟢 Level 1 — أساسيات الـ loops

### 1. طبع من 1 حتى N

المستخدم يدخل:

```
N = 10
```

النتيجة:

```
1 2 3 4 5 6 7 8 9 10
```

استعمل `for`.

---

### 2. طبع من N حتى 1

```
N = 5
```

النتيجة:

```
5 4 3 2 1
```

---

### 3. الأعداد الزوجية

طبع جميع الأعداد الزوجية من `1` حتى `N`.

```
N = 10

2 4 6 8 10
```

---

### 4. مجموع الأعداد

حسب:

```
1 + 2 + 3 + ... + N
```

مثلاً:

```
N = 5
```

النتيجة:

```
15
```

---

### 5. Factorial

احسب:

```
5! = 5 × 4 × 3 × 2 × 1
```

النتيجة:

```
120
```

دير:

```
int factorial(int n);
```

---

# 🟡 Level 2 — Conditions داخل loops

### 6. Count digits

المستخدم يدخل:

```
58321
```

خاصك تعرف عدد الأرقام:

```
5
```

مثلاً:

```
100 → 3 digits
7 → 1 digit
```

استعمل `while`.

---

### 7. Sum digits

```
58321
```

النتيجة:

```
5 + 8 + 3 + 2 + 1 = 19
```

---

### 8. Reverse number

```
Input: 12345
Output: 54321
```

استعمل `while`.

---

### 9. Palindrome number

كتب:

```
int isPalindrome(int n);
```

مثلاً:

```
121 → 1
123 → 0
1221 → 1
```

الفكرة: الرقم من اليمين لليسار خاصو يكون نفسو.

---

### 10. أكبر digit

```
Input: 58321
```

النتيجة:

```
8
```

---

# 🟠 Level 3 — Logic ديال loops

### 11. Prime Number

كتب:

```
int isPrime(int n);
```

مثلاً:

```
7  → 1
13 → 1
10 → 0
1  → 0
```

**مهم:** فكر شحال من مرة فعلاً خاصك تدور فـ loop.

---

### 12. طبع جميع Prime numbers

المستخدم يدخل:

```
N = 20
```

النتيجة:

```
2 3 5 7 11 13 17 19
```

هنا عندك **loop داخل loop**.

---

### 13. GCD

مثلاً:

```
A = 24
B = 18
```

النتيجة:

```
6
```

دير:

```
int gcd(int a, int b);
```

حاول تلقى algorithm ديالك باستعمال loops.

---

### 14. Count divisors

```
N = 12
```

divisors:

```
1 2 3 4 6 12
```

النتيجة:

```
6
```

دير:

```
int countDivisors(int n);
```

---

### 15. Perfect Number

العدد perfect إلا كان مجموع divisors ديالو **بدون العدد نفسه** كيساوي العدد.

مثلاً:

```
6
```

divisors:

```
1 + 2 + 3 = 6
```

إذن:

```
6 → Perfect
```

دير:

```
int isPerfect(int n);
```

---

# 🔵 Level 4 — Nested Loops

### 16. Rectangle

المستخدم يدخل:

```
rows = 4
cols = 6
```

طبع:

```
******
******
******
******
```

استعمل nested loops.

---

### 17. Triangle

```
*
**
***
****
*****
```

---

### 18. Number Triangle

```
1
12
123
1234
12345
```

---

### 19. Multiplication Table

إلى `10`:

```
1 x 1 = 1
1 x 2 = 2
...
10 x 10 = 100
```

هنا nested loops.

---

### 20. Prime Triangle

مثلاً أول 5 primes:

```
2
3 5
7 11 13
17 19 23 29
31 37 41 43 47
```

**هاد واحد خليه للتحدي.**

---

# 🔴 Level 5 — Arrays + Loops

### 21. Array Analyzer

عندك:

```
int arr[10];
```

حسب:

```
sum
average
max
min
even count
odd count
```

ولكن حاول تقسّمها إلى functions:

```
int sumArray(...);
int maxArray(...);
int minArray(...);
int countEven(...);
```

---

### 22. Reverse Array

```
[1 2 3 4 5]
```

تصبح:

```
[5 4 3 2 1]
```

**ممنوع array ثانية.**

---

### 23. Search

كتب:

```
int find(int arr[], int size, int target);
```

مثلاً:

```
[4 8 2 9 5]

target = 9

return 3
```

إلا ما لقيتيه:

```
-1
```

---

### 24. Second Maximum

```
[10 5 20 8 15]
```

النتيجة:

```
15
```

ديرها بدون `sort`.

وزيد تعامل مع:

```
[10 20 20 5]
```

بحيث `20` ما تتحسبش كـ second maximum.

---

# 💀 Level 6 — Mini Projects

### 25. ATM كامل

هاد المرة جمع كلشي.

```
========== ATM ==========

1. Check Balance
2. Deposit
3. Withdraw
4. Transaction History
5. Exit
```

استعمل:

```
int balance;
int transactions[100];
int transactionCount;
```

مثلاً:

```
Deposit: 500
Withdraw: 200
Deposit: 100
```

history:

```
+500
-200
+100
```

والبرنامج خاصو يبقى خدام حتى المستخدم يختار:

```
5. Exit
```

يعني هنا غادي تستعمل:

```
do while
   +
switch
   +
if
   +
functions
   +
arrays
   +
loops
```

---

## 🧠 ولكن كاين Challenge مهم

من بعد ما تكمل 25، حاول تدير **Mini Project واحد من راسك**:

### 🔥 Student Grade Analyzer

```
Number of students: 5

Student 1: 14
Student 2: 8
Student 3: 17
Student 4: 12
Student 5: 6
```

البرنامج يعطي:

```
Average: 11.4
Highest: 17
Lowest: 6
Passed: 3
Failed: 2
```

وزيد menu:

```
1. Show all grades
2. Average
3. Highest
4. Lowest
5. Passed students
6. Failed students
7. Exit
```

**هاد المشروع بالضبط مناسب للمرحلة اللي نتا فيها دابا**: ما فيه لا pointers لا structs، ولكن فيه `functions + arrays + loops + conditions + logic` كاملين.
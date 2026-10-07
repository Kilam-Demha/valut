
أكيد. بما أنك باغي **تقوّي الـ Functions + Arrays + Logic + Conditions** وبلا ما ندخلو دابا لـ pointers و `struct`، نعطيك **20 تمرين بحال mini-projects صغار**، وكل واحد فيه مشكل خاصك تفكر فيه قبل الكود.

غادي نصعّد الصعوبة تدريجياً، وما نعطيكش الحلول دابا.

## 🟢 المستوى 1 — تثبيت الـ Functions + Arrays

### 1. نظام تحليل النقط

عندك:

```
int grades[10] = {12, 15, 8, 17, 10, 19, 7, 14, 16, 11};
```

دير functions:

```
float average(int arr[], int size);
int maxGrade(int arr[], int size);
int minGrade(int arr[], int size);
int countPassed(int arr[], int size);
```

القواعد:

- النجاح من `10` وفوق.
- حسب المعدل.
- حسب أكبر وأصغر نقطة.
- حسب عدد الناجحين.

**الهدف:** تقسيم problem كبير إلى functions صغار.

---

### 2. Number Analyzer

عندك array ديال أعداد صحيحة.

دير:

```
int countPositive(...)
int countNegative(...)
int countZero(...)
int countEven(...)
int countOdd(...)
```

مثلاً:

```
[-4, 0, 7, 8, -2, 11, 0]
```

البرنامج يعطيك:

```
Positive: 2
Negative: 2
Zero: 2
Even: 3
Odd: 2
```

---

### 3. ATM صغير

عندك:

```
int balance = 1000;
```

دير functions:

```
void deposit(...);
int withdraw(...);
void showBalance(...);
```

القواعد:

- deposit خاصو يكون `> 0`.
- withdraw ما يفوتش balance.
- ما تقبلش amount بـ `0` أو negative.

زيد menu:

```
1. Deposit
2. Withdraw
3. Balance
4. Exit
```

---

### 4. Search System

عندك:

```
int numbers[10];
```

كتب:

```
int findNumber(int arr[], int size, int target);
```

خاصها ترجع **index** ديال الرقم.

إلا ما لقاتوش:

```
-1
```

مثلاً:

```
[4, 8, 2, 9, 5]
target = 9

return 3
```

---

### 5. Temperature Analyzer

عندك temperatures ديال أسبوع:

```
[22, 25, 19, 31, 28, 17, 24]
```

دير functions باش تعرف:

- average
- highest
- lowest
- عدد الأيام فوق `25`
- واش كان شي يوم فوق `40`

مثلاً:

```
int hasExtremeTemperature(int arr[], int size);
```

ترجع `1` أو `0`.

---

# 🟡 المستوى 2 — Logic أقوى

### 6. Password Analyzer

عندك array ديال characters:

```
char password[] = "Ahmed123";
```

دير functions:

```
int hasDigit(char arr[]);
int hasUppercase(char arr[]);
int hasLowercase(char arr[]);
int isStrongPassword(char arr[]);
```

القواعد:

```
Strong =
digit + uppercase + lowercase + length >= 8
```

مثلاً:

```
Ahmed123 → Strong
ahmed123 → Weak
AHMED123 → Weak
Ahmedabc → Weak
```

---

### 7. Shopping Cart صغير

عندك:

```
float prices[10];
```

دير:

```
float totalPrice(...);
int countExpensiveItems(...);
float applyDiscount(...);
```

القواعد:

```
total >= 500 → 10% discount
total >= 1000 → 15%
otherwise → 0%
```

**التحدي:** ما تديرش discount إلا من بعد ما تحسب total.

---

### 8. Bank Transaction Analyzer

عندك:

```
int transactions[10] =
{
    500, -200, -50, 1000, -300, 200, -100
};
```

موجب = deposit  
سالب = withdrawal

دير:

```
int totalDeposits(...);
int totalWithdrawals(...);
int countWithdrawals(...);
int biggestWithdrawal(...);
```

وزيد:

```
int finalBalance(int initialBalance, int transactions[], int size);
```

---

### 9. Remove Duplicates

عندك:

```
[2, 5, 2, 7, 5, 9, 2]
```

خاصك توصل لـ:

```
[2, 5, 7, 9]
```

function:

```
int removeDuplicates(int arr[], int size);
```

وترجع:

```
4
```

**هنا غادي تستعمل array manipulation + nested loops + conditions.**

---

### 10. Reverse + Compare

عندك:

```
[1, 2, 3, 2, 1]
```

بغينا نعرفو واش array **Palindrome**.

```
int isPalindrome(int arr[], int size);
```

مثلاً:

```
[1,2,3,2,1] → 1
[1,2,3,4,5] → 0
```

**ممنوع تستعمل array ثانية.**

---

# 🟠 المستوى 3 — Mini Projects حقيقيين

### 11. Student Management بدون Struct

عندك:

```
int ids[10];
int grades[10];
```

كل index كيمثل student.

مثلاً:

```
ids:    101  102  103  104
grades: 15   8    17   12
```

دير:

```
int findStudent(int ids[], int size, int id);
int getGrade(...);
int isPassed(...);
```

Menu:

```
1. Search student
2. Show grade
3. Check pass
4. Show highest grade
5. Exit
```

هنا غادي تتعلم تربط **جوج arrays بنفس index**.

---

### 12. Inventory System

عندك:

```
int productIds[10];
int quantities[10];
```

مثلاً:

```
ID:       101  102  103
Quantity:  5    0    12
```

دير:

```
int findProduct(...);
int sellProduct(...);
int restockProduct(...);
int isAvailable(...);
```

القواعد:

```
quantity == 0 → Out of stock
quantity > 0  → Available
```

إلا بغينا نبيع `7` من product عندو `5`:

```
Not enough stock
```

---

### 13. Voting System

عندك votes:

```
[1, 2, 1, 3, 2, 1, 3, 2]
```

كل رقم candidate.

دير:

```
int countVotes(int votes[], int size, int candidate);
int findWinner(int votes[], int size);
int hasTie(...);
```

خاصك تفكر:

> كيفاش نحسب votes ديال كل candidate؟

وزيد حالة:

```
Candidate 1 → 3
Candidate 2 → 3
Candidate 3 → 2
```

هنا كاين **tie**.

---

### 14. Parking Lot

عندك:

```
int parking[10];
```

القيمة:

```
0 → empty
1 → occupied
```

دير:

```
int findFreeSpot(...);
int countFreeSpots(...);
int parkCar(...);
int removeCar(...);
```

مثلاً:

```
[1,1,0,1,0,0,1,1,1,0]
```

البرنامج يعرف أول place خاوية.

---

### 15. Game: Number Guessing

الـ secret number:

```
int secret = 47;
```

المستخدم عندو `5` محاولات.

function:

```
int checkGuess(int secret, int guess);
```

وترجع:

```
-1 → guess too low
 0 → correct
 1 → guess too high
```

مثلاً:

```
Guess: 30
Too low

Guess: 60
Too high

Guess: 47
You win!
```

---

# 🔴 المستوى 4 — Logic قوي

### 16. Mini CPU

عندك array ديال instructions:

```
[10, 20, 30, 40]
```

وعندك commands:

```
1 → ADD
2 → SUBTRACT
3 → MULTIPLY
4 → MAX
5 → MIN
```

دير:

```
int calculate(int arr[], int size, int operation);
```

مثلاً:

```
operation = 1

10 + 20 + 30 + 40 = 100
```

ولكن:

```
operation = 4
```

النتيجة:

```
40
```

---

### 17. Array Compression

عندك:

```
[1,1,1,2,2,3,3,3,3,4]
```

بغينا:

```
[1,2,3,4]
```

ولكن هاد المرة **غير العناصر المتتابعة المتكررة**.

مثلاً:

```
[1,1,2,1,1]
```

النتيجة:

```
[1,2,1]
```

ماشي:

```
[1,2]
```

function:

```
int compress(int arr[], int size);
```

وترجع new size.

---

### 18. Frequency Analyzer

عندك:

```
[2,3,2,5,3,2,7,5]
```

بغينا نعرفو frequency ديال كل رقم.

النتيجة المنطقية:

```
2 → 3 times
3 → 2 times
5 → 2 times
7 → 1 time
```

دير:

```
int countFrequency(int arr[], int size, int target);
```

ومن بعد استعملها داخل function أخرى.

**هنا غادي تبدأ تفهم علاش functions مفيدة: function كتستعمل function أخرى.**

---

### 19. Mini Login System

عندك users، ولكن بلا `struct`.

استعمل:

```
char usernames[5][20];
char passwords[5][20];
```

مثلاً:

```
Ahmed   1234
Ali     abc
Sara    xyz
```

دير:

```
int findUser(...);
int checkPassword(...);
int login(...);
```

المستخدم عندو 3 محاولات.

```
Username:
Password:

Login successful
```

أو:

```
Wrong password
Attempts remaining: 2
```

هنا غادي تجمع:

```
functions
+
arrays
+
strings
+
conditions
+
loops
+
logic
```

---

# 💀 المستوى 5 — Mini Project كبير

### 20. Mini Bank System

هاد واحد ديرو من بعد ما تكمل الباقي.

بلا `struct` وبلا pointers.

عندك:

```
int accountIds[10];
int balances[10];
int accountCount;
```

مثلاً:

```
ID:       1001  1002  1003
Balance:   500   1200   300
```

دير functions:

```
int findAccount(...);
int createAccount(...);
int deposit(...);
int withdraw(...);
int transfer(...);
void showAccount(...);
```

Menu:

```
========== BANK ==========

1. Create account
2. Deposit
3. Withdraw
4. Transfer
5. Check balance
6. Exit
```

### Rules

**Create:**

- ID ما يكونش موجود.
- balance initial ≥ 0.

**Deposit:**

- amount > 0.

**Withdraw:**

- amount > 0.
- amount <= balance.

**Transfer:**

مثلاً:

```
1001 → 1002
amount = 200
```

خاص:

```
1001 balance -= 200
1002 balance += 200
```

ولكن إلا ما كانش account أو balance ما كافيش:

```
Transfer failed
```

---

## 🧠 الطريقة اللي بغيتك تخدم بها

ما تبداش مباشرة بالكود.

قبل كل تمرين كتب فـ الورقة:

```
1. شنو المعطيات؟
2. شنو خاصني نرجع؟
3. شنو function اللي نحتاج؟
4. شنو conditions؟
5. شنو loops؟
6. شنو اللي غادي يتبدل فـ array؟
```

مثلاً تمرين `removeDuplicates`:

```
Input:
array + size

Output:
new size

Modification:
نبدل نفس array

Tools:
for
for
if
```

هاد الطريقة هي اللي غادي تبني عندك **logic ديال programmer**، ماشي غير حفظ syntax.

**وبالنسبة ليك دابا، بدا بـ 1 → 2 → 4 → 7 → 9 → 10، ومن بعد دخل للـ mini-projects 11–20.**
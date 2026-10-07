إييه آحمد، هادي هي الطريقة اللي بغيت نخدمو بها معاك. **ما غاديش نضيعو الوقت فـtutorials**. أنا نعطيك شنو خاصك تعرف اليوم، تعريف مختصر وواضح، ومن بعد **أنت تكتب الكود وتطبق**.

# 🟢 اليوم الأول — C Refresh

**المدة:** تقريباً 2 حتى 3 ساعات.  
**الهدف:** ماشي تعلم C كاملة. الهدف هو نرجعو يدك للكود ونشوفو شنو باقي فاكر وشنو خاصو refresh.

اليوم غادي نخدمو غير هادو:

```
1. Program structure
2. Variables
3. Data types
4. printf
5. scanf
6. Operators
7. if / else
8. for
9. while
10. Functions
```

ولكن ما غاديش نعطيك 10 tutorials. ها التعاريف ديالهم دابا.

---

## 1️⃣ Program structure

أي برنامج C بسيط كيكون عندو نقطة البداية:

```
#include <stdio.h>

int main(void)
{
    return 0;
}
```

### شنو كتعني؟

`#include <stdio.h>`

كتقول للـcompiler:  
**بغيت نستعمل الأدوات الموجودة فـstdio، بحال `printf` و`scanf`.**

`main()`

هي **نقطة البداية ديال البرنامج**. البرنامج كيبدا التنفيذ من هنا.

`return 0;`

كتعني أن البرنامج سالا بشكل عادي ونجح.

---

# 2️⃣ Variable

**Variable = بلاصة فـmemory كنخزنو فيها قيمة، وعندها اسم ونوع.**

مثلاً:

```
int age = 25;
```

عندك:

```
int  → النوع
age  → الاسم
25   → القيمة
```

مثال:

```
int age = 25;
float price = 19.5;
char grade = 'A';
```

---

# 3️⃣ Data Types

الـtype كيحدد **شنو نوع البيانات اللي غادي نخزنو وكيفاش غادي نتعاملو معاها**.

اليوم خاصك تعرف غير:

```
int
float
double
char
```

مثلاً:

```
int age = 25;
float temperature = 23.5;
double salary = 12345.75;
char grade = 'A';
```

ما تدخلش دابا فـ`long`, `short`, `unsigned`... نخليوهم من بعد.

---

# 4️⃣ printf

`printf` كتستعملها باش **تطبع معلومات فالـterminal**.

مثلاً:

```
printf("Hello\n");
```

باش تطبع variable:

```
int age = 25;

printf("Age = %d\n", age);
```

أهم formats اليوم:

```
%d  → int
%f  → float
%c  → char
```

---

# 5️⃣ scanf

`scanf` كتستعملها باش **تاخذ input من المستخدم**.

مثلاً:

```
int age;

scanf("%d", &age);
```

لاحظ هادي:

```
&age
```

ما تحاولش تحفظ علاش دابا.

غير عرف أن `&` هنا مرتبط بعنوان الـvariable، وغادي نفهموه مزيان ملي نوصلو للـpointers.

---

# 6️⃣ Operators

Operators هما الرموز اللي كنستعملو باش نديرو عمليات أو مقارنات.

### الحساب:

```
+   -   *   /   %
```

مثلاً:

```
int result = 10 + 5;
```

`%` كتعطيك **الباقي ديال القسمة**:

```
10 % 3
```

النتيجة:

```
1
```

وهاد `%` مهمة بزاف فـproblem solving.

---

### المقارنة:

```
==    !=    >    <    >=    <=
```

مثلاً:

```
age >= 18
```

هاد expression كتكون نتيجتها:

```
true
```

ولا:

```
false
```

---

# 7️⃣ if / else

كتستعملها باش البرنامج **ياخذ قرار حسب condition**.

مثلاً:

```
if (age >= 18)
{
    printf("Adult\n");
}
else
{
    printf("Minor\n");
}
```

الفكرة:

```
condition
    ↓
  true  → if
  false → else
```

ما تحتاجش أكثر من هادشي اليوم.

---

# 8️⃣ for

`for` كتستعملها ملي كتكون باغي **تعاود نفس العملية عدة مرات**.

مثلاً:

```
for (int i = 0; i < 10; i++)
{
    printf("%d\n", i);
}
```

الفكرة ديالها:

```
initialization
      ↓
   condition
      ↓
     code
      ↓
    update
      ↓
   condition
      ↓
     ...
```

ما تحفظش الشكل فقط. خاصك تفهم **علاش loop كتوقف**.

---

# 9️⃣ while

نفس الفكرة: تكرار.

```
int i = 0;

while (i < 10)
{
    printf("%d\n", i);
    i++;
}
```

الفرق البسيط اللي خاصك اليوم:

**`for`** مزيانة ملي عارف structure ديال التكرار.

**`while`** مزيانة ملي كتفكر أكثر فـ"بقا دير هادشي مادام الشرط صحيح".

ما تحتاجش تدخل فالتفاصيل دابا.

---

# 🔟 Functions

هادشي مهم جداً.

**Function = جزء من الكود عندو مهمة محددة، كتقدر تستعملو مرات متعددة.**

مثلاً:

```
int square(int number)
{
    return number * number;
}
```

ومن بعد:

```
int result = square(5);
```

النتيجة:

```
25
```

عندك:

```
int       → نوع القيمة اللي غادي ترجع
square    → اسم function
int number → parameter
return    → القيمة اللي غادي ترجع
```

---

# 🧠 دابا سالينا النظرية ديال اليوم

وهنا بغيتك **توقف القراية**.

ما تمشيش تشوف tutorial.

دابا وقت الـcoding.

---

# 🔥 التمرين 1

صايب:

```
calculator.c
```

البرنامج يسول المستخدم على جوج أرقام:

```
Enter first number:
Enter second number:
```

ومن بعد يطبع:

```
Sum
Difference
Multiplication
Division
Remainder
```

مثلاً:

```
Enter first number: 10
Enter second number: 3

Sum = 13
Difference = 7
Multiplication = 30
Division = 3
Remainder = 1
```

**ممنوع تستعمل ChatGPT باش يعطيك الكود.** 😄

إلا نسيت syntax ديال شي حاجة، رجع فقط للتعاريف اللي فوق.

---

# 🔥 التمرين 2

صايب:

```
number.c
```

المستخدم يدخل number.

البرنامج يقول:

```
Positive / Negative / Zero
Even / Odd
Greater than 100 / Not greater than 100
```

مثلاً:

```
Enter number: 42

Positive
Even
Not greater than 100
```

---

# 🔥 التمرين 3

صايب برنامج:

```
numbers.c
```

المستخدم يدخل `N`.

البرنامج يطبع:

```
1
2
3
...
N
```

ومن بعد يطبع:

```
Sum = ...
```

ومن بعد:

```
Even numbers = ...
```

مثلاً `N = 10`:

```
Numbers:
1 2 3 4 5 6 7 8 9 10

Sum = 55

Even:
2 4 6 8 10
```

هنا غادي تستعمل **loop + condition**.

---

# 🧠 التمرين 4 — مهم

دير function:

```
is_even()
```

كتاخد number وكتقول واش زوجي ولا فردي.

ومن بعد استعملها فـ`main`.

الفكرة:

```
main
 ↓
is_even(7)
 ↓
Odd
```

ما نعطيكش implementation. بغيتك تفكر فيها.

---

# 🏆 Challenge ديال اليوم

إلا ساليت الأربعة، دير:

## Prime Checker

المستخدم يدخل رقم:

```
Enter number: 17
```

البرنامج يقول:

```
17 is prime
```

وإلا:

```
Enter number: 15

15 is not prime
```

**هاد التمرين ما تقلبش على الحل.**

جلس معاه.

فكر:

> شنو هو Prime؟

> شحال من numbers خاصني نجرب نقسم عليهم؟

> كيفاش نعرف واش شي number كيقسم number آخر؟

استعمل:

```
%
for
if
```

وهنا غادي نبدأو نرجعو **عقلية problem solving** ديالك.

---

# 📁 نظم الخدمة ديالك هكا

```
embedded-journey/
└── 01-c-refresh/
    ├── calculator.c
    ├── number.c
    ├── numbers.c
    ├── functions.c
    └── prime.c
```

وكل ملف compile بوحدو.

مثلاً:

```
gcc -Wall -Wextra -Werror calculator.c -o calculator
./calculator
```

هاد flags مهمين:

```
-Wall
-Wextra
-Werror
```

كيخليو compiler يشدد معاك فـwarnings، وهاد العادة زوينة من البداية.

---

# ⏱️ كيفاش تقسم هاد العشية؟

```
20 دقيقة
↓
قرا التعاريف اللي فوق

30 دقيقة
↓
Calculator

30 دقيقة
↓
Number Analyzer

30 دقيقة
↓
Loops + Numbers

20 دقيقة
↓
Functions

30-45 دقيقة
↓
Prime Challenge
```

**إلا بقا شي تمرين ما خدمش، ماشي مشكل.**

المهم أنك **كتفكر وكتكتب بيدك**.

---

## 🚨 وقاعدة ديالنا من اليوم

من دابا، أي concept غادي نتعلموه غادي ندوزوه بهاد الطريقة:

**Definition → مثال صغير → تمرين → Challenge → مراجعة الكود.**

ما غاديش نقول ليك:

> "سير شوف 3 ساعات ديال C tutorial."

لا.

أنا نعطيك **غير المعرفة اللي محتاجها فداك النهار**، وأنت تطبق.

**دابا المهمة الوحيدة ديالك هي اليوم 1. ما تقفزش لليوم 2.**

ومن ملي تسالي، صيفط ليا **الكود ديالك حتى إلا كان فيه errors**. ما تصلحوش قبل ما تصيفطو؛ بغيت نشوف كيفاش كتفكر، ومن تما نصلحو مع بعضياتنا ونحدد ليك **اليوم 2 بالضبط**.

chra7 lia hado -Wall -Wextra -Werror

أكيد خويا. هادو مهمين، وخصوصاً إلى بغينا من دابا نعودوك على **طريقة خدمة مزيانة ديال Programmer**.

ملي كتكتب:

```
gcc -Wall -Wextra -Werror main.c -o main
```

راه كتقول لـ`gcc`:

> "Compile ليا هاد البرنامج، ولكن بغيتك تكون صارم معايا وتنبّهني لأي حاجة مشبوهة فالكود."

نفصلوهم:

---

## 1. `-Wall`

`-Wall` جاية من:

**Warnings ALL**

ولكن الاسم شوية مضلل 😄، ماشي حرفياً جميع الـwarnings.

كتفعل مجموعة مهمة من التحذيرات اللي `gcc` يقدر يكتاشفها.

مثلاً:

```
#include <stdio.h>

int main(void)
{
    int age;

    printf("Hello\n");

    return 0;
}
```

هنا `age` معلنة ولكن ما استعملناهاش.

إلى compile عادي:

```
gcc main.c -o main
```

ممكن البرنامج يتـcompile عادي.

ولكن مع:

```
gcc -Wall main.c -o main
```

ممكن يعطيك warning بحال:

```
warning: unused variable 'age'
```

يعني:

> "آ صاحبي، علاش صايب variable وما استعملتيهاش؟"

⚠️ الـwarning **ماشي error**. البرنامج يقدر يتـcompile.

---

# 2. `-Wextra`

هاد وحدة كتزيد:

**Warnings إضافية**

يعني `-Wall` عطاك مجموعة مهمة، و`-Wextra` كتقول لـGCC:

> "زيد قلب ليا حتى على مشاكل أخرى."

مثلاً ممكن تكتشف ليك حاجات ما غطاتهاش مجموعة `-Wall`.

لهذا غالباً كتلقى الناس كيديرو:

```
gcc -Wall -Wextra main.c -o main
```

بدل غير:

```
gcc main.c -o main
```

---

# 3. `-Werror`

هادي هي اللي مهمة بزاف.

`-Werror` معناها:

> **أي Warning اعتابرو Error.**

مثلاً عندك:

```
int main(void)
{
    int age;

    return 0;
}
```

مع:

```
gcc -Wall -Wextra main.c -o main
```

إلى GCC لقا:

```
warning: unused variable 'age'
```

راه غير warning، وغالباً البرنامج غادي يتبنى.

ولكن:

```
gcc -Wall -Wextra -Werror main.c -o main
```

دابا نفس الـwarning كتولي:

```
error: unused variable 'age'
```

والـcompilation كتوقف.

يعني GCC كيقول ليك:

> "صلح الكود ديالك عاد نكمل."

---

# 🧠 علاش بغيتك تستعملهم؟

حيت دابا نقدر نخليك من البداية تعتاد على:

```
كتكتب code
     ↓
Compiler
     ↓
Compiler كينتقد الكود ديالك
     ↓
كتصلح المشاكل
     ↓
Compile ناجح
```

ماشي:

```
كتكتب code
     ↓
كيخدم
     ↓
صافي 😂
```

هاد الفرق مهم.

خصوصاً فـEmbedded، فين bugs صغيرة تقدر تسبب مشاكل كبيرة.

---

# 🔥 جربها دابا بنفسك

صايب `test.c`:

```
#include <stdio.h>

int main(void)
{
    int age = 25;
    int number = 10;

    printf("Hello\n");

    return 0;
}
```

جرب:

```
gcc test.c -o test
```

ومن بعد:

```
gcc -Wall -Wextra test.c -o test
```

وشوف شنو قال ليك.

ومن بعد:

```
gcc -Wall -Wextra -Werror test.c -o test
```

غادي تشوف الفرق.

---

## 🎯 وخلي عندك هاد القاعدة

من دابا فـC ديالك:

```
gcc -Wall -Wextra -Werror file.c -o file
```

**ماشي ضروري تحفظ شنو كل warning كيعني من دابا.**

إلا خرج ليك warning/error، **قراه وحاول تفهم علاش خرج**.

وهنا بالضبط غادي نتعلمو بطريقة Programmer:  
**ماشي نحفظو المعلومات، ولكن نتعلمو نقراو المشاكل ونحلّوها.**إييه آحمد، دابا فهمتك بالضبط 😄. بغيتي **Mini Project فيه logic بزاف** باش تجمع `variables + conditions + loops + functions + arrays + strings + input/output`، ولكن **مازال بلا pointers وstructs** حيث ما وصلناش ليهم.




# 🔥 Mini Project: نظام تسيير Parking

غادي نصاوبو **Parking Management System** فالـTerminal.

الفكرة:

عندك Parking فيه مثلاً **20 بلاصة**، والبرنامج خاصو يسير الدخول والخروج ديال السيارات.

---

## 🎯 شنو خاص البرنامج يدير؟

ملي تشغلو يعطيك Menu:

```
================================
       PARKING MANAGEMENT
================================

1. Add car
2. Remove car
3. Search car
4. Show all cars
5. Show available spaces
6. Show statistics
7. Exit

Choose:
```

وهنا غادي يبدا الـlogic الحقيقي.

---

# 1️⃣ Add car

المستخدم يدخل:

```
Enter plate number: 12345-A-6
Enter owner name: Ahmed
```

البرنامج خاصو يتحقق:

### واش Parking عامر؟

```
Parking full!
```

إلا ما عامرش:

### واش نفس السيارة داخلة من قبل؟

```
Car already exists!
```

إلا ما كانتش:

```
Car added successfully!
Space number: 7
```

يعني هنا عندك:

```
if
arrays
loops
strings
functions
logic
```

---

# 2️⃣ Remove car

المستخدم يدخل:

```
Enter plate number: 12345-A-6
```

البرنامج يقلب عليها.

إلا لقاها:

```
Car found.
Removing car...
Car removed successfully.
```

إلا ما لقاهاش:

```
Car not found.
```

ولكن هنا خاصك تفكر:

> كيفاش نحرك البيانات من بعد ما نحيد سيارة؟

مثلاً:

```
[CAR] [CAR] [CAR] [EMPTY] [CAR]
```

من بعد remove:

```
[CAR] [CAR] [EMPTY] [CAR] [CAR]
```

ولا تقدر تخلي الـspace فارغة.

**اختار أنت التصميم.**

---

# 3️⃣ Search car

المستخدم يقدر يقلب بالـplate:

```
Enter plate: 12345-A-6

Car found!

Plate: 12345-A-6
Owner: Ahmed
Space: 7
```

إلا ما لقاهاش:

```
Car not found.
```

---

# 4️⃣ Show all cars

يطبع:

```
================================
           CARS
================================

Space 1  | 12345-A-6 | Ahmed
Space 2  | EMPTY
Space 3  | 98765-B-2 | Yassine
Space 4  | EMPTY
...
```

هنا خاصك تستعمل loops مزيان.

---

# 5️⃣ Available spaces

مثلاً:

```
Total spaces: 20
Occupied: 7
Available: 13
```

ولكن ما بغيتكش تخزن `available = 13` وتبدلها يدويّاً.

خلي البرنامج **يحسبها** من الـdata.

هادشي مهم فالتفكير البرمجي.

---

# 6️⃣ Statistics 🔥

هنا نزيدو شوية logic.

مثلاً:

```
================================
          STATISTICS
================================

Total spaces: 20
Occupied spaces: 8
Available spaces: 12

Occupancy: 40%

Cars starting with 1: 3
Cars starting with 2: 2
Cars starting with 3: 1

Longest owner name: Yassine
```

ماشي ضروري تدير آخر 3 إحصائيات من الأول؛ ولكن بغيتك على الأقل تدير:

```
Total
Occupied
Available
Occupancy %
```

---

# 7️⃣ Exit

```
Are you sure you want to exit? (y/n):
```

إلا `y`:

```
Goodbye!
```

إلا `n`:

يرجع للـMenu.

---

# 🧠 دابا أهم حاجة: Architecture

ما بغيتكش تدير:

```
int main()
{
    // 500 lines
}
```

❌ لا.

قسم البرنامج لـfunctions.

مثلاً:

```
main()
│
├── show_menu()
├── add_car()
├── remove_car()
├── search_car()
├── show_cars()
├── show_available_spaces()
└── show_statistics()
```

ولكن **أنت اللي خاصك تحدد parameters والـreturn values**.

أنا ما غاديش نعطيك التصميم كامل.

---

# 📦 Data ديالك

بما أننا مازال ما وصلناش لـ`struct`، غادي نستعملو arrays.

مثلاً غادي تحتاج تفكر فشي حاجة بحال:

```
char plates[20][20];
char owners[20][50];
int occupied[20];
```

ولكن ما تاخدش هادشي كحل جاهز.

فكر:

> شنو المعلومات اللي خاصني نخزن لكل سيارة؟

عندك على الأقل:

```
Plate
Owner
Space
```

وبما أننا مازال ما تعلمناش `struct`، خاصك تدير mapping بين arrays.

**هادشي intentional.**

من بعد ملي نوصلو لـ`struct` غادي نرجعو لنفس المشروع ونشوفو كيفاش `struct` كتخليه أنظف بزاف.

---

# 🔥 Logic Challenges

وهادي هي أهم حاجة فالمشروع.

## Challenge 1

إلا دخل المستخدم:

```
12345-A-6
```

وكاينة:

```
12345-A-6
```

خاص البرنامج يرفضها.

ولكن:

```
12345-A-7
```

خاصو يقبلها.

يعني خاصك تدير **String comparison**.

---

## Challenge 2

إلا Parking فيه:

```
20 spaces
```

والـ20 كاملين عامرين.

ملي يدير:

```
Add car
```

خاصك ما تخليش البرنامج يدخل سيارة إضافية.

---

## Challenge 3

إلا شي واحد دار:

```
Remove car
```

بـplate ما كايناش:

```
Car not found
```

وما يتبدل حتى data.

---

## Challenge 4

الـMenu خاصو يبقى خدام:

```
Menu
 ↓
Action
 ↓
Menu
 ↓
Action
 ↓
Menu
 ↓
...
```

يعني البرنامج ما يساليش حتى المستخدم يختار Exit.

هنا غادي تحتاج loop.

---

# 🚨 Input validation

وهنا نزيدو level آخر.

إلا المستخدم كتب:

```
Choose: 99
```

خاص:

```
Invalid choice!
```

ويرجع للـMenu.

إلا كتب:

```
Choose: -1
```

نفس الشي.

---

# 🧠 المستوى اللي بغيت منك

ما تحاولش تكمل المشروع كامل فنهار واحد.

ديرو بهاد المراحل:

### Level 1

```
Menu
Add
Show
Exit
```

### Level 2

```
Remove
Search
```

### Level 3

```
Validation
Parking full
Duplicate plate
Invalid menu
```

### Level 4

```
Statistics
```

### Level 5 🔥

حاول تزيد:

```
Entry time
Exit time
Parking duration
Price
```

وهنا غادي تدخل فـlogic أقوى.

مثلاً:

```
First hour: 5 DH
Each additional hour: 3 DH
```

وتحسب الثمن حسب مدة الوقوف.

---

# ⚠️ القاعدة ديال المشروع

**ممنوع:**

❌ Copy/Paste solution  
❌ تشوف project كامل فـYouTube  
❌ تستعمل ChatGPT باش نعطيك implementation

**مسموح:**

✅ تقلب على syntax ديال function نسيتيها  
✅ تقرا documentation ديال `strcmp` مثلاً  
✅ تسولني على concept  
✅ تصيفط ليا error  
✅ تصيفط ليا الكود ونراجعو

---

# 🎯 والهدف الحقيقي

المشروع ماشي Parking.

الهدف هو أنك من بعد ما تساليه تكون قادر تقول:

> "نقدر ناخد problem، نفككها، نحدد data، نحدد functions، ونكتب algorithm قبل ما نبدا code."

**هاد المهارة هي اللي بغينا نرجعوها عندك.**

وزيد حاجة مهمة: منين نساليو هاد المشروع، **ما غاديش نرميه**. غادي نرجعو ليه فالمراحل الجاية:

```
Version 1
C basics
    ↓
Version 2
Arrays + Strings
    ↓
Version 3
Structs
    ↓
Version 4
Pointers
    ↓
Version 5
Files
    ↓
Version 6
Embedded mindset
```

يعني نفس المشروع غادي يكبر معاك، وكل مرة غادي تشوف **علاش concept جديد فـC مفيد**. 🔥
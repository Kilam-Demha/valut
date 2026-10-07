t9dar tchra7 lia nawa3 errors li kainin fi c

أكيد 👍 فـ C كاينين أنواع مختلفة ديال **errors**، ومهم بزاف تفهم الفرق بينهم حيث ملي الكود كيطيح، أول سؤال خاصك تعرفو هو: **فين وقع المشكل؟**

غادي نشرحهم ليك من الصفر وبـ Darija بالعربية.

## 🧠 الخريطة العامة

```
                 ERRORS فـ C
                     │
        ┌────────────┼────────────┐
        ↓            ↓            ↓
   Compile Error   Linker Error   Runtime Error
        │                           │
        ↓                           ↓
  الكود ما كيتجمعش             البرنامج خدام
                                  ولكن كيوقع
                                  مشكل أثناء التنفيذ
        │
        └──────────────┐
                       ↓
                Logical Error
                       │
                       ↓
                 البرنامج خدام
                 ولكن النتيجة غلط
```

كاين حتى نوع مهم آخر:

```
Warning ⚠️
   ↓
ماشي بالضرورة Error
ولكن compiler كيقول:
"راه كاين شي حاجة مشبوهة هنا"
```

---

# 1️⃣ Syntax / Compile Error

هاد النوع كيوقع ملي كتكتب C بطريقة ما كتوافقش قواعد اللغة.

مثلاً:

```
#include <stdio.h>

int main(void)
{
    printf("Hello")
    return 0;
}
```

نسينا `;` من بعد `printf`.

غالباً compiler غادي يعطيك شي حاجة بحال:

```
error: expected ';' before 'return'
```

يعني:

> كنت كنتسنى `;` قبل `return`.

### مثال آخر

```
int main(void)
{
    int age = 20

    return 0;
}
```

حتى هنا ناقصة `;`.

### القاعدة

**Compile Error = compiler ما قدرش يحول الكود ديالك لبرنامج قابل للتنفيذ.**

يعني:

```
.c
 ↓
Compiler
 ↓
❌ STOP
```

---

# 2️⃣ Semantic / Type Error

هنا syntax ممكن تكون صحيحة، ولكن **المعنى ديال الكود ماشي صحيح** أو النوع ديال البيانات ما مناسبش.

مثلاً:

```
int age = "Ahmed";
```

Syntax ديال declaration صحيحة:

```
int age = ...
```

ولكن `int` خاصو رقم، وانت عطيتو string.

```
int
 ↓
خاص رقم

"Ahmed"
 ↓
string ❌
```

مثال آخر:

```
int result;

result = 10 / "2";
```

ما عندهاش معنى فـ C.

هاد الأخطاء غالباً compiler كيكتاشفها.

---

# 3️⃣ Linker Error

هاد النوع مختلف شوية.

الكود ديالك ممكن يكون **صحيح syntaxياً**، ولكن ملي compiler كيوصل لمرحلة الربط، ما كيلقاش شي function أو library محتاجها.

مثلاً:

```
#include <stdio.h>
#include <math.h>

int main(void)
{
    double x = sqrt(25);

    printf("%f\n", x);

    return 0;
}
```

إلا compileيتي هكذا:

```
gcc main.c
```

ممكن يوقع:

```
undefined reference to `sqrt'
```

حيت `sqrt()` جاية من math library، وخصك تربطها:

```
gcc main.c -lm
```

هنا:

```
main.c
  ↓
Compiler
  ↓
Object file
  ↓
Linker
  ↓
❌ sqrt ما لقاهاش
```

ومع:

```
gcc main.c -lm
```

```
main.c
  ↓
Compiler
  ↓
Linker + libm
  ↓
Executable ✅
```

---

# 4️⃣ Runtime Error

هنا البرنامج **تجمع بنجاح** وبدأ يخدم، ولكن المشكل وقع أثناء التنفيذ.

مثلاً:

```
#include <stdio.h>

int main(void)
{
    int a = 10;
    int b = 0;

    printf("%d\n", a / b);

    return 0;
}
```

هنا:

```
10 / 0
```

ماشي عملية صحيحة.

البرنامج ممكن يتوقف أثناء execution.

يعني:

```
Compile
   ↓
✅
   ↓
Run
   ↓
💥 Runtime Error
```

---

# 5️⃣ Memory Error

هاد النوع مهم بزاف خصوصاً ملي غادي توصل لـ **pointers**.

مثلاً:

```
int main(void)
{
    int array[3];

    array[10] = 5;

    return 0;
}
```

عندك:

```
array[0]
array[1]
array[2]
```

ولكن انت مشيتي لـ:

```
array[10]
```

وهذا خارج حدود الـ array.

هادشي ممكن يسبب:

- crash
- segmentation fault
- corruption ديال memory
- نتائج غريبة

والمشكل أن compiler ماشي دائماً يقدر يكتاشفو.

---

# 6️⃣ Logical Error

هاد واحد مهم بزاف حيث البرنامج **ما كيقولكش بالضرورة كاين error**.

مثلاً بغينا نحسبو المتوسط:

```
int a = 10;
int b = 20;

int average = a + b / 2;

printf("%d\n", average);
```

يمكن انت كنت باغي:

```
(10 + 20) / 2
= 15
```

ولكن C كتطبق precedence:

```
10 + (20 / 2)
= 20
```

يعني البرنامج خدام:

```
Compilation ✅
Execution ✅
Crash ❌
```

ولكن:

```
Result = 20 ❌
```

هاد هو:

> **Logical Error = البرنامج خدام ولكن المنطق ديالك غلط.**

والحل:

```
int average = (a + b) / 2;
```

---

# 7️⃣ Warning ⚠️

هادشي **ماشي Error بالضرورة**.

مثلاً:

```
#include <stdio.h>

int main(void)
{
    int age;

    printf("%d\n", age);

    return 0;
}
```

`age` ما عطيناهش قيمة قبل ما نستعملوه.

إلا استعملتي:

```
gcc -Wall -Wextra -Werror main.c
```

compiler يقدر يعطيك warning/error حسب الحالة.

خصوصاً مع:

```
-Wall
-Wextra
-Werror
```

### الفرق:

```
Warning ⚠️
    ↓
"كاين احتمال يكون عندك مشكل"

Error ❌
    ↓
"ما نقدرش نكمل"
```

ومع:

```
-Werror
```

كتقول للـ compiler:

```
Warning → تعامل معاه بحال Error
```

---

# 🧠 أهم فرق خاصك تحفظو

|النوع|شنو وقع؟|
|---|---|
|**Syntax / Compile Error**|كتبت C بطريقة مخالفة للقواعد|
|**Semantic / Type Error**|المعنى أو الأنواع ماشي مناسبين|
|**Linker Error**|function/library المطلوبة ما تلقاتش|
|**Runtime Error**|المشكل وقع والبرنامج خدام|
|**Memory Error**|تعامل غلط مع memory|
|**Logical Error**|البرنامج خدام ولكن النتيجة غلط|
|**Warning**|compiler شاف حاجة مشبوهة|

وأهم حاجة:

```
             كتكتب code
                  ↓
              Compiler
                  ↓
        ┌─────────┴─────────┐
        ↓                   ↓
      Error               OK
        ↓                   ↓
      STOP                Linker
                            ↓
                     ┌──────┴──────┐
                     ↓             ↓
                   Error           OK
                     ↓             ↓
                   STOP          Program
                                    ↓
                                  Run
                                    ↓
                              ┌─────┴─────┐
                              ↓           ↓
                           Runtime     Logical
                            Error       Error
```

**ملاحظة مهمة:** ماشي كل المشاكل فـ C كيتسمّاو رسمياً بنفس التصنيف؛ بعض المصادر كتفرق بين compile-time/type/constraint errors وlinker/runtime/undefined behavior. ولكن هاد التقسيم عملي جداً باش تتعلم **كيفاش تشخّص المشكل**.

إلى بغيتي تتعلم C مزيان، من بعد نقدر ندوزو **Error by Error**: نعطيك code فيه مشكل، وانت تحاول تلقى الـerror وتصلحو، وأنا نصحح ليك.

![](https://images.openai.com/static-rsc-5/tiJw_KLDoRbYZaPmgPv_vJZn8xCbmcvmbLrzPcxuBj9GUYZWr9izf19je7CndLSlLvMeJtTQm2czrzzy20SXl6rd-J83aRcD7qadLP3vpKnLBoF7qeJiFf3szRIYmWjl3KTM19N8OQ8RgZUCOsiZRojlo8RUI0emTAy-WuSDYHOoyrMzX2zFX5FetEVdqC2f48d2R0qJ9hOwhJQEg8QzE2d1CEGYtfWMS5uPu3YsOJ6TSP0PgzwTjqWbZN_45JVD_dhhbfsu1XUzd8dYzY5dIQ)

![](data:image/webp;base64,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)

NodeMaven

Proxies for Python

Connect your scraper with HTTP(S), SOCKS5 and location targeting

Pub

Plus d’options

chno lfar9 bin exucution time o run time o compiler time

آه، هادو كيتخلطو بزاف فالبداية، ولكن الفرق بسيط:

### 1. Compiler time 🛠️

هو **الوقت اللي الـcompiler كيخدم فيه على الكود ديالك**.

مثلاً:

```
int x = 10;
printf("%d\n", x);
```

كتدير:

```
gcc main.c -o main
```

هنا `gcc` كيقرأ الكود وكيحاول يحولو لبرنامج قابل للتنفيذ.

```
main.c
  ↓
Compiler
  ↓
main
```

إذن:

> **Compiler time = الوقت ديال compilation.**

إلا كان عندك syntax error:

```
printf("Hello")
```

المشكل كيظهر فـ **compiler time**.

---

### 2. Run time ▶️

هو **الوقت اللي البرنامج ديالك كيكون خدام فعلياً**.

من بعد:

```
gcc main.c -o main
```

كتشغل:

```
./main
```

دابا البرنامج دخل لـ **run time**.

مثلاً:

```
int age = 20;
printf("%d\n", age);
```

أثناء تشغيل البرنامج، CPU كينفذ التعليمات.

```
Source Code
    ↓
Compiler time
    ↓
Executable
    ↓
Run time
    ↓
CPU executes instructions
```

---

### 3. Execution time ⚙️

هنا النقطة المهمة:

**Execution time و Run time غالباً كيتستعملو بمعنى قريب جداً، ولكن ماشي دائماً بنفس المعنى الدقيق.**

**Execution time** كيركز أكثر على:

> الوقت اللي كيحتاجو البرنامج/تعليمة باش تتنفذ.

مثلاً عندك:

```
for (int i = 0; i < 1000000; i++)
{
    // ...
}
```

إلى قلنا:

> "شنو هو execution time ديال هاد البرنامج؟"

كنقصدو **شحال من وقت خدات عملية التنفيذ**.

مثلاً:

```
Program started
      ↓
   execution
      ↓
Program finished

   0.25 seconds
```

أما **run time** كتقدر تشير بشكل أوسع إلى **المرحلة اللي البرنامج فيها خدام**.

---

## 🧠 حفظها بهاد الطريقة

```
          C PROGRAM
              │
              ↓
       COMPILER TIME
       "نبني البرنامج"
              │
              ↓
         executable
              │
              ↓
          RUN TIME
       "نشغل البرنامج"
              │
              ↓
       EXECUTION TIME
      "شحال خدات التنفيذ؟"
```

مثال واقعي:

```
gcc main.c -o main
```

⬆️ **Compiler time**

ثم:

```
./main
```

⬆️ **Run time**

وإلى البرنامج خدم فـ:

```
0.15 seconds
```

⬆️ هادي هي **execution time**.

### ⚠️ ولكن

ما تقولش:

> "Run time و Execution time هما جوج مراحل مختلفين تماماً."

لا. فـ البرمجة المصطلحين **كيكون بينهم تداخل كبير**، وخصوصاً "runtime" كيتستعمل أيضاً بمعنى البيئة/المرحلة اللي البرنامج كيتنفذ فيها.

**الخلاصة:**

|المصطلح|المعنى|
|---|---|
|**Compiler time**|الوقت اللي compiler كيحوّل فيه source code|
|**Run time**|المرحلة اللي البرنامج فيها كيتشغل|
|**Execution time**|المدة/الوقت اللي كتحتاجو عملية التنفيذ|

مثلاً **runtime error** معناها: الخطأ وقع **أثناء تشغيل البرنامج**، ماشي أثناء compilation.

  

[](#probe&oppref=0)

Sponsored options

Ad
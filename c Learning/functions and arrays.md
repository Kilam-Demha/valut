إييه أحمد، دابا فهمت شنو باغي بالضبط. ما بغيناش نبقاو عالقين فـ Binary بزاف. الهدف ديالنا هو **نكملو مراجعة C بطريقة عملية**: شوية logic + functions حتى تولّي مرتاح فـ syntax، parameters, return types، ومن بعد ندخلو للـ pointers وmemory وbit manipulation.

غادي نخدمو بحال **training** ماشي tutorial طويل.

## الخطة ديالنا دابا

غادي نمشيو بهاد الترتيب:

```
1. Functions basics
   ↓
2. Parameters / arguments
   ↓
3. Return types
   ↓
4. void
   ↓
5. Scope + local variables
   ↓
6. Functions مع arrays
   ↓
7. Functions مع pointers
   ↓
8. Logic problems
   ↓
9. Bitwise + Binary
```

والـ Binary اللي بدينا فيه غادي نرجعو ليه ملي نوصلو للـ bitwise، باش يكون عندو معنى.

---

# 1. أولاً: شنو هي Function؟

Function هي **جزء من البرنامج عندو مهمة محددة**.

مثلاً بغينا نحسبو مجموع جوج أرقام.

بلا function:

```
int a = 10;
int b = 20;

int result = a + b;
```

مع function:

```
int add(int a, int b)
{
    return a + b;
}
```

ومن بعد:

```
int result = add(10, 20);
```

الفكرة:

```
add(10, 20)
    ↓
function
    ↓
30
```

---

# 2. Function عندها 4 حوايج خاصك تميزهم

شوف:

```
int add(int a, int b)
{
    return a + b;
}
```

قسمها:

```
int        add        (int a, int b)
 ↑          ↑                ↑
return    name          parameters
type
```

و:

```
return a + b;
```

هي القيمة اللي function غادي ترجع.

إذن:

### `int`

هادشي سميتو:

**Return type**

يعني:

> function غادي ترجع `int`.

---

### `add`

هاد هو:

**Function name**

---

### `int a, int b`

هادو:

**Parameters**

يعني المعلومات اللي function كتحتاج تدخل ليها.

---

### `return`

كتحدد شنو غادي ترجع function.

---

# 3. Parameters و Arguments

هاد الفرق مهم.

عندنا:

```
int add(int a, int b)
{
    return a + b;
}
```

`a` و `b` سميتهم:

> parameters

ولكن ملي نديرو:

```
add(10, 20);
```

`10` و `20` سميتهم:

> arguments

بمعنى:

```
parameter = المتغير اللي كيتستقبل القيمة

argument = القيمة اللي عطينا للـ function
```

مثال:

```
int add(int a, int b)
```

```
a ← parameter
b ← parameter
```

وملي:

```
add(5, 8);
```

```
5 ← argument
8 ← argument
```

---

# 4. Types ديال Functions

هادشي هو اللي باغي نركزو عليه.

## النوع 1: Function كترجع `int`

```
int square(int x)
{
    return x * x;
}
```

مثلاً:

```
int result = square(5);
```

النتيجة:

```
25
```

---

## النوع 2: Function كترجع `float`

```
float half(float x)
{
    return x / 2.0f;
}
```

مثلاً:

```
float result = half(10.0f);
```

النتيجة:

```
5.0
```

---

## النوع 3: Function كترجع `char`

```
char firstLetter(void)
{
    return 'A';
}
```

---

## النوع 4: Function كترجع `void`

هنا function **ما كترجع حتى قيمة**.

مثلاً:

```
void hello(void)
{
    printf("Hello\n");
}
```

كنستعملوها:

```
hello();
```

ما تقدرش دير:

```
int x = hello();   // غلط
```

حيت `hello()` ما عندهاش return value.

---

# 5. دابا واحد التصنيف مهم

Function تقدر تكون:

### عندها parameters وعندها return

```
int add(int a, int b)
{
    return a + b;
}
```

### عندها parameters وما عندهاش return

```
void printNumber(int x)
{
    printf("%d\n", x);
}
```

### ما عندهاش parameters وعندها return

```
int getNumber(void)
{
    return 42;
}
```

### ما عندها لا parameters لا return

```
void hello(void)
{
    printf("Hello\n");
}
```

يعني عندك هاد الـ matrix:

```
                         Return
                    نعم          لا
                 ┌─────────┬─────────┐
Parameters نعم   │ int f() │ void f() │
                 ├─────────┼─────────┤
Parameters لا    │ int f() │ void f() │
                 └─────────┴─────────┘
```

---

# دابا بغيتك تخدم Logic 🔥

ما نعطيكش الحل.

## Exercise 1 — Function بسيطة

كتب function سميتها:

```
isEven
```

كتاخد:

```
int
```

وترجع:

```
int
```

المطلوب:

```
إذا كان الرقم زوجي → ترجع 1
إذا كان فردي → ترجع 0
```

مثلاً:

```
isEven(8) → 1
isEven(7) → 0
isEven(100) → 1
isEven(13) → 0
```

**ممنوع دابا تستعمل أي حاجة معقدة.** غير `if` و `%`.

---

## Exercise 2 — أكبر رقم

كتب:

```
int max(int a, int b)
```

وترجع الرقم الأكبر.

```
max(10, 20) → 20
max(50, 12) → 50
max(7, 7)   → 7
```

---

## Exercise 3 — Absolute Value

كتب:

```
int absolute(int x)
```

مثلاً:

```
absolute(5)  → 5
absolute(-5) → 5
absolute(0)  → 0
```

---

## Exercise 4 — Logic شوية أقوى

كتب:

```
int countDigits(int n)
```

المطلوب ترجع عدد الأرقام.

```
countDigits(7)     → 1
countDigits(42)    → 2
countDigits(1234)  → 4
countDigits(99999) → 5
```

هنا غادي تحتاج **loop + logic**.

---

## Exercise 5 — Function كتستعمل Function أخرى

من بعد دير:

```
int isPositive(int n)
```

و:

```
int isEven(int n)
```

ومن بعد:

```
int isPositiveEven(int n)
```

مثلاً:

```
isPositiveEven(8)  → 1
isPositiveEven(-8) → 0
isPositiveEven(7)  → 0
isPositiveEven(0)  → 0
```

هنا غادي نبداو ندربو على **تقسيم المشكلة**:

```
isPositiveEven()
       ↓
 ┌─────┴─────┐
 ↓           ↓
positive    even
```

وهذا مهم بزاف فـ programmer mindset.

---

### طريقة الخدمة ديالنا

ما بغيتكش تكتب جميع التمارين مرة وحدة.

**بدا بـ Exercise 1 فقط.**

كتب ليا الكود ديالك حتى إلا كان فيه غلط، وأنا غادي نخليك تحاول تصلحو بنفسك ونشرح ليك **علاش**، ماشي نعطيك الحل مباشرة.

chof dwi lia ala chno hiya void function o hta kifach nraja3 array fi function ?


إييه، هادو جوج حوايج مهمين بزاف فـ C، خصوصاً إلا بغينا ندوزو من functions للـ pointers والـ arrays. نخليوهم واضحين.

# 1. شنو هي `void` function؟

أولاً، `void` معناها هنا:

> **ما كايناش قيمة راجعة.**

مثلاً:

```
void sayHello(void)
{
    printf("Hello\n");
}
```

هاد function كتدير action:

```
sayHello()
   ↓
تطبع Hello
   ↓
ما كترجع حتى قيمة
```

لذلك ما نقدرش نديرو:

```
int x = sayHello(); // ❌
```

حيت `sayHello()` ما عندهاش return value.

---

## `void` فالجوج بلايص

شوف:

```
void sayHello(void)
```

كاينين جوج `void` ولكن المعنى ديالهوم مختلف.

### الأول:

```
void sayHello
```

هاد `void` هو **return type**.

يعني:

> function ما كترجع حتى قيمة.

### الثاني:

```
sayHello(void)
```

هاد `void` كيعني:

> function ما كتستقبل حتى parameter.

إذن:

```
void sayHello(void)
```

معناها:

> function ما كتستقبل والو وما كترجع والو.

---

# 2. ولكن واش `void` function ما كتدير والو؟

لا ❌.

هاد سوء فهم مشهور.

هي تقدر تدير أي action:

```
void printNumber(int n)
{
    printf("%d\n", n);
}
```

كتستقبل رقم، وكتطبعو، ولكن **ما كترجعش قيمة للـ caller**.

مثلاً:

```
printNumber(42);
```

---

# 3. دابا نجيبو للـ Array

هنا كاين واحد الفرق مهم:

في C، **ما كتقدرش ترجع array مباشرة من function بالطريقة العادية** بحال:

```
int getArray(void)
{
    return ???;
}
```

حيت `int` غير integer.

وحتى:

```
int[] getArray(void) // ❌ ماشي syntax صحيحة فـ C
```

ولكن كاينين طرق أخرى.

---

# 4. الطريقة المهمة: نستعمل Pointer

مثلاً عندنا array:

```
int numbers[5] = {10, 20, 30, 40, 50};
```

إلى بغينا function تعدل هاد الـ array:

```
void doubleArray(int arr[], int size)
{
    for (int i = 0; i < size; i++)
    {
        arr[i] = arr[i] * 2;
    }
}
```

ونستعملوها:

```
doubleArray(numbers, 5);
```

من بعد:

```
numbers:

10  20  30  40  50

        ↓ function

20  40  60  80  100
```

لاحظ:

```
void doubleArray(int arr[], int size)
```

الـ function **ما رجعاتش array**.

هي **عدلات array اللي عطيناها ليها**.

وهذا مهم جداً.

---

# 5. علاش function قدرت تعدل الـ array؟

هنا غادي نبداو ندخلو للـ pointer concept.

ملي كتدير:

```
doubleArray(numbers, 5);
```

فالـ array، فهاد السياق، كيتحول عملياً لـ **pointer لأول عنصر**.

يعني conceptuellement:

```
numbers
   ↓
+----+----+----+----+----+
| 10 | 20 | 30 | 40 | 50 |
+----+----+----+----+----+
  ↑
  |
 address ديال أول عنصر
```

والـ function كتستقبل هاد العنوان:

```
void doubleArray(int arr[], int size)
```

ويمكن كذلك تكتب parameter هكا:

```
void doubleArray(int *arr, int size)
```

فـ parameter ديال function:

```
int arr[]
```

و:

```
int *arr
```

عندهم نفس المعنى تقريباً فهاد السياق.

---

# 6. واش نقدر function "ترجع" pointer لـ array؟

نعم، ولكن هنا خاصنا نكونو حذرين.

مثلاً:

```
int *getArray(void)
{
    ...
}
```

هاد function كتقول:

> غادي نرجع **address ديال int**.

ولكن **ما خاصناش نرجعو pointer لــ local array**:

```
int *getArray(void)
{
    int arr[5] = {1, 2, 3, 4, 5};

    return arr; // ❌ خطر
}
```

علاش؟

حيت `arr` local variable، ومنين function كتسالي، داك الـ storage ديالو ما كيبقاش صالح للاستعمال بهاد الطريقة.

هاد النقطة غادي نوقفو عندها ملي ندخلو pointers وstack.

---

# 7. إذن عندنا 3 أفكار مختلفين

### A — Function ترجع قيمة

```
int add(int a, int b)
{
    return a + b;
}
```

```
input → function → value
```

---

### B — `void` function تعدل array

```
void modify(int arr[], int size)
{
    arr[0] = 100;
}
```

```
array
  ↓
function
  ↓
نفس array تبدلات
```

---

### C — Function ترجع pointer

```
int *function(...)
```

هنا ما كتقولش "غادي نرجع array".

كتقول:

> **غادي نرجع address ديال int.**

وهذا فرق مهم جداً.

---

## حاجة أخيرة مهمة

ملي كتكتب:

```
void printArray(int arr[], int size)
```

كاين واحد السؤال:

**علاش زدنا `size`؟**

حيت داخل function:

```
sizeof(arr)
```

ما غاديش يعطيك size الحقيقي ديال array اللي كانت عند caller بالطريقة اللي كتوقع.

لذلك غالباً كنمررو:

```
array + size
```

مثلاً:

```
printArray(numbers, 5);
```

يعني:

```
numbers → فين كاينة array
5       → شحال فيها من عنصر
```

وهدي من أهم القواعد اللي خاصك تكون حافظها:

> **إلى مررت array لـ function، مرر معها size ديالها.**

هادشي غادي يربط لينا مباشرة **Functions → Arrays → Pointers → Memory**، وهاد هو المسار اللي مناسب ليك دابا فمراجعة C.


wlakin kifach nraja3 array ?

آه، دابا فهمتك: **بغيتي تعرف كيفاش function تقدر “ترجع” array**.

المهم هنا هو أن C **ما كتخليش function ترجع array مباشرة** بحال هكا:

```
int[] getNumbers(void) // ❌
```

ولكن عندك طرق أخرى.

### الطريقة 1: نعطي الـ array للـ function وهي تعمرو

هاد الطريقة هي اللي خاصك تفهمها مزيان دابا:

```
void getNumbers(int arr[], int size)
{
    for (int i = 0; i < size; i++)
    {
        arr[i] = i + 1;
    }
}
```

ومن بعد:

```
int main(void)
{
    int numbers[5];

    getNumbers(numbers, 5);

    for (int i = 0; i < 5; i++)
    {
        printf("%d ", numbers[i]);
    }
}
```

النتيجة:

```
1 2 3 4 5
```

هنا **ما رجعناش array بـ `return`**.

ولكن function خذات array ديال `main`:

```
getNumbers(numbers, 5);
```

وعمراتها:

```
numbers[0] = 1;
numbers[1] = 2;
...
```

يعني تقدر تشوفها هكا:

```
main
 │
 │ numbers[5]
 │
 └──────► getNumbers()
              │
              └── كتبدل نفس array
```

### علاش `void` هنا؟

حيت function ما محتاجاش ترجع value:

```
void getNumbers(...)
```

هي غير **كتخدم على array اللي عطيناها**.

---

أما إلا كنت كتقصد حرفياً:

> "بغيت function تدير array جديدة وترجعها ليا"

فهنا كندخلو فـ **pointers + malloc** أو **static array** أو **struct**.

ولكن قبل ما نمشيو ليهم، خاصك تفهم هاد الفكرة:

> **Array كتدخل للـ function عن طريق pointer، والـ function تقدر تبدل نفس الـ array.**

إلا بغيتي، نديرولك دابا **تمرين صغير غير على array + function** باش تشوف بعينيك كيفاش كتدخل وكيفاش كتخرج منها.

أعطني تمرين صغير غير على array + function باش نشوف كيفاش كتدخل وكيفاش كتخرج منها

أكيد. غادي نعطيك **تمرين واحد فقط**، بلا solution، باش تجرب بيدك.

### 🧠 التمرين: تعديل Array داخل Function

عندك هاد `array`:

```
int numbers[5] = {2, 4, 6, 8, 10};
```

بغينا نكتبوا function سميتها:

```
void doubleArray(int arr[], int size)
```

المطلوب ديالها:

> تضرب كل عنصر داخل الـ array فـ `2`.

يعني من بعد استدعاء الـ function، خاص:

```
2  4  6  8  10
```

تولي:

```
4  8  12  16  20
```

### المطلوب منك

كمّل هاد الكود:

```
#include <stdio.h>

void doubleArray(int arr[], int size)
{
    // كتب الكود هنا
}

int main(void)
{
    int numbers[5] = {2, 4, 6, 8, 10};

    doubleArray(numbers, 5);

    for (int i = 0; i < 5; i++)
    {
        printf("%d ", numbers[i]);
    }

    return 0;
}
```

**مهم:** حاول تفهم هاد السطر:

```
doubleArray(numbers, 5);
```

شنو وقع لـ `numbers` ملي دخلات للـ function؟

حل التمرين، وصيفط ليا الكود ديالك، وأنا نراجعو معاك **سطر بسطر**.
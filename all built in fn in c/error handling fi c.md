أكيد. نعاودو **Error Handling فـ C من الصفر** وبالترتيب، باش تكون عندك الصورة كاملة قبل التمارين.

# Error Handling فـ C — من الصفر

## 1. أولاً: شنو هو Error؟

الـ **error** هو مشكل كيوقع وكيمنع العملية من أنها تدوز بالطريقة اللي كنتي باغي.

مثلاً:

```
int result = 10 / 0;
```

هنا عندنا مشكل، حيث القسمة على `0` غير صالحة.

ولكن فـ C خاصنا نفرقو بين **أنواع الأخطاء**.

---

# 2. أنواع الأخطاء فـ C

## A. Compile-time Error

كيوقع ملي كتكتب code فيه syntax/type problem والـ compiler ما يقدرش يحولو لبرنامج.

مثلاً:

```
int x = ;
```

الـ compiler غادي يعطيك error.

```
Source Code
    ↓
 Compiler
    ↓
❌ Error
```

هاد النوع ماشي هو اللي كنقصدو غالباً ملي كنهدرو على **Error Handling**.

---

## B. Runtime Error

البرنامج قدر يتـcompile، ولكن ملي بدا يخدم وقع مشكل.

مثلاً:

```
int a = 10;
int b = 0;

int result = a / b;
```

هنا المشكل وقع أثناء التنفيذ.

---

## C. Logical Error

البرنامج كيخدم عادي، ولكن المنطق ديالك غالط.

```
int a = 10;
int b = 20;

printf("%d", a - b);
```

إلا كنت باغي `30`، البرنامج ما عندوش compiler error، ولكن **المنطق غلط**.

---

# 3. واش C فيها `try/catch`؟

**لا. ❌**

C ما فيهاش:

```
try
catch
throw
```

بحال Java / C++ / Python.

بدل ذلك، C كتخليك **نتا تتعامل مع الأخطاء**.

والطرق المهمة هي:

```
1. Return values
2. NULL
3. EOF
4. errno
5. perror()
6. strerror()
7. assert()
8. ferror()
9. feof()
10. Input validation
11. Cleanup
```

دابا نشرحوهم وحدة بوحدة.

---

# 4. الطريقة الأولى: Return Values

هاد هي **الأساس**.

الفكرة:

```
function()
    ↓
كتدير العملية
    ↓
return value
    ↓
caller كيتحقق
    ↓
Success أو Error
```

مثلاً:

```
int divide(int a, int b)
{
    if (b == 0)
        return -1;

    return a / b;
}
```

ملي نديرو:

```
int result = divide(10, 2);
```

غادي يرجع:

```
5
```

ولكن:

```
int result = divide(10, 0);
```

غادي يرجع:

```
-1
```

إذن حنا قررنا:

```
-1 → error
>= 0 → success
```

⚠️ ولكن **C ما فرضاتش علينا `-1`**.

نتا اللي قررتي أن `-1` يمثل error.

---

# 5. علاش `return value` مهم؟

حيت function كتقدر تقول للـ caller:

```
"أنا نجحت"
```

ولا:

```
"أنا فشلت"
```

مثلاً:

```
int divide(int a, int b)
{
    if (b == 0)
        return -1;

    return a / b;
}
```

والـ caller:

```
int result = divide(10, 0);

if (result == -1)
{
    printf("Error\n");
}
else
{
    printf("%d\n", result);
}
```

يعني:

```
divide()
   ↓
return -1
   ↓
caller شاف -1
   ↓
عرف أن العملية فشلات
```

---

# 6. Error Codes

دابا نزيدو خطوة.

ممكن ما يكونش عندنا **error واحد فقط**.

مثلاً:

```
0  → SUCCESS
-1 → INVALID INPUT
-2 → FILE ERROR
-3 → MEMORY ERROR
```

مثلاً:

```
int check_age(int age)
{
    if (age < 0)
        return -1;

    if (age > 120)
        return -2;

    return 0;
}
```

هنا:

```
age = 25
→ 0
→ success

age = -5
→ -1
→ invalid age

age = 150
→ -2
→ age too large
```

هاد القيم كنسميوهم:

**Error Codes**

---

# 7. علاش ما نستعملوش أي رقم؟

خاصك تختار values ما يتعارضوش مع valid results.

مثلاً:

```
int get_age(void);
```

والـ valid values:

```
0 → valid
1 → valid
2 → valid
...
120 → valid
```

ما نقدرش نقولو:

```
0 = error
```

حيت `0` أصلاً age صحيح.

ممكن نستعملو:

```
-1 = error
```

حيت العمر ما كيكونش negative.

إذن:

```
-1      → error
0..120  → valid
```

هاد المبدأ مهم جداً:

> **Error value خاصها ما تتخلطش مع valid values.**

---

# 8. الطريقة الثانية: `NULL`

هادشي غادي يولي مهم بزاف ملي ندخلو لـ **pointers**.

بعض functions كترجع pointer.

مثلاً:

```
int *function(void);
```

إلا ما قدرتش ترجع pointer صالح، ممكن ترجع:

```
NULL
```

مثلاً `malloc()`:

```
int *p = malloc(10 * sizeof(int));

if (p == NULL)
{
    // allocation failed
}
```

هنا:

```
malloc()
   ↓
نجحات → address
فشلات → NULL
```

إذن:

**`NULL` غالباً كيعني "ما كاين حتى object/address صالح".**

---

# 9. الطريقة الثالثة: `EOF`

`EOF` معناها:

**End Of File**

كتستعمل مع بعض عمليات input/file.

مثلاً:

```
int c;

while ((c = getchar()) != EOF)
{
    putchar(c);
}
```

الفكرة:

```
كاين input
   ↓
قراه
   ↓
قراه
   ↓
قراه
   ↓
EOF
   ↓
وقف
```

⚠️ `EOF` ماشي بالضرورة معناها دائماً "error".

غالباً كتدل على **نهاية input**، وبعض functions كتستعملها كذلك للإشارة إلى failure.

---

# 10. `errno`

هنا كنبدأو ندخلو لواحد المستوى أهم.

بعض functions ديال C/POSIX ملي كتفشل، كتخلي **error code** فـ variable سميتها:

```
errno
```

كتحتاج:

```
#include <errno.h>
```

مثلاً:

```
operation
    ↓
failed
    ↓
errno = error code
```

ولكن مهم:

> **ماشي كل function كتستعمل `errno`.**

يعني ماشي أي function فـ C إلا فشلات خاصك تمشي تشوف `errno`.

---

# 11. `perror()`

`perror()` كتعاونك تطبع رسالة مفهومة مرتبطة بـ `errno`.

مثلاً:

```
FILE *file = fopen("data.txt", "r");

if (file == NULL)
{
    perror("fopen");
}
```

ممكن يخرج لك شي حاجة بحال:

```
fopen: No such file or directory
```

يعني:

```
fopen()
   ↓
failure
   ↓
errno
   ↓
perror()
   ↓
human-readable message
```

---

# 12. `strerror()`

`strerror()` حتى هي كتجيب message من error code.

مثلاً:

```
#include <string.h>
```

الفكرة:

```
error code
    ↓
strerror()
    ↓
string message
```

الفرق البسيط:

```
perror()     → كتطبع message مباشرة
strerror()   → كترجع لك string باش نتا تستعملها
```

مثلاً من ناحية الفكرة:

```
printf("%s\n", strerror(errno));
```

---

# 13. `assert()`

`assert()` مختلفة شوية.

كتستعملها بزاف فـ **debugging/development**.

مثلاً:

```
assert(x != NULL);
```

المعنى:

> أنا متأكد أن `x` ماشي `NULL`. إلا كان `NULL`، راه عندي programming bug.

خاص:

```
#include <assert.h>
```

إذن `assert()` ماشي replacement لـ normal error handling ديال user input أو file errors.

---

# 14. `ferror()`

مع files، ممكن تحتاج تعرف:

> واش القراءة فشلات بسبب error؟

هنا:

```
ferror(file)
```

كتساعدك تعرف واش وقع file error.

---

# 15. `feof()`

حتى هي مع files:

```
feof(file)
```

كتشوف:

> واش وصلنا لنهاية الملف؟

فرق مهم:

```
feof()   → وصلنا EOF؟
ferror() → وقع file error؟
```

ما تخلطهمش.

---

# 16. Input Validation

هادشي مهم بزاف.

قبل ما تستعمل input، **تحقق منه**.

مثلاً:

```
int age;

scanf("%d", &age);

if (age < 0)
{
    printf("Invalid age\n");
}
```

هنا كتدير:

```
Input
 ↓
Validation
 ↓
Valid? ── نعم → continue
   │
   لا
   ↓
handle error
```

هادشي كنسميوه:

**Input Validation**

---

# 17. Cleanup

إلا وقع error وسط البرنامج، ممكن تكون عندك resources خاصك تسدهم أو تحررهم.

مثلاً:

```
open file
   ↓
allocate memory
   ↓
operation fails
   ↓
cleanup
   ↓
return error
```

مثلاً:

```
FILE *file = fopen("data.txt", "r");

if (file == NULL)
{
    return -1;
}

/* ... */

fclose(file);
```

وملي غادي نتعلمو `malloc/free` غادي يبان هاد الموضوع أكثر.

---

# 18. الصورة الكاملة

دابا بغيتك تشوف Error Handling فـ C بهاد الشكل:

```
                 ERROR HANDLING IN C
                         │
        ┌────────────────┼────────────────┐
        │                │                │
   Return values      NULL             EOF
        │
        │
   Error Codes
        │
        └──────────────┐
                       │
                     errno
                       │
                ┌──────┴──────┐
                │             │
             perror()     strerror()
                
        Files:
        ├── ferror()
        └── feof()

        Development:
        └── assert()

        General:
        ├── validation
        └── cleanup
```

---

# 19. شنو خاصك تحفظ دابا؟

ما تحفظش التفاصيل كاملين مرة وحدة.

فـ **المرحلة الأولى** خاصك تفهم هاد الفكرة:

```
C ما عندهاش try/catch
        ↓
function كتبلغ caller بالنتيجة
        ↓
return value
        ↓
caller كيتحقق
        ↓
success / error
```

ومن بعد:

```
Return value
     ↓
Error codes
     ↓
NULL
     ↓
EOF
     ↓
errno
     ↓
perror / strerror
     ↓
file errors
     ↓
assert
     ↓
cleanup
```

**هاد هو الترتيب اللي غادي نتبعو معاك.**

ودابا بما أنك بغيتي **الفكرة كاملة قبل التمارين**، من هنا نقدر ندوزو للمرحلة التطبيقية: نبدأو بـ **`return values + error codes`** ونطلعوك بالتدريج حتى `errno/perror`.
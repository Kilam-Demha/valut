# 🧠 POINTERS IN C — من الصفر

## 1. قبل Pointer: خاصنا نفهمو Memory

أي variable كتكتبها فـ C، راه البرنامج كيحتاج يحط القيمة ديالها فـ **memory**.

مثلاً:

```
int x = 42;
```

تقدر تتخيلها هكذا:

```
RAM

Address       Value
┌────────┐
│  1000  │ ───────► 42
└────────┘
             ↑
             x
```

المهم هنا:

```
x = value
```

ولكن `x` عندها كذلك:

```
address = location ديالها فالـ memory
```

يعني عندنا جوج مفاهيم:

```
VALUE
ADDRESS
```

مثلاً:

```
x
│
├── value   = 42
└── address = 1000   ← مثال فقط
```

⚠️ العنوان `1000` غير مثال للتوضيح. العنوان الحقيقي كيحددو النظام.

---

# 2. شنو هو Address؟

الـ **address** هو المكان اللي متخزن فيه variable فـ memory.

تخيل RAM بحال عمارة:

```
Memory

1000 → [42]
1004 → [100]
1008 → [7]
```

كل box عندها:

```
Address
Value
```

إذا قلنا:

```
int x = 42;
```

فـ:

```
x       → القيمة 42
&x      → العنوان ديال x
```

وهنا دخلنا لأول operator مهم:

# `&`

`&` كتقول:

> **عطيني address ديال هاد variable.**

مثلاً:

```
int x = 42;
```

إلى درنا:

```
&x
```

فالنتيجة هي:

```
address ديال x
```

---

# 3. `&x` ماشي Value

هاد النقطة بغيتك تثبتها مزيان.

عندنا:

```
int x = 42;
```

إذن:

```
x   → 42
&x  → address ديال x
```

مثلاً افترضنا:

```
x = 42
&x = 1000
```

إذن:

```
x
↓
42

&x
↓
1000
```

ماشي:

```
&x = 42
```

❌

---

# 4. دابا شنو هو Pointer؟

Pointer هو **variable كيتخزن فيه address**.

مثلاً:

```
int x = 42;

int *p = &x;
```

عندنا دابا:

```
x
┌──────────┐
│    42    │
└──────────┘
    ↑
   1000
```

و:

```
p
┌──────────┐
│   1000   │
└──────────┘
```

إذن:

```
x → contains 42

p → contains address of x
```

هادشي هو Pointer.

---

# 5. علاش سميتو Pointer؟

حيت `p` ماشي كيشاور للقيمة مباشرة.

هو كيشاور لـ **المكان** اللي فيه القيمة.

```
p
│
│ contains address
▼
x
│
│ contains value
▼
42
```

يعني:

```
p → x → 42
```

وهنا عندك واحد النموذج ذهني مهم:

> **Pointer stores an address, and that address points to another object in memory.**

---

# 6. Syntax ديال Pointer

شوف:

```
int *p;
```

معناها:

> `p` هو pointer capable of pointing to an `int`.

مهم بزاف:

```
int *p
```

ماشي معناها:

> p هو integer.

بل:

> p هو pointer لـ integer.

---

# 7. علاش كتبنا `int *`؟

حيت C خاصها تعرف **نوع البيانات اللي كيشاور ليها pointer**.

مثلاً:

```
int *p;
char *q;
double *r;
```

معناهم:

```
p → int
q → char
r → double
```

علاش النوع مهم؟

حيت من بعد غادي يدخل فـ:

```
dereferencing
pointer arithmetic
memory access
```

وغادي نشوفو علاش بالتفصيل.

---

# 8. دابا دخلنا لـ `*` الثانية

عندنا:

```
int *p = &x;
```

هنا `*` فـ declaration كتقول:

> `p` هو pointer.

ولكن ملي نستعملو:

```
*p
```

فهنا المعنى تبدل.

`*p` كتقول:

> **سير للـ address اللي مخزن داخل p، وجيب القيمة اللي تما.**

هاد العملية سميتها:

# Dereferencing

---

## شوفها بالـ Memory

عندنا:

```
int x = 42;
int *p = &x;
```

نفترضو:

```
Address      Content

1000         42
2000         1000
```

إذن:

```
x  → 42

p  → 1000

*p → 42
```

علاش؟

حيت:

```
p
↓
1000
↓
memory[1000]
↓
42
```

إذن:

```
*p
```

كتجيب القيمة الموجودة فـ address اللي كيحمل `p`.

---

# 9. أهم 3 expressions

خاصك تفرق بينهم:

```
x
&x
*p
```

إلى:

```
int x = 42;
int *p = &x;
```

فالمعنى:

```
x
↓
42

&x
↓
address ديال x

p
↓
address ديال x

*p
↓
42
```

إذن:

```
x  == *p
```

من ناحية القيمة.

ولكن:

```
x  ≠ p
```

حيت:

```
x → value
p → address
```

---

# 10. Pointer يقدر يبدل variable

وهنا كتبدأ القوة الحقيقية ديال pointers.

عندنا:

```
int x = 42;
int *p = &x;
```

دابا:

```
*p = 100;
```

شنو وقع؟

ماشي غير بدلنا `p`.

حنا قلنا:

> مشي للـ address اللي داخل `p`، وبدل القيمة اللي تما إلى `100`.

يعني:

```
قبل:

x
┌────┐
│ 42 │
└────┘
  ↑
  p


بعد:

x
┌─────┐
│ 100 │
└─────┘
  ↑
  p
```

وبالتالي:

```
printf("%d", x);
```

غادي تلقى:

```
100
```

🔥 وهنا خاصك تفهم علاش Pointer مهم.

---

# 11. Pointer ماشي نسخة من variable

شوف الفرق:

```
int x = 42;
int y = x;
```

هنا:

```
x → 42
y → 42
```

ولكن `y` عندها نسخة مستقلة.

إذا:

```
y = 100;
```

يبقى:

```
x → 42
y → 100
```

أما:

```
int *p = &x;
```

فهنا:

```
p → x
```

و:

```
*p = 100;
```

كيبدل **x نفسها**.

---

# 12. علاش Pointers مهمين فـ C؟

حيت كيخليوك تتعامل مباشرة مع:

```
Memory
```

ومن هنا كيجيو بزاف ديال concepts:

```
Pointers
   ↓
Arrays
   ↓
Strings
   ↓
Functions
   ↓
Dynamic Memory
   ↓
Structs
   ↓
Linked Lists
   ↓
Trees
   ↓
Systems Programming
```

يعني Pointer ماشي topic صغير.

هو واحد من **أساسات C**.

---

# 13. Pointer و Array

هنا غادي نربطو مع اللي قريتي قبل.

عندنا:

```
int numbers[] = {10, 20, 30};
```

فالـ memory:

```
┌──────┬──────┬──────┐
│  10  │  20  │  30  │
└──────┴──────┴──────┘
   ↑
numbers
```

اسم array كيقدر يستعمل كـ address ديال أول element فـ expressions.

يعني تقريباً:

```
numbers
   ↓
&numbers[0]
```

وهنا غادي نكتاشفو من بعد العلاقة:

```
array ↔ pointer
```

ولكن **ما غاديش نقول لك array = pointer**، حيت هادي من الأخطاء المشهورة.

غادي نوصلو ليها بالتدريج.

---

# 14. Pointer و String

وهنا غادي تفهم علاش قلت لك Pointer غادي يقوي فهمك للـ String.

عندنا:

```
char name[] = "Ahmed";
```

Memory:

```
┌───┬───┬───┬───┬───┬────┐
│ A │ h │ m │ e │ d │ \0 │
└───┴───┴───┴───┴───┴────┘
  ↑
name
```

تقدر يكون عندك:

```
char *p = name;
```

دابا:

```
p
↓
'A'
```

و:

```
*p
```

تعطي:

```
'A'
```

و:

```
*(p + 1)
```

تعطي:

```
'h'
```

ولكن **ما غاديش نتعمقو فـ `p + 1` دابا** حتى نفهمو Pointer Arithmetic.

---

# 🧠 أهم Summary دابا

كتب هادشي فـ notebook:

```
VARIABLE
    ↓
has a VALUE
    ↓
stored somewhere in MEMORY
    ↓
that location has an ADDRESS
```

مثلاً:

```
int x = 42;
```

```
x   → value
&x  → address
```

Pointer:

```
int *p = &x;
```

```
p   → stores address of x
*p  → accesses value at that address
```

يعني:

```
        address
p ─────────────────► x
                     │
                     │ value
                     ▼
                    42
```

### القاعدة الذهبية:

```
&  → GET ADDRESS

*  → GO TO ADDRESS / DEREFERENCE
```

ولكن انتبه:

```
int *p;
```

الـ `*` هنا جزء من **declaration** وكتقول أن `p` pointer.

أما:

```
*p
```

فهنا **dereference**.

---

## 🧪 أول تمرين — بلا حل

بغيتك دابا غير تدير هاد البرنامج:

```
#include <stdio.h>

int main(void)
{
    int x = 50;
    int *p = &x;

    printf("x = ...\n");
    printf("&x = ...\n");
    printf("p = ...\n");
    printf("*p = ...\n");

    return 0;
}
```

### المطلوب منك:

1. عمر `%d` أو `%p` فالبلايص المناسبة.
2. قبل ما تشغلو، **توقع** شنو غادي يخرج.
3. شرح ليا بلسانك الفرق بين:
    - `x`
    - `&x`
    - `p`
    - `*p`

**ما تحتاجش تدخل دابا فـ pointer arithmetic ولا arrays.** بغيت نتأكد الأول أن هاد الأساس دخل ليك بالمنطق، ماشي بالحفظ.
chof 7aliyan ana wsalt string fi c bghit menak t3tini char7 pro o mofid o bts fi had topic

أكيد. بما أنك وصلتي دابا لـ **String فـ C**، غادي نعطيك واحد الشرح **Pro ولكن من الصفر**، وبالمنطق ديال C، باش ما تحفظش غير `strlen()` و `strcpy()` وإنما تفهم **شنو هو string فعلاً فـ memory**.

# 🧠 String فـ C — Pro Foundation

## 1. أول Concept: واش String type فـ C؟

**لا.**

هاد النقطة مهمة بزاف:

C ما فيهاش type اسمو:

```
string
```

عوض ذلك، الـ String فـ C هي:

> **مجموعة ديال `char` مخزنة بشكل متتابع فـ memory، وآخرها `'\0'`.**

مثلاً:

```
char name[] = "Ahmed";
```

فالـ memory عندنا:

```
       0      1      2      3      4      5
     ┌──────┬──────┬──────┬──────┬──────┬──────┐
     │  A   │  h   │  m   │  e   │  d   │ \0   │
     └──────┴──────┴──────┴──────┴──────┴──────┘
       char   char   char   char   char   char
```

إذن:

```
"Ahmed"
```

ماشي غير 5 characters.

هي:

```
'A' 'h' 'm' 'e' 'd' '\0'
```

يعني **6 bytes**، حيث `sizeof(char) = 1`.

---

# 2. علاش `'\0'` مهمة؟

`'\0'` هي:

> **Null character / String terminator**

وقيمتها العددية:

```
0
```

ولكن خاصك تفرق بينها وبين:

```
'0'
```

حيت:

```
'\0'  → character بقيمة 0
'0'   → character ديال الرقم صفر
```

مثلاً:

```
char x = '\0';
```

و:

```
char x = '0';
```

ماشي نفس الحاجة.

---

# 3. كيفاش C كتعرف فين سالات String؟

C ما عندهاش variable داخلي كيقول:

```
length = 5
```

إلى كان عندنا:

```
char name[] = "Ahmed";
```

والـ memory:

```
A h m e d \0
```

إلى بغيتي تقرا string، كتبدأ من أول character وكتدوز:

```
A → h → m → e → d → \0
```

ملي تلقى:

```
'\0'
```

كتقول:

> هنا سالات الـ string.

وهنا كيجي concept مهم جداً:

## String Length ≠ String Capacity

مثلاً:

```
char name[20] = "Ahmed";
```

عندك:

```
capacity = 20 bytes
length   = 5 characters
```

ولكن فعلياً:

```
A h m e d \0
```

والباقي unused.

---

# 4. `sizeof` vs `strlen`

هاد الفرق **لازم تفهمو مزيان**.

عندنا:

```
char name[] = "Ahmed";
```

### `sizeof(name)`

كتسول:

> شحال ديال bytes محجوزين للـ array كاملة؟

الجواب:

```
6
```

حيت:

```
A h m e d \0
```

---

### `strlen(name)`

كتسول:

> شحال character كاين قبل `'\0'`؟

الجواب:

```
5
```

إذن:

```
sizeof(name) = 6
strlen(name) = 5
```

### القاعدة الذهبية:

```
sizeof → memory size
strlen → string length
```

---

# 5. علاش `strlen()` ما كتحسبش `'\0'`؟

حيت `'\0'` ماشي جزء من **المحتوى النصي**.

مثلاً:

```
A h m e d \0
```

المحتوى:

```
Ahmed
```

عدد characters:

```
5
```

ولكن باش C تعرف فين تسالي، خاصها:

```
\0
```

إذن:

```
String length = 5
Memory required = 6 bytes
```

---

# 6. العلاقة بين String و Array

هادشي مهم جداً:

```
char name[] = "Ahmed";
```

هو فعلياً:

```
char name[] = {'A', 'h', 'm', 'e', 'd', '\0'};
```

يعني String فـ C مبنية فوق **character array**.

ولهذا تقدر تدير:

```
name[0]
name[1]
name[2]
```

مثلاً:

```
name[0] → 'A'
name[1] → 'h'
name[2] → 'm'
```

و:

```
name[5] → '\0'
```

---

# 7. String literal vs Character

خاصك تفرق بين:

```
'A'
```

و:

```
"A"
```

الأولى:

```
'A'
```

هي **character واحد**.

الثانية:

```
"A"
```

هي **string**.

فـ memory:

```
'A'

┌─────┐
│  A  │
└─────┘
```

أما:

```
"A"

┌─────┬─────┐
│  A  │ \0  │
└─────┴─────┘
```

يعني:

```
'A'  → char
"A"  → string
```

---

# 8. علاش كنستعملو `%s`؟

مع:

```
printf()
```

إلى بغيتي تطبع string:

```
printf("%s", name);
```

`%s` كتقول لـ `printf`:

> عطيني address ديال بداية string، وقرا characters حتى تلقى `'\0'`.

وهنا غادي نربطوها بالـ memory.

---

# 9. String والـ Address

عندنا:

```
char name[] = "Ahmed";
```

مثلاً افتراضياً:

```
Address       Value

1000          'A'
1001          'h'
1002          'm'
1003          'e'
1004          'd'
1005          '\0'
```

اسم الـ array:

```
name
```

فمعظم expressions كيتحول إلى:

```
address ديال أول element
```

يعني تقريباً:

```
name → 1000
```

و:

```
&name[0]
```

حتى هي:

```
1000
```

إذن:

```
printf("%s", name);
```

كتعطي `printf`:

```
address ديال 'A'
```

وهو كيبقى يقرا:

```
1000 → A
1001 → h
1002 → m
1003 → e
1004 → d
1005 → \0
```

ويتوقف.

---

# 10. وهنا كيبان علاش String مرتبطة بـ Pointer

مثلاً:

```
char *p = name;
```

دابا:

```
name
 ↓
┌───┬───┬───┬───┬───┬────┐
│ A │ h │ m │ e │ d │ \0 │
└───┴───┴───┴───┴───┴────┘
 ↑
 p
```

`p` كيشاور لأول character.

إذن:

```
*p
```

يعطي:

```
'A'
```

و:

```
*(p + 1)
```

يعطي:

```
'h'
```

وهنا String كتدخل مباشرة مع **Pointers + Arrays + Memory**.

---

# 11. أهم قاعدة فـ Strings

إلى بغيتي تفهم String بصفة Pro، حفظ هاد النموذج:

```
STRING
   │
   ├── characters
   │
   ├── contiguous memory
   │
   └── terminated by '\0'
```

يعني:

```
"Ahmed"

        String
          │
          ▼
┌─────┬─────┬─────┬─────┬─────┬─────┐
│ 'A' │ 'h' │ 'm' │ 'e' │ 'd' │ '\0'│
└─────┴─────┴─────┴─────┴─────┴─────┘
   0     1     2     3     4     5
```

---

# 12. أهم Functions ديال `<string.h>`

من بعد الأساس، هادو هما اللي خاصك تعرف:

### قياس

```
strlen()
```

### النسخ

```
strcpy()
strncpy()
```

### المقارنة

```
strcmp()
strncmp()
```

### الدمج

```
strcat()
strncat()
```

### البحث

```
strchr()
strstr()
```

### تقسيم/معالجة

كاينين functions أخرى حسب الحاجة.

ولكن **ما بغيتكش تحفظهم دابا**.

الأهم هو تفهم:

```
array
  ↓
char array
  ↓
'\0'
  ↓
string
  ↓
pointer
  ↓
memory
  ↓
<string.h>
```

---

# 13. أخطر نقطة: `'\0'` ماشي optional

شوف:

```
char a[] = {'A', 'h', 'm', 'e', 'd'};
```

هادشي **array ديال char** ولكن ماشي بالضرورة valid C string.

حيت ما عندكش:

```
'\0'
```

أما:

```
char a[] = {'A', 'h', 'm', 'e', 'd', '\0'};
```

فهنا عندك C string صحيحة.

---

# 14. علاش هادشي خطير؟

إلى درتي:

```
printf("%s", a);
```

وما كايناش `'\0'`، `printf` غادي يبقى يقرا memory من بعد `a` بحثاً على `'\0'`.

يعني:

```
A h m e d ? ? ? ? ? ...
          ↑
     memory أخرى
```

وهنا تقدر تدخل فـ:

> **Undefined Behavior**

وهذا من أهم أسباب bugs فـ C.

---

# 15. `char name[6]` vs `char name[5]`

مثلاً:

```
char name[6] = "Ahmed";
```

مزيان:

```
A h m e d \0
```

ولكن:

```
char name[5] = "Ahmed";
```

هنا خاصك تنتبه.

كاينين 5 characters:

```
A h m e d
```

ولكن string تحتاج كذلك:

```
\0
```

إذن خاصها **6 elements** باش تكون null-terminated بشكل طبيعي.

---

# 16. قاعدة مهمة جداً فـ C

إلى كانت عندك:

```
char str[] = "Hello";
```

فالـ compiler كيحسب:

```
5 characters
+
1 '\0'
=
6 chars
```

يعني:

```
sizeof(str)
```

تعطي:

```
6
```

بينما:

```
strlen(str)
```

تعطي:

```
5
```

---

# 🧠 الخلاصة الاحترافية

كتب عندك هاد الخلاصة:

```
C has no built-in string type.

A C string is:
a contiguous sequence of char
terminated by '\0'.
```

مثال:

```
char str[] = "Ahmed";
```

Memory:

```
A h m e d \0
```

```
strlen(str) → number of characters before '\0'
sizeof(str) → total memory occupied by the array
```

و:

```
'A'  → char
"A"  → string
```

و:

```
str
```

كيشير عملياً لأول element فـ expressions، لذلك String وPointers مرتبطين بقوة.

---

## 🧭 المسار اللي أنصحك به دابا

ما نمشيوش مباشرة لـ 20 function. ديرها بهاد الترتيب:

```
1. String concept
        ↓
2. '\0'
        ↓
3. char array
        ↓
4. sizeof vs strlen
        ↓
5. indexing
        ↓
6. address & pointer
        ↓
7. input/output strings
        ↓
8. <string.h>
        ↓
9. strcpy / strcmp / strcat...
        ↓
10. manual implementation
        ↓
11. common bugs
        ↓
12. String + pointers
```

**والـ Pro level الحقيقي** هو ملي تقدر تكتب بنفسك `strlen()` و `strcpy()` و `strcmp()` باستعمال loops وpointers، وتفهم علاش خدامين من الـ memory perspective.

chof ghadi t3tini sumury dial had lma3lomat li pro men getchar o scanf

أكيد. هادي **الخلاصة Pro** ديال المعلومات اللي خاصك تحتافظ بها من `scanf` و `getchar`، خصوصاً فـ C Strings وinput.

## 🧠 `scanf` vs `getchar`

### 1. `scanf("%s", str)`

`%s` كتقرا **word/token**، يعني كتوقف ملي تلقى whitespace:

```
space
tab
newline
```

مثلاً:

```
Ahmed Malik
```

مع `%s`:

```
Ahmed
```

هي اللي غادي تدخل للـ array، حيث `scanf("%s")` ما كتقراش السطر كامل.

والـ `scanf` كتضيف `'\0'` فالنهاية باش تخلي الناتج C string، بشرط يكون الـ buffer فيه المكان الكافي.

---

### 2. `getchar()`

`getchar()` كتقرا **character واحد كل مرة**.

مثلاً:

```
Ahmed
```

كتقرا:

```
A → h → m → e → d → \n
```

ومن بعد نقدروا نقرروا حنا شنو هي **condition ديال التوقف**.

مثلاً السطر كامل:

```
while (ch != '\n')
```

يعني:

> قرا character بـ character حتى يوصل Enter.

---

## 🔥 أهم Concept: علاش `getchar()` كترد `int`؟

رغم أنها كتقرا character، return type ديالها هو:

```
int
```

حيت خاصها تكون قادرة ترجع:

```
قيم characters
      +
EOF
```

يعني خاص **قيمة إضافية** باش تمثل حالة:

> ما بقا حتى input / وصلنا لنهاية الـ input.

لهذا كنستعملو عادة:

```
int ch;
```

ماشي:

```
char ch;
```

---

## ⚠️ الفرق بين `'\n'` و `'\0'` و `EOF`

هاد الثلاثة مهمين بزاف:

|القيمة|المعنى|
|---|---|
|`'\n'`|Newline / Enter|
|`'\0'`|نهاية C string|
|`EOF`|نهاية الـ input أو error|

مثلاً:

```
Ahmed\n
```

فالـ input:

```
A h m e d \n
          ↑
       Enter
```

ومن بعد إلا بغينا نخزنوه كـ C string، كنزيدو:

```
A h m e d \0
          ↑
     نهاية string
```

**مهم:** `'\n'` و `'\0'` ماشي نفس الحاجة.

---

## 🧠 الصورة الكبيرة

```
Keyboard/Input
      ↓
   getchar()
      ↓
   int ch
      ↓
 ┌───────────────┐
 │ character ?   │ → خزنو فـ array
 │ '\n' ?        │ → سالا السطر
 │ EOF ?         │ → سالا input
 └───────────────┘
      ↓
   '\0'
      ↓
C String complete
```

### ⭐ الخلاصة اللي خاصك تحفظها

> **`scanf("%s")` كتقرا word، أما `getchar()` كتقرا character واحد كل مرة. `getchar()` كترجع `int` باش تقدر تمثل قيم الـ characters وزيد عليها `EOF`. `'\n'` كيعني نهاية السطر، و`'\0'` كيعني نهاية الـ C string.**

هادشي دابا داخل فـ **Strings + Input**، وماشي غير حفظنا functions؛ فهمنا **علاش C مصمماهم بهاد الطريقة**.


آه، نخليو `buffer` من الصفر وبلا تعقيد. 👌

## 1. أولاً: شنو هي الذاكرة؟

ملي البرنامج خدام، كيكون عندو مساحة فالـ RAM يقدر يخزن فيها البيانات.

مثلاً:

```
char name[20];
```

البرنامج كيقول:

> عطيني بلاصة فـ memory فيها **20 `char`**.

تقدر تتخيلها بحال **20 خانات**:

```
name:

[0] [1] [2] [3] [4] [5] [6] [7] [8] [9]
[10][11][12][13][14][15][16][17][18][19]
```

كل خانة كتخزن `char` واحد.

---

## 2. دابا فين جا Buffer؟

كلمة **buffer** ماشي نوع جديد ديال data، وماشي function.

هي غير **اسم كنستعملوه لوصف مساحة من الذاكرة كنخزنو فيها data مؤقتاً**.

مثلاً:

```
char name[20];
```

إلا قلنا:

> "`name` هو buffer"

المعنى هو:

> هاد 20 خانات غادي نستعملوهم مؤقتاً باش نستقبلو ونخزنو characters.

---

## 3. علاش محتاجين Buffer أصلاً؟

شوف شنو كيوقع:

```
Keyboard
   ↓
Ahmed Malik
   ↓
   ؟
```

الـ CPU ما كيقدرش يخلي characters ديال input طايرين هكا 😂.

خاصنا **بلاصة نخزنو فيها**:

```
Keyboard
   ↓
Ahmed Malik
   ↓
┌────────────────────┐
│ A h m e d _ M a... │
└────────────────────┘
       ↑
     buffer
```

مثلاً:

```
char name[20];
```

هاد `name` هو المكان اللي غادي نستقبلو فيه الـ input.

---

## 4. علاش قلنا Buffer وما قلناش Array؟

هنا النقطة المهمة:

**Array** كتشرح لينا **كيفاش منظمة الذاكرة**:

```
char name[20];
```

هي array ديال 20 `char`.

أما **buffer** كتشرح لينا **الدور ديال هاد المساحة**:

> كنستعملوها باش نستقبلو/نخزنو data مؤقتاً.

يعني نفس `array` تقدر تكون buffer إلا استعملتيها لهاد الغرض.

مثلاً:

```
char name[20];
```

من ناحية structure:

> Array

من ناحية الدور:

> Buffer

---

## 5. دابا نرجعو للمشكل ديالنا

عندنا:

```
char name[20];
```

عندنا 20 خانات:

```
[0] [1] [2] ... [18] [19]
```

إلا المستخدم كتب:

```
Ahmed
```

كنخزنو:

```
[A][h][m][e][d][\0][ ][ ][ ]...
```

لاحظ:

```
A h m e d
```

= 5 characters

وزدنا:

```
\0
```

= خانة أخرى.

إذن:

```
5 + 1 = 6
```

والـ 14 خانات الباقية ما محتاجينهاش دابا.

---

## 6. فين كيوقع Buffer Overflow؟

دابا المستخدم كتب **20 characters**:

```
[A][B][C][D][E]...[S][T]
```

الـ buffer عامر كامل:

```
0                    19
↓                     ↓
[A][B][C] ... [S][T]
```

ولكن حنا بغينا نزيدو:

```
name[i] = '\0';
```

فين غادي نحطو `'\0'`؟

خاصو يمشي لـ:

```
name[20]
```

ولكن `name[20]` **ما كايناش**.

حيت آخر خانة هي:

```
name[19]
```

إذن البرنامج كيحاول يكتب **خارج المساحة اللي عطيناه**.

هادشي هو:

> **Buffer Overflow**

---

### 🧠 خزن هاد الصورة فدماغك

```
ARRAY
↓
20 خانات فالذاكرة

BUFFER
↓
نفس هاد المساحة، ولكن كنستعملوها
باش نستقبلو/نخزنو data مؤقتاً

BUFFER OVERFLOW
↓
البيانات فاتت الحجم المسموح به
وولات كتكتب خارج الـ buffer
```

**أهم جملة:**

الـ **buffer** ماشي حاجة مختلفة على الـ **array**؛ هو غير اسم كنوصفو بيه واحد المساحة فالذاكرة كنستعملوها مؤقتاً باش نستقبلو ولا نخزنو فيها البيانات.
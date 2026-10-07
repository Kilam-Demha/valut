

آه، فهمتك. بما أنك دابا فاهم **1D Array** وباغي تعرف شنو كاين من غيرها، غادي نبنيوها من الصفر وبالمنطق، ماشي غير syntax.

# Arrays فـ C من غير 1D

أول حاجة خاصك تعرف أن `array` ماشي غير:

```
int tab[5];
```

هاد الشي هو **1D array**.

منين كنزيدو dimensions، كنولّيو كنخزنو البيانات فـ مستويات:

```
1D → لائحة
2D → جدول
3D → مجموعة ديال الجداول
4D → مجموعة ديال مجموعات...
```

والفكرة الأساسية ديالهم كاملين وحدة:

> **Array = عناصر من نفس النوع مخزنين بشكل متتابع فـ الذاكرة.**

---

# 1. 2D Array — أهم واحد من بعد 1D

مثلاً عندنا جدول:

```
       column
       0   1   2
     ┌───┬───┬───┐
row 0│ 5 │ 8 │ 2 │
     ├───┼───┼───┤
row 1│ 7 │ 1 │ 9 │
     ├───┼───┼───┤
row 2│ 4 │ 6 │ 3 │
     └───┴───┴───┘
```

فـ C:

```
int tab[3][3];
```

المعنى:

```
3 rows
3 columns
```

يعني:

```
tab[0][0] = 5
tab[0][1] = 8
tab[0][2] = 2

tab[1][0] = 7
...
```

### فين كتستعمل؟

2D كتجي بزاف فـ:

- matrices
- tables
- grids
- games
- images
- maps
- spreadsheets
- linear algebra

مثلاً لعبة Tic-Tac-Toe:

```
X O X
O X O
X _ X
```

طبيعي جداً تمثلها بـ:

```
char board[3][3];
```

---

# 2. أهم حاجة تفهمها: 2D ماشي حاجة سحرية

هاد:

```
int tab[3][4];
```

تقدر تشوفها ذهنياً هكذا:

```
tab
 │
 ├── row 0 → [ ][ ][ ][ ]
 ├── row 1 → [ ][ ][ ][ ]
 └── row 2 → [ ][ ][ ][ ]
```

يعني **array ديال arrays**.

وهذه نقطة مهمة بزاف:

```
int tab[3][4];
```

هي:

> Array فيها 3 عناصر، وكل عنصر منها هو `int[4]`.

يعني:

```
int[3][4]

      ↓

3 × (int[4])
```

---

# 3. كيفاش كنـ iterate عليها؟

مع 1D كنتي كتحتاج loop وحدة:

```
for i
    tab[i]
```

مع 2D خاصك جوج:

```
for كل row
    for كل column
        استعمل العنصر
```

يعني منطقياً:

```
row 0 → column 0,1,2,3
row 1 → column 0,1,2,3
row 2 → column 0,1,2,3
```

وهنا غادي تبدا تشوف علاش nested loops مهمين فـ C.

---

# 4. Memory ديال 2D

هاد النقطة مهمة ليك خصوصاً حيث باغي تفهم C من الداخل.

مثلاً:

```
int tab[2][3];
```

منطقياً:

```
[ a ][ b ][ c ]
[ d ][ e ][ f ]
```

ولكن فـ memory، العناصر كيتخزنو **row-major**:

```
a → b → c → d → e → f
```

يعني ماشي memory فيها بالضرورة "جداول فوق بعضياتها".

هي memory متتابعة.

مثلاً إذا كان `int = 4 bytes`:

```
a    b    c    d    e    f
↓    ↓    ↓    ↓    ↓    ↓
100  104  108  112  116  120
```

وهنا غادي يبان ليك لاحقاً علاش **pointer + array** مرتبطين بشكل قوي.

---

# 5. 3D Array

من بعد 2D عندنا:

```
int tab[2][3][4];
```

هنا عندك:

```
2
 └── 3
      └── 4
```

تقدر تتخيلها كـ **جوج ديال 2D arrays**:

```
Layer 0

[ ][ ][ ]
[ ][ ][ ]
[ ][ ][ ]
[ ][ ][ ]

Layer 1

[ ][ ][ ]
[ ][ ][ ]
[ ][ ][ ]
[ ][ ][ ]
```

أو:

```
2 layers
×
3 rows
×
4 columns
```

---

# 6. فين كتستعمل 3D؟

ماشي أنك خاصك تحفظ syntax وتستعملها كل نهار.

كتبان فـ حالات بحال:

### Images

مثلاً image RGB:

```
height × width × channels
```

مثلاً:

```
image[height][width][3]
```

فين:

```
0 → Red
1 → Green
2 → Blue
```

### 3D games / simulations

مثلاً:

```
x × y × z
```

باش تمثل space ثلاثي الأبعاد.

### Scientific data

مثلاً:

```
time × row × column
```

---

# 7. 4D وما فوق؟

C تسمح ليك حتى:

```
int a[2][3][4][5];
```

وحتى أكثر.

ولكن هنا خاصك تفرق بين:

> **ممكن تقنياً**

و

> **مفيد عملياً**

ماشي حيث C كتسمح ليك بـ 7D array يعني خاصك تحفظ 7D arrays.

فـ المستوى ديالك دابا:

```
1D  ⭐⭐⭐⭐⭐
2D  ⭐⭐⭐⭐⭐
3D  ⭐⭐⭐
4D+ ⭐
```

التركيز الحقيقي ديالك يكون على **1D + 2D**، ومن بعد تفهم 3D كمفهوم.

---

# 8. Arrays ديال أنواع مختلفة

Array ماشي غير `int`.

تقدر:

```
char letters[5];
float prices[10];
double values[20];
```

حتى structs:

```
struct Student students[30];
```

وهنا غادي نوصلو لمفهوم مهم جداً:

> **Array ديال structures**

مثلاً:

```
students

[ Student ][ Student ][ Student ][ Student ]
```

وهذا مستعمل بزاف فـ البرامج الحقيقية.

---

# 9. Arrays داخل Arrays

خاصك كذلك تفهم أن arrays تقدر تكون nested:

```
int a[3][4];
```

هي:

```
array
 ├── array
 ├── array
 └── array
```

و:

```
int a[2][3][4];
```

هي:

```
array
 ├── array
 │    ├── array
 │    ├── array
 │    └── array
 │
 └── array
      ├── array
      ├── array
      └── array
```

هاد mental model مهم أكثر من حفظ:

```
a[x][y][z]
```

---

# 10. Arrays و pointers

وهنا غادي نربطها بالـ **Pointer** اللي غادي تدخل ليه دابا.

مع 1D:

```
int a[5];
```

عندك:

```
a
↓
[10][20][30][40][50]
```

وكل عنصر عندو address.

مع 2D:

```
int a[3][4];
```

كتولي:

```
a
 ↓
 ┌───────────────┐
 │ row 0         │
 ├───────────────┤
 │ row 1         │
 ├───────────────┤
 │ row 2         │
 └───────────────┘
```

وهنا pointer arithmetic غادي تولي مهمة جداً.

ولكن **ما نستعجلوش عليها دابا**. بما أنك داخل للـ pointers، غادي ناخدوها من الأساس ونشوفو بالضبط:

```
array
 ↓
address
 ↓
pointer
 ↓
pointer arithmetic
 ↓
2D array
 ↓
pointer to array
 ↓
dynamic 2D arrays
```

---

# 11. Static vs Dynamic Arrays

هاد distinction مهم بزاف.

دابا غالباً كتستعمل:

```
int a[10];
```

هاد الحجم معروف.

ولكن كاين dynamic allocation:

```
malloc
calloc
realloc
free
```

ومن بعد نقدروا نبنيو arrays الحجم ديالها كيتحدد أثناء execution.

مثلاً البرنامج يسول:

```
How many students?
```

المستخدم يقول:

```
150
```

والبرنامج يحجز memory لـ 150 عنصر.

هادشي غادي يكون مهم جداً فـ:

- pointers
- memory management
- data structures
- linked lists
- dynamic arrays

---

# 12. VLA — Variable Length Array

كاين حتى:

```
int n;

scanf("%d", &n);

int tab[n];
```

هنا الحجم كيتحدد runtime.

هاد النوع سميتو:

**VLA — Variable Length Array**

ولكن ما بغيتكش دابا تخلطو مع `malloc`.

خاصك تعرف الفرق:

```
int a[10]
    ↓
fixed-size array

int a[n]
    ↓
VLA

malloc(...)
    ↓
dynamic memory
```

غادي نفصلهم ملي ندوزو للـ memory/pointers.

---

# 13. Arrays و strings

وأنت دابا قريب كملتي موضوع strings.

خاصك تكون عندك الصورة:

```
char name[6]
```

يمكن تكون:

```
A l i c e \0
```

يعني string فـ C هي عملياً:

> **1D array of char + '\0' terminator**

وهذا علاش string مرتبطة مباشرة بالـ arrays.

---

# 14. Arrays و Data Structures

وهنا النقطة اللي مهمة لمسارك كامل.

Array نفسها تعتبر **data structure بسيطة**.

ومن بعد غادي تبني عليها:

```
Array
 │
 ├── Static Array
 │
 ├── Dynamic Array
 │
 ├── 2D Array
 │
 └── Array of Structs
       ↓
   Data Structures
       ↓
   Stack
   Queue
   Hash Table
   Heap
   ...
```

يعني ما تعتبرش 2D و3D مجرد "syntax إضافي".

خاصك تفهم:

> **كيفاش البيانات منظمة، فين مخزنة، كيفاش نوصل ليها، وشحال كتكلّف العملية.**

---

# شنو خاصك تكون عارف فـ Arrays دابا؟

أنا نقسمها ليك هكذا:

### المستوى 1 — خاصك تكون قوي فيه ⭐⭐⭐⭐⭐

```
1D Array
index
memory layout
sizeof
iteration
search
insert
delete
shift
traversal
```

### المستوى 2 — ضروري ⭐⭐⭐⭐⭐

```
2D Array
rows / columns
nested loops
memory layout
row-major order
passing 2D arrays to functions
```

### المستوى 3 — مهم ⭐⭐⭐⭐

```
Array + Pointer
pointer arithmetic
pointer to array
array of pointers
```

### المستوى 4 — من بعد ⭐⭐⭐⭐

```
Dynamic arrays
malloc
calloc
realloc
free
dynamic 2D arrays
```

### المستوى 5 — حسب الحاجة ⭐⭐

```
3D arrays
4D arrays
VLA
```

---

## والخلاصة اللي بغيتك تخرج بها

```
                 ARRAYS
                    │
          ┌─────────┴─────────┐
          │                   │
         1D                  2D
          │                   │
       [ ][ ]          [ ][ ][ ]
                         [ ][ ][ ]
                              │
                              ↓
                             3D
                              │
                              ↓
                       higher dimensions
```

ولكن الأهم:

```
1D Array
   ↓
Memory
   ↓
Pointer
   ↓
Pointer Arithmetic
   ↓
2D Array
   ↓
Dynamic Memory
   ↓
Dynamic Arrays
   ↓
Data Structures
```

**وبالنسبة ليك دابا، ما ندوزوش لـ 3D مباشرة.** أحسن progression هو: **نشرح 2D بعمق → نعطيك exercises بلا حلول → من بعد نربط 2D بالـ pointers → ثم dynamic arrays.** هكذا غادي تفهم C ماشي تحفظها.

ok atini exercices

أكيد. غادي نعطيك **تمارين 2D Arrays من السهل للصعيب**، وبلا حلول كما بغيتي. وما غاديش نعطيك commands/code جاهز؛ أنت اللي خاصك تخرج الـ logic والكود.

## 🟢 المستوى 1 — فهم 2D

### Exercice 1 — إنشاء وطباعة Matrix

أنشئ `int matrix[3][4]`.

- عمّرها بـ 12 أرقام.
- طبع جميع العناصر.
- استعمل `nested loops`.

**الهدف:** تفهم `row` و `column`.

---

### Exercice 2 — مجموع العناصر

عندك:

```
1  2  3
4  5  6
7  8  9
```

احسب مجموع جميع العناصر.

**الهدف:** traversal ديال 2D.

---

### Exercice 3 — أكبر عنصر

عندك Matrix بـ `4 × 4`.

لقَى أكبر قيمة فيها.

**ممنوع** تستعمل function جاهزة بحال `max`.

---

### Exercice 4 — أصغر عنصر

نفس الفكرة، ولكن لقَى أصغر عنصر.

وخدم بطريقة صحيحة حتى إلا كانت جميع القيم سالبة.

---

## 🟡 المستوى 2 — Rows / Columns

### Exercice 5 — مجموع كل Row

عندك:

```
1  2  3
4  5  6
7  8  9
```

خاصك تخرج:

```
Row 0 = 6
Row 1 = 15
Row 2 = 24
```

**ممنوع** تحسبهم manually.

---

### Exercice 6 — مجموع كل Column

نفس Matrix.

النتيجة خاصها تكون:

```
Column 0 = 12
Column 1 = 15
Column 2 = 18
```

---

### Exercice 7 — أكبر Row Sum

عندك Matrix:

```
2  8  1
4  3  9
7  2  5
```

احسب مجموع كل row، ومن بعد حدد **أي row عندو أكبر sum**.

ماشي غير أكبر element.

---

## 🟠 المستوى 3 — Search

### Exercice 8 — البحث عن عنصر

عندك Matrix `4 × 4`.

المستخدم يدخل رقم.

خاص البرنامج يقول:

```
Found
```

إلا كان موجود.

وإلا:

```
Not found
```

---

### Exercice 9 — عدد مرات ظهور رقم

مثلاً:

```
1  2  3
2  4  2
5  2  7
```

المستخدم يدخل:

```
2
```

البرنامج يحسب شحال من مرة ظهر.

النتيجة:

```
4
```

---

### Exercice 10 — Position ديال عنصر

المستخدم يدخل رقم.

إلا لقيتيه، طبع:

```
row = ?
column = ?
```

إلا كان الرقم كاين أكثر من مرة، قرر واش:

- تطبع أول occurrence فقط
- أو تطبع جميع positions

وخدم بالـ logic ديالك.

---

# 🔴 المستوى 4 — Manipulation

### Exercice 11 — Matrix Transpose

عندك:

```
1 2 3
4 5 6
```

حوّلها إلى:

```
1 4
2 5
3 6
```

هنا غادي تبدا تفهم مزيان العلاقة بين:

```
matrix[i][j]
```

و:

```
matrix[j][i]
```

---

### Exercice 12 — تبديل جوج Rows

عندك:

```
1 2 3
4 5 6
7 8 9
```

بدّل:

```
Row 0
```

مع:

```
Row 2
```

تصبح:

```
7 8 9
4 5 6
1 2 3
```

---

### Exercice 13 — تبديل جوج Columns

نفس Matrix.

بدّل:

```
Column 0
```

مع:

```
Column 2
```

---

## 🔥 المستوى 5 — Logic

### Exercice 14 — Main Diagonal

عندك Matrix مربعة:

```
1 2 3
4 5 6
7 8 9
```

استخرج:

```
1
5
9
```

ومن بعد احسب مجموعهم.

**مهم:** حاول تفهم علاش العناصر ديال diagonal عندها علاقة بـ `i` و `j`، ماشي غير تحفظ condition.

---

### Exercice 15 — Secondary Diagonal

نفس Matrix، ولكن استخرج:

```
3
5
7
```

وحسب مجموعهم.

---

### Exercice 16 — Matrix Symmetry

حدد واش Matrix مربعة **symmetric** ولا لا.

مثلاً:

```
1 2 3
2 4 5
3 5 6
```

هاد Matrix symmetric.

خاصك تكتشف القاعدة بنفسك.

---

## 🧠 المستوى 6 — Challenge

### Exercice 17 — Tic-Tac-Toe

مثل board ديال Tic-Tac-Toe بـ:

```
3 × 3
```

استعمل:

```
X
O
_
```

وخلي البرنامج يحدد واش:

- X ربح
- O ربح
- تعادل
- اللعبة مازال مستمرة

هاد التمرين مهم بزاف حيث غادي يجمع ليك:

```
2D Array
+
nested loops
+
conditions
+
logic
```

---

### Exercice 18 — Matrix Multiplication

عندك:

```
A = 2 × 3
B = 3 × 2
```

حسب:

```
C = A × B
```

هنا غادي تدخل لأول مرة فـ **منطق حقيقي ديال 2D arrays**.

---

### الترتيب اللي أنصحك به

ما تحاولش تحلهم كاملين مرة وحدة:

```
1 → 2 → 3 → 4
        ↓
5 → 6 → 7
        ↓
8 → 9 → 10
        ↓
11 → 12 → 13
        ↓
14 → 15 → 16
        ↓
17 → 18
```

**بدا غير بـ Exercice 1.** حلّو بوحدك، وصيفط ليا الكود ديالك، وأنا نراجع ليك **الـ logic قبل syntax** وما نعطيكش الحل مباشرة.
آه دابا فهمتك مزيان. بما أنك داخل فـ **Arrays** وباغي ترجع C بجدية، ما نبقاوش غير فـ`int arr[5]`. خاصك
تعرف **شنو كاين وراء الـarray**، خصوصاً الحوايج اللي كيستعملها واحد فاهم C مزيان.

# 🧠 أولاً: شنو هي Array بالضبط؟

الـArray هي مجموعة ديال عناصر **من نفس النوع** مخزنين **متتابعين فالذاكرة**.

مثلاً:

```
int arr[4] = {10, 20, 30, 40};
```

فالغالب الذاكرة غادي تكون بحال:

```
arr
 ↓
┌────┬────┬────┬────┐
│ 10 │ 20 │ 30 │ 40 │
└────┴────┴────┴────┘
  ↑
 address ديال أول عنصر
```

وكل `int` عندو الحجم ديالو، مثلاً إلا كان `int` = 4 bytes:

```
arr[0] → address + 0
arr[1] → address + 4
arr[2] → address + 8
arr[3] → address + 12
```

وهنا كيبدا السر ديال Arrays فـC.

---

# 1️⃣ Array عادية `1D`

```
int arr[5];
```

هادشي كيعني:

> حجز 5 ديال `int` متتابعين فالذاكرة.

تقدر تهيأها:

```
int arr[5] = {1, 2, 3, 4, 5};
```

أو:

```
int arr[] = {1, 2, 3, 4, 5};
```

هنا compiler هو اللي كيحسب الحجم.

---

# 2️⃣ Array جزئياً مهيأة

```
int arr[5] = {10, 20};
```

النتيجة:

```
10 20 0 0 0
```

العناصر اللي ما عطيتهمش قيمة كيتصفرو.

---

# 3️⃣ Array ديال `char`

هاد النوع مهم بزاف:

```
char name[6] = "Ahmed";
```

فالذاكرة:

```
'A' 'h' 'm' 'e' 'd' '\0'
```

لاحظ `\0`.

هادشي هو **null terminator**، وهو اللي كيحدد نهاية الـC string.

يعني:

```
char name[] = "Ahmed";
```

الحجم الحقيقي هو **6** ماشي 5.

---

# 4️⃣ Array ديال Strings

هنا كاينين طرق مختلفة.

### الطريقة الأولى: 2D char array

```
char names[3][20] = {
    "Ahmed",
    "Ali",
    "Youssef"
};
```

عندك:

```
names
 ├── Ahmed
 ├── Ali
 └── Youssef
```

كل اسم عندو مساحة ثابتة ديال 20 `char`.

هاد الطريقة مفيدة ملي بغيتي **عدد ثابت من strings وبأحجام محددة**.

---

# 5️⃣ 2D Array

مثلاً Matrix:

```
int matrix[3][4];
```

يعني:

**3 rows × 4 columns**

```
       col
       0   1   2   3
     ┌───┬───┬───┬───┐
row0 │   │   │   │   │
     ├───┼───┼───┼───┤
row1 │   │   │   │   │
     ├───┼───┼───┼───┤
row2 │   │   │   │   │
     └───┴───┴───┴───┘
```

والوصول:

```
matrix[1][2]
```

يعني row 1، column 2.

---

# 6️⃣ Multidimensional Arrays

C ما كتوقفش فـ2D.

تقدر:

```
int cube[3][4][5];
```

هادشي 3 dimensions.

وتقدر حتى أكثر:

```
int data[2][3][4][5];
```

ولكن فالتطبيقات العادية، منين كتكثر dimensions خاصك تسول راسك واش التصميم ديالك ما محتاجش structure أحسن.

---

# 🔥 7️⃣ Array و Pointer — الحاجـة المهمة

هادشي خاصك تفهمو مزيان:

```
int arr[5] = {10, 20, 30, 40, 50};
```

فمعظم expressions، `arr` كتتحول لـ pointer لأول عنصر:

```
arr
```

تقريباً:

```
&arr[0]
```

وبالتالي:

```
arr[2]
```

مكافئة لـ:

```
*(arr + 2)
```

يعني:

```
arr
 ↓
[10][20][30][40][50]
 ↑
 |
arr + 0

arr + 1 → 20
arr + 2 → 30
```

وهنا كتدخل قوة C الحقيقية.

---

# ⚠️ ولكن `array` ماشي `pointer`

هاد النقطة كيغلطو فيها بزاف:

```
int arr[5];
int *p;
```

**ماشي نفس النوع.**

`arr` هي Array.

`p` هو Pointer.

مثلاً:

```
p = arr;
```

مسموح.

ولكن:

```
arr = p;
```

❌ ممنوع.

حيت Array ما تقدرش تعاود تعطيها address جديد.

---

# 🧠 8️⃣ `sizeof` — حاجة مهمة جداً

شوف:

```
int arr[10];
```

تقدر تعرف الحجم:

```
sizeof(arr)
```

يعطيك **عدد bytes** اللي كتحجزهم الـarray.

وعدد العناصر:

```
sizeof(arr) / sizeof(arr[0])
```

مثلاً إلا كان `int = 4 bytes`:

```
sizeof(arr)      = 40
sizeof(arr[0])   = 4

40 / 4 = 10
```

هاد pattern مهم جداً فـC.

---

# 💀 9️⃣ ولكن `sizeof` مع Function فيها Trap

شوف:

```
void print(int arr[])
{
    printf("%zu\n", sizeof(arr));
}
```

هنا **ما غاديش يعطيك حجم الـarray الأصلية**.

علاش؟

حيت parameter:

```
int arr[]
```

كيتعامل فعلياً مع:

```
int *arr
```

يعني داخل function فقدتي معلومات الحجم.

لهذا كنكتبو:

```
void print(int arr[], size_t size)
```

ونمررو الحجم:

```
print(arr, 10);
```

هاد النقطة من علامات أن الواحد بدا فاهم C مزيان.

---

# 🔥 10️⃣ Array ديال Pointers

تقدر يكون عندك:

```
int *arr[5];
```

فرق كبير بينها وبين:

```
int (*arr)[5];
```

الأولى:

```
int *arr[5]
```

هي:

> Array فيها 5 pointers لـ`int`.

أما الثانية:

```
int (*arr)[5]
```

هي:

> Pointer كيشاور لـArray فيها 5 `int`.

**الأقواس هنا مهمين جداً.**

هاد النوع ديال syntax كيدخلنا لعالم C المتقدم.

---

# 🔥 11️⃣ Pointer to Array

مثلاً:

```
int matrix[3][4];

int (*p)[4] = matrix;
```

`p` هنا ماشي pointer لـ`int` عادي.

هو pointer لـ:

```
array of 4 integers
```

وهذا مهم جداً مع 2D arrays.

---

# 🧠 12️⃣ Array Parameters و 2D Arrays

مثلاً:

```
void printMatrix(int matrix[][4], int rows)
```

الـ`4` هنا مهمة.

C خاصو يعرف **عدد الأعمدة** باش يحسب العنوان ديال:

```
matrix[i][j]
```

مثلاً:

```
matrix[2][3]
```

باش يعرف فين كاين هاد العنصر فالذاكرة.

---

# 🚀 13️⃣ Variable Length Arrays — VLA

كاين حتى:

```
int n;

scanf("%d", &n);

int arr[n];
```

هنا الحجم معروف **وقت التشغيل** ماشي وقت compilation.

هادشي سميتو:

**Variable Length Array**

ولكن خاص تعرف أن دعم VLA مرتبط بمعيار C/compiler والإعدادات، وماشي دائماً الاختيار الأفضل خصوصاً فالكود portable أو embedded.

---

# 💀 14️⃣ Dynamic Array

هنا كنخرجو من الـarray الثابتة:

```
int arr[100];
```

ونمشيو للـHeap:

```
int *arr = malloc(n * sizeof *arr);
```

هنا `n` تقدر تكون معروفة وقت التشغيل.

ومن بعد:

```
free(arr);
```

هاد الموضوع مهم بزاف فـC.

وخصوصاً Embedded Systems، خاصك تفهم **stack vs heap** مزيان قبل ما تعتمد على `malloc`.

---

# 🔥 15️⃣ Flexible Array Member

هاد وحدة advanced بزاف:

```
struct Packet
{
    int size;
    char data[];
};
```

`data[]` هنا ماشي Array عادية.

هادشي سميتو:

**Flexible Array Member**

كتقدر تستعملها باش تدير structure فيها data variable-size بطريقة متقدمة.

---

# 🧠 16️⃣ Arrays والـMemory Layout

مثلاً:

```
int a[3] = {10, 20, 30};
```

العناصر متتابعين:

```
a[0] a[1] a[2]
 ↓    ↓    ↓
10   20   30
```

ولكن:

```
int *p = a;
```

و:

```
p + 1
```

ما كيزيدش غير `1 byte`.

كيقفز لحجم `int`.

إلا كان `int = 4 bytes`:

```
p       → address 1000
p + 1   → address 1004
p + 2   → address 1008
```

هادشي هو **pointer arithmetic**.

---

# ☠️ 17️⃣ Out of Bounds

واحد من أخطر الأخطاء:

```
int arr[5];

arr[5] = 100;
```

❌ غلط.

آخر index هو:

```
0 1 2 3 4
```

`arr[5]` خارج الـarray.

C غالباً ما غاديش يوقفك ويقولك "راك غلطتي".

وهنا كاين الخطر:

**Undefined Behavior.**

---

# 🧠 18️⃣ Array of Structs

وهذه مهمة جداً فالمشاريع:

```
struct Student
{
    char name[50];
    int age;
};

struct Student students[100];
```

هنا عندك **100 Student**.

مثلاً:

```
students[0].age = 20;
students[1].age = 22;
```

هاد الشكل غادي تحتاجو بزاف فـCRUD والمشاريع.

---

# 🔥 شنو خاصك تكون فاهم كـC Developer؟

إلا بغيتي نقولو **Array mastered**، خاصك تكون قادر تفهم وتخدم هاد السلسلة:

```
Array
 ↓
Indexing
 ↓
Memory layout
 ↓
sizeof
 ↓
Array → Pointer decay
 ↓
Pointer arithmetic
 ↓
Arrays + Functions
 ↓
2D Arrays
 ↓
Array of pointers
 ↓
Pointer to array
 ↓
Strings
 ↓
Dynamic arrays
 ↓
malloc / realloc / free
 ↓
Arrays + structs
```

وأنا كنقترح عليك **ما نمشيوش مباشرة لـ`malloc`**.

دابا بما أنك باغي تمارين بزاف، أحسن مرحلة هي:

### 🔥 Array Mastery — 15 تمارين

ندير لك تمارين فيهم بالتدريج:

**Arrays → Functions → Pointers → 2D Arrays → Strings → Dynamic Arrays**

ولكن **ما نعطيكش 15 مرة وحدة مع الحل**. نعطيك الـ15 challenges بلا حلول، وانت تخدمهم، ومنين توقع فشي وحدة نحللوها مع بعضنا. هكا غادي ترجع C فعلاً، ماشي غير تقرا عليها.
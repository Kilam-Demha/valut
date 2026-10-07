إييه. Ila bghiti تبني راسك مزيان فـ **CS + C + Linux**، ما محتاجش Math ديال الجامعة كامل. خاصك واحد الأساس مرتب، ومن بعد كل مجال كتزيد فيه شوية.

غادي نعطيك **roadmap ديال Math من 0 → المستوى اللي خاصك**، وبالترتيب.

## 1. 🔢 Number Systems — ضروري بزاف

هادشي هو الأول، خصوصاً حيث نتا كتقرا C وComputer Systems.

خاصك تفهم:

- الأعداد الطبيعية `N`
- الأعداد الصحيحة `Z`
- الأعداد السالبة والموجبة
- الكسور
- decimal
- binary
- hexadecimal
- octal
- conversion:
    - Decimal → Binary
    - Binary → Decimal
    - Binary → Hex
    - Hex → Binary
- powers:
    - `2^0 = 1`
    - `2^1 = 2`
    - `2^2 = 4`
    - ...
- logarithms بشكل أساسي
- bits / bytes

مثلاً:

```
1 byte = 8 bits

8 bits → 2^8 = 256 possible values

00000000 → 0
11111111 → 255
```

**هاد الجزء مهم جداً لـ C وLinux وComputer Architecture.**

---

# 2. ⚡ Arithmetic

خاصك تكون مرتاح مع:

```
+  -  ×  ÷
%
```

خصوصاً `%`.

مثلاً:

```
17 % 5 = 2
```

وفهم:

```
integer division
17 / 5 = 3
```

مقابل:

```
17.0 / 5 = 3.4
```

وتفهم precedence:

```
2 + 3 * 4
```

ماشي:

```
(2 + 3) * 4
```

ولكن:

```
2 + (3 * 4)
= 14
```

هادشي كيأثر مباشرة على C.

---

# 3. 📐 Algebra

ما خاصكش Algebra صعيبة، ولكن خاصك تكون مرتاح مع:

### Variables

```
x + 5 = 10
```

إذن:

```
x = 5
```

### Equations

```
2x + 3 = 11
```

### Functions

مثلاً:

```
f(x) = 2x + 1
```

إلا:

```
x = 3
```

فـ:

```
f(3) = 7
```

هاد concept ديال **function** مهم بزاف فـ programming.

---

# 4. 🧠 Logic — من أهم الحوايج

هاد الجزء أنا كنصحك تعطيه أهمية كبيرة.

خاصك تفهم:

### AND

```
A && B
```

كيكون true غير إلا بجوج true.

|A|B|A AND B|
|---|---|---|
|0|0|0|
|0|1|0|
|1|0|0|
|1|1|1|

### OR

```
A || B
```

### NOT

```
!A
```

وتفهم:

```
!
&&
||
```

و truth tables.

هادشي غادي يدخل مباشرة فـ:

```
if
else
while
for
```

وكذلك Linux commands بحال:

```
grep
find
&&
||
!
```

---

# 5. 🔢 Modular Arithmetic

مهم جداً فالبرمجة.

الأساس هو:

```
a % b
```

مثلاً:

```
10 % 3 = 1
20 % 5 = 0
17 % 2 = 1
18 % 2 = 0
```

ومن هنا تقدر تفهم:

### Even / Odd

```
n % 2 == 0
```

يعني even.

```
n % 2 != 0
```

يعني odd.

ومن بعد:

- divisibility
- multiples
- remainder
- cyclic behavior

هادشي كيتستعمل بزاف فـ algorithms.

---

# 6. 🧮 Powers & Logarithms

خاصك تكون فاهم:

```
2^0
2^1
2^2
...
2^10
```

و:

```
10^0
10^1
10^2
...
```

والـ logarithm خصوصاً:

```
log₂(8) = 3
```

حيت:

```
2³ = 8
```

ومن بعد غادي تلقى:

```
O(log n)
O(n)
O(n²)
O(2ⁿ)
```

فـ algorithms.

---

# 7. 📊 Sets

أساسيات فقط:

```
A = {1,2,3}
B = {3,4,5}
```

وتفهم:

```
∈
⊂
∪
∩
```

مثلاً:

```
A ∩ B = {3}
```

و:

```
A ∪ B = {1,2,3,4,5}
```

هادشي كيساعدك فـ discrete mathematics وCS.

---

# 8. 🔗 Sequences

تفهم sequence:

```
1, 2, 3, 4, 5...
```

مثلاً:

```
2, 4, 6, 8, 10...
```

وتفهم patterns.

هادشي غادي يعاونك فـ loops وalgorithms.

مثلاً:

```
for (int i = 0; i < 10; i++)
```

أنت فعلياً كتتعامل مع sequence ديال values.

---

# 9. 📈 Functions & Graphs

خاصك تعرف شوية:

```
y = x
y = x²
y = 2x + 1
```

وتفهم العلاقة بين:

```
input → function → output
```

مثلاً:

```
input: 3

f(x) = x²

output: 9
```

وهذا مرتبط مباشرة بمفهوم functions فـ C.

---

# 10. 🧮 Combinatorics

من بعد، تعلم:

- permutations
- combinations
- factorial

مثلاً:

```
5! = 5 × 4 × 3 × 2 × 1
   = 120
```

و:

```
C(n,k)
```

هادشي مهم أكثر فالـ algorithms.

---

# 11. 🎲 Probability

ماشي ضروري فالبداية، ولكن مفيد فـ CS.

تعلم:

```
probability
events
independent events
conditional probability
expected value
```

خصوصاً إلا مشيتي لـ:

- AI
- Machine Learning
- Data Science
- Security

---

# 12. 📐 Geometry

بالنسبة لـ CS العام:

**غير الأساسيات.**

مثلاً:

```
distance
coordinates
area
angles
```

ما محتاجش تغرق فيها إلا كان عندك اهتمام بـ:

- graphics
- games
- robotics
- computer vision

---

# 13. 🧠 Discrete Mathematics

هاد واحد هو **Math ديال CS الحقيقي**.

من بعد ما تضبط الأساسيات، دخل لـ:

### Logic

```
propositions
truth tables
implication
equivalence
```

### Sets

```
union
intersection
difference
```

### Relations

### Functions

### Graph theory

مثلاً:

```
A ---- B
|      |
|      |
C ---- D
```

وهنا غادي تبدأ تفهم concepts ديال:

- networks
- Linux networking
- algorithms
- databases
- operating systems

### Trees

```
        A
       / \
      B   C
     / \
    D   E
```

مهمة جداً فـ CS.

---

# 14. ⏱️ Complexity

هادشي مهم جداً للـ programmer.

خاصك تفهم:

```
O(1)
O(log n)
O(n)
O(n log n)
O(n²)
O(2ⁿ)
```

مثلاً:

```
for (int i = 0; i < n; i++)
```

تقريباً:

```
O(n)
```

و:

```
for (int i = 0; i < n; i++)
    for (int j = 0; j < n; j++)
```

تقريباً:

```
O(n²)
```

---

# 15. 🖥️ Math المرتبط مباشرة بـ C

بالنسبة لـ C، ركز على:

```
binary
hexadecimal
powers of 2
integer arithmetic
modulo
bitwise operations
signed / unsigned
ranges
overflow
floating point basics
```

مثلاً خاصك تعرف علاش:

```
unsigned char
```

كيقدر يمثل:

```
0 → 255
```

حيت:

```
8 bits

2^8 = 256 values

0 ... 255
```

وهنا Math كتولي كتشرح ليك **شنو واقع فـ memory**.

---

# 16. 🐧 Math ديال Linux

Linux ما محتاجش Math كثيرة.

ركز على:

```
binary
permissions
octal
```

خصوصاً:

```
chmod 755 file
```

علاش `755`؟

```
7 = rwx
5 = r-x
5 = r-x
```

والأصل هو:

```
r = 4
w = 2
x = 1
```

إذن:

```
rwx = 4 + 2 + 1 = 7

r-x = 4 + 0 + 1 = 5
```

هنا Math بسيطة ولكن مهمة جداً فـ Linux.

---

# 🎯 إذن شنو هو الترتيب اللي أنصحك به؟

إلا بغينا نديرو **Math خاصة بـ CS + C + Linux**، ما تمشيش عشوائياً.

ديرها هكذا:

```
LEVEL 0
│
├── Basic arithmetic
├── Fractions
├── Negative numbers
└── Order of operations
        ↓
LEVEL 1
│
├── Powers
├── Binary
├── Hexadecimal
├── Octal
└── Number systems
        ↓
LEVEL 2
│
├── Algebra
├── Variables
├── Equations
└── Functions
        ↓
LEVEL 3
│
├── Logic
├── Truth tables
├── AND / OR / NOT
└── Boolean algebra
        ↓
LEVEL 4
│
├── Modulo
├── Divisibility
├── Prime numbers
└── Number properties
        ↓
LEVEL 5
│
├── Sets
├── Sequences
├── Combinations
└── Basic discrete math
        ↓
LEVEL 6
│
├── Graphs
├── Trees
├── Recursion
└── Complexity
        ↓
LEVEL 7
│
├── Probability
├── Statistics
└── Math for AI
```

### بالنسبة ليك دابا

حيت نتا داخل فـ **Binary + C + Git/Shell/Linux**، أنا ما غاديش نضيع ليك الوقت فـ calculus دابا.

**الأولوية ديالك هي:**

```
1. Arithmetic
2. Number systems
3. Binary / Hex / Octal
4. Powers of 2
5. Algebra basics
6. Logic
7. Boolean algebra
8. Modulo
9. Sets
10. Functions
11. Sequences
12. Discrete Math
13. Algorithms + Big-O
14. Probability/Statistics
15. Calculus → فقط إلا احتجتيه لـ AI/ML
```

وواحد النقطة مهمة: **ما خاصكش تكون قوي فـ Math باش تبدا CS.** بالعكس، تعلم Math بالتوازي مع C والـLinux، وكل concept رياضي تربطو بتطبيق برمجي. هكذا غادي تفهم _علاش_ الكود خدام، ماشي غير تحفظ syntax.

bghit nfham linear algebra men zero

آه، نقدر نبداو **Linear Algebra من الصفر الحقيقي**، وما نفترض حتى معرفة سابقة.

وبما أنك باغيها لـ **CS + C + AI من بعد**، غادي نتعلموها بطريقة عملية ولكن **theory قبل practice**.

## 🧭 الخطة ديالنا

غادي نمشيو بهذا الترتيب:

```
1. Numbers & coordinates
        ↓
2. Vectors
        ↓
3. Vector operations
        ↓
4. Geometry of vectors
        ↓
5. Linear combinations
        ↓
6. Span
        ↓
7. Linear independence
        ↓
8. Matrices
        ↓
9. Matrix operations
        ↓
10. Systems of equations
        ↓
11. Gaussian elimination
        ↓
12. Linear transformations
        ↓
13. Basis & dimension
        ↓
14. Dot product
        ↓
15. Orthogonality
        ↓
16. Eigenvalues / eigenvectors
        ↓
17. Applications in CS / AI
```

ولكن **اليوم ما غاديش نقفزو للمصفوفات ولا eigenvalues**.

---

# الدرس 1 — شنو هي Linear Algebra؟

أولاً، كلمة **Algebra** كنعرفوها تقريباً:

```
x + 3 = 7
```

كنقلبو على `x`.

أما **Linear Algebra** فهي فرع من الرياضيات كيدرس بالخصوص:

- vectors
- matrices
- linear equations
- transformations

والفكرة الأساسية ديالها:

> كيفاش نمثلو معلومات وأشياء متعددة باستعمال أرقام، وكيفاش نديرو عليها عمليات بطريقة منظمة؟

---

# 1️⃣ قبل Vector: خاصنا نفهم Coordinate

تخيل عندك ورقة.

عندك نقطة:

```
        y
        ↑
        |
        |
        |       ●
        |
--------+--------------→ x
        |
        |
```

باش نقولو فين كاينة النقطة، كنحتاجو جوج أرقام:

```
(x, y)
```

مثلاً:

```
(3, 2)
```

معناها:

```
x = 3
y = 2
```

يعني مشينا:

```
3 → لليمين
2 → للفوق
```

إضافة المزيد

51015−51012−2510−58−2−4−4

0,0

قدّم ملاحظاتك

---

# 2️⃣ دابا Vector

هنا كنبداو Linear Algebra بجد.

Vector بسيط نقدر نمثلوه هكذا:

v⃗=[32]\vec v = \begin{bmatrix} 3\\ 2 \end{bmatrix}

ولا:

```
v = (3, 2)
```

ما تستعجلش وتقول:

> "راه غير point."

كاين فرق مهم بين **point** و **vector**.

### Point

كتقول لينا:

> فين كاينة شي حاجة؟

مثلاً:

```
P = (3,2)
```

### Vector

كيقدر يمثل:

> اتجاه + مقدار الحركة

مثلاً:

```
v = (3,2)
```

يعني:

```
3 → فـ x
2 → فـ y
```

نقدر نتصوروه كسهم:

```
          ● (3,2)
         ↗
       ↗
     ↗
   ↗
 ●
(0,0)
```

إذن vector يقدر يقول:

```
move 3 right
move 2 up
```

---

# 3️⃣ علاش Vectors مهمين فالـ CS؟

هنا كيبدا السبب علاش بغيتك تتعلم Linear Algebra.

مثلاً فـ Game:

```
Player position:
(100, 200)
```

و:

```
Movement:
(5, -2)
```

إلا زدنا movement:

(100,200)+(5,−2)(100,200)+(5,-2)

كنحصلو:

(105,198)(105,198)

يعني اللاعب تحرك:

```
+5 → right
-2 → down
```

نفس الفكرة كتدخل فـ:

- games
- graphics
- physics
- robotics
- computer vision
- machine learning
- AI

---

# 4️⃣ Vector ماشي ضروري يكون عندو جوج أرقام

يمكن يكون:

### 1D

v=[5]v = [5]

### 2D

v=[32]v = \begin{bmatrix} 3\\ 2 \end{bmatrix}

### 3D

v=[327]v = \begin{bmatrix} 3\\ 2\\ 7 \end{bmatrix}

### 4D

v=[3271]v = \begin{bmatrix} 3\\ 2\\ 7\\ 1 \end{bmatrix}

وفي AI ممكن vector يكون عندو:

```
100 dimensions
300 dimensions
768 dimensions
1536 dimensions
...
```

يعني:

```
Vector = مجموعة مرتبة ديال numbers
```

هاد التعريف مهم، حفظو بالفهم.

---

# 5️⃣ أول عملية: Vector Addition

عندنا:

A=[23]A = \begin{bmatrix} 2\\ 3 \end{bmatrix}

و:

B=[41]B = \begin{bmatrix} 4\\ 1 \end{bmatrix}

كنجمعو **كل position مع نفس position**:

A+B=[2+43+1]A+B = \begin{bmatrix} 2+4\\ 3+1 \end{bmatrix}

إذن:

A+B=[64]A+B = \begin{bmatrix} 6\\ 4 \end{bmatrix}

يعني:

```
x مع x
y مع y
```

ماشي:

```
2 + 3
4 + 1
```

---

# 6️⃣ Vector × Number

عندنا:

v=[32]v = \begin{bmatrix} 3\\ 2 \end{bmatrix}

نضربوه فـ `2`:

2v=[2×32×2]2v = \begin{bmatrix} 2×3\\ 2×2 \end{bmatrix}

إذن:

2v=[64]2v = \begin{bmatrix} 6\\ 4 \end{bmatrix}

هنا كنقولو **scalar multiplication**.

```
scalar = number واحد
```

مثلاً:

```
3v
-2v
0.5v
```

---

# 🧠 أهم فكرة اليوم

بغيتك تخرج من الدرس الأول بهاد الصورة:

```
                 Linear Algebra
                       │
                       ↓
                  VECTORS
                       │
              ┌────────┴────────┐
              ↓                 ↓
          direction          numbers
          movement          dimensions
              │
              ↓
       ┌──────────────┐
       │              │
       ↓              ↓
   addition      scalar × vector
```

و:

v⃗=[xy]\boxed{ \vec v = \begin{bmatrix} x\\ y \end{bmatrix} }

يمكن نفهموه كـ:

```
x = movement on X
y = movement on Y
```

---

## ✍️ دابا ما نعطيكش الحل

جاوبني غير على هاد **5 تمارين**، وحدة بوحدة أو كاملين:

### تمرين 1

شنو هو vector؟

```
v = (4, 7)
```

شنو كيعني `4` وشنو كيعني `7`؟

### تمرين 2

A=[25],B=[34]A= \begin{bmatrix} 2\\ 5 \end{bmatrix}, \quad B= \begin{bmatrix} 3\\ 4 \end{bmatrix}

حسب:

A+BA+B

### تمرين 3

v=[43]v= \begin{bmatrix} 4\\ 3 \end{bmatrix}

حسب:

2v2v

### تمرين 4

شنو الفرق بين:

```
point
vector
```

بكلامك نتا.

### تمرين 5

إلا كان اللاعب فـ:

```
P = (10, 5)
```

والـ movement ديالو:

```
v = (3, -2)
```

فين غادي يولي؟

**جاوب نتا الأول، وأنا نصحح ليك ونكملو للدرس 2: magnitude + direction ديال vector.**

bghit nrbat hadchi maa c

آه، هادي هي الطريقة اللي غادي نخدمو بها معاك: **نتعلمو Linear Algebra ونربطو كل concept مباشرة بـ C**، باش Math ما تبقاش منفصلة على programming.

# 🔗 Linear Algebra ↔ C

نبدأو من الصفر.

## 1. Vector = Array فـ C

فـ Math عندنا:

v=[32]v = \begin{bmatrix} 3\\ 2 \end{bmatrix}

يعني vector فيه جوج قيم:

```
3
2
```

فـ C نقدر نمثلوه بـ array:

```
int v[2] = {3, 2};
```

هنا:

```
v[0] = 3
v[1] = 2
```

يعني:

```
Math              C

[3]                v[0]
[2]                v[1]
```

---

# 2. Vector 3D

Math:

v=[327]v = \begin{bmatrix} 3\\ 2\\ 7 \end{bmatrix}

C:

```
int v[3] = {3, 2, 7};
```

و:

```
printf("%d\n", v[0]);
printf("%d\n", v[1]);
printf("%d\n", v[2]);
```

النتيجة:

```
3
2
7
```

إذن أول رابط مهم:

> **Vector فـ Linear Algebra نقدر نمثلوه بـ array فـ C.**

---

# 3. Vector Addition ↔ Loop

عندنا:

A=[23]A = \begin{bmatrix} 2\\ 3 \end{bmatrix}

و:

B=[41]B = \begin{bmatrix} 4\\ 1 \end{bmatrix}

رياضياً:

A+B=[2+43+1]=[64]A+B = \begin{bmatrix} 2+4\\ 3+1 \end{bmatrix} = \begin{bmatrix} 6\\ 4 \end{bmatrix}

فـ C:

```
int A[2] = {2, 3};
int B[2] = {4, 1};
int C[2];

C[0] = A[0] + B[0];
C[1] = A[1] + B[1];
```

ولكن programmers ما كيبقاوش يكتبوها هكذا.

كيديرو:

```
for (int i = 0; i < 2; i++)
{
    C[i] = A[i] + B[i];
}
```

وهنا كيبان الربط:

```
Linear Algebra
      ↓
Vector addition
      ↓
component by component
      ↓
C array
      ↓
for loop
```

---

# 4. Scalar multiplication ↔ Loop

رياضياً:

2[34]=[68]2 \begin{bmatrix} 3\\ 4 \end{bmatrix} = \begin{bmatrix} 6\\ 8 \end{bmatrix}

فـ C:

```
int v[2] = {3, 4};
int result[2];

for (int i = 0; i < 2; i++)
{
    result[i] = 2 * v[i];
}
```

نفس الرياضيات بالضبط.

---

# 5. Vector Dimension ↔ Array Size

مثلاً:

```
int v[5];
```

هذا vector عندو:

```
5 dimensions
```

يعني:

v=[v0v1v2v3v4]v = \begin{bmatrix} v_0\\ v_1\\ v_2\\ v_3\\ v_4 \end{bmatrix}

وهنا غادي تبدأ تفهم علاش فـ AI كنلقاو vectors كبار بزاف.

مثلاً:

```
double vector[768];
```

هذا vector عندو **768 components**.

---

# 6. علاش C مناسب لهادشي؟

حيت Linear Algebra كتخدم بزاف بـ:

```
numbers
arrays
loops
memory
```

وهادشي كامل C قوية فيه.

مثلاً vector:

```
double v[4] = {
    1.2,
    3.5,
    7.1,
    2.8
};
```

فالـ memory كيكونو values مخزنين sequentially:

```
Memory

┌──────┬──────┬──────┬──────┐
│ 1.2  │ 3.5  │ 7.1  │ 2.8  │
└──────┴──────┴──────┴──────┘
   ↑      ↑      ↑      ↑
 v[0]   v[1]   v[2]   v[3]
```

وهنا كتبدأ Linear Algebra تربطها حتى بـ **memory وC**.

---

# 7. وهادشي غادي يوصلنا للـ Matrix

من بعد vector غادي ندوزو لـ matrix.

رياضياً:

A=[123456]A = \begin{bmatrix} 1 & 2 & 3\\ 4 & 5 & 6 \end{bmatrix}

فـ C:

```
int A[2][3] = {
    {1, 2, 3},
    {4, 5, 6}
};
```

يعني:

```
Math                  C

1  2  3              A[0][0] A[0][1] A[0][2]
4  5  6              A[1][0] A[1][1] A[1][2]
```

وهنا غادي نربطو:

```
Matrix
   ↓
2D Array
   ↓
Nested loops
   ↓
Memory
```

---

# 🎯 الطريقة اللي غادي نقراو بها

ما غاديش ندير معاك:

```
Math course
     +
C course
```

منفصلين.

غادي نديرو:

```
       Linear Algebra
             ↓
        mathematical idea
             ↓
          example
             ↓
         C representation
             ↓
           memory
             ↓
           exercise
```

مثلاً:

```
Vector
  ↓
Array
  ↓
Vector addition
  ↓
for loop
  ↓
Memory
```

ومن بعد:

```
Matrix
  ↓
2D array
  ↓
nested loops
  ↓
memory layout
```

ومن بعد:

```
Dot product
  ↓
multiplication + addition
  ↓
C loop
```

ومن بعد:

```
Matrix multiplication
  ↓
3 nested loops
  ↓
C
```

وهنا غادي تبدا تشوف علاش **Math ديال CS ماشي مادة بوحدها؛ هي طريقة باش تفهم algorithms والـ code**.

**دابا ما نزيدوش لقدّام.** خدم هاد الربط الأول:

```
int A[3] = {2, 4, 6};
int B[3] = {1, 3, 5};
int C[3];
```

بغيتك تكتب **بـ C** الكود اللي يحسب:

C=A+BC = A + B

باستعمال `for`.

جاوب بالكود ديالك، وأنا نصححو قبل ما ندوزو لـ **magnitude ديال vector + C**.
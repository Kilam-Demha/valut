┌──────────────────────────────────┐
│                             COMPUTER BASICS          
└──────────────────────────────────┘

DATA
Raw facts / values
																	 معطيات خام

INFORMATION
Data + Meaning / Context
Data عندها معنى وسياق

INSTRUCTION
												أمر كيحدد شنو خاص Computer يدير

COMPUTER
System كيستقبل Data + Instructions
																	  → كيعالجهم 
																  → كيخرج Output
															  
																   
																					DATA   
         +      ===> input
   INSTRUCTIONS
         ↓
     COMPUTER
         ↓
    PROCESSING
         ↓
       OUTPUT




══════════════════════════════════════
              HARDWARE
══════════════════════════════════════

Physical components of a computer => المكونات المادية ديال Computer

Examples:
CPU
RAM
SSD
Keyboard
Mouse
Screen
Motherboard


══════════════════════════════════════
              SOFTWARE
══════════════════════════════════════

Definition:
Software هو مجموعة منظمة من البرامج (Programs)،
التعليمات (Instructions)، والبيانات (Data) التي تحدد
للـ Computer شنو خاصو يدير وكيفاش ينفذ المهام ديالو.

Software = Programs + Instructions + Data


العلاقة مع Hardware:

Hardware
= المكونات الفيزيائية ديال Computer

Software
= البرامج + التعليمات + البيانات

Hardware + Software
        ↓
  Computer System


BTS — Behind The Scenes:

Software
    ↓
Instructions
    ↓
CPU executes the instructions
    ↓
Hardware performs the operations
    ↓
Result / Output


ملاحظة مهمة:

CPU هو Hardware.
الـ CPU ما كيقررّش بوحدو شنو خاصو يدير.

Software كيوفر Instructions،
والـ CPU كينفذ هاد Instructions.


الفكرة الأساسية:

Hardware = الجسم الفيزيائي ديال Computer
Software = البرامج والمنطق والتعليمات اللي كتخليه يخدم
يعني Hardware هو **المكونات الفيزيائية**، وSoftware هو **المنطق والتعليمات** اللي كتخلي هاد المكونات تخدم بطريقة معينة.
ولكن الـ Software ماشي كامل نفس النوع.

كاين Software كيخدم مباشرة مع المستخدم، وكاين Software كينظم ويوفر الخدمات للنظام والبرامج الأخرى. **هاد التقسيم غادي ناخدوه من بعد بوحدو.




																																											════════════════════════════════════════════════════════   
                     BINARY SYSTEM
         ══════════════════════════════════════════

1. BIT
──────────────────────────────────────────
Bit = Binary Digit

هو أصغر وحدة أساسية فالمعلومات الرقمية.

Bit عندو جوج قيم فقط:

0 أو 1

مثال:
1011 = 4 Bits


2. BYTE
──────────────────────────────────────────
1 Byte = 8 Bits

مثال:

10110101 = 8 Bits = 1 Byte


3. BINARY SYSTEM
──────────────────────────────────────────
Binary = Number System أساسه 2.

كيستعمل غير:

0 و 1

Decimal = Base 10
Binary  = Base 2


4. POSITIONAL VALUE
──────────────────────────────────────────
كل Position فـ Binary عندها Power ديال 2.

من اليمين لليسار:

2⁰   2¹   2²   2³   2⁴   2⁵
 1    2    4    8   16   32

Rightmost Bit دائماً:

2⁰ = 1


5. BINARY → DECIMAL
──────────────────────────────────────────
كل Bit كنضربوه فـ Power ديال 2
حسب Position ديالو، ومن بعد كنجمعو.

Formula:

Bit × 2^Position

مثال:

1011₂

= 1×2³ + 0×2² + 1×2¹ + 1×2⁰

= 8 + 0 + 2 + 1

= 11₁₀


مثال:

10101₂

= 1×2⁴ + 0×2³ + 1×2²
  + 0×2¹ + 1×2⁰

= 16 + 0 + 4 + 0 + 1

= 21₁₀


6. ZERO BIT
──────────────────────────────────────────
إلى Bit = 0:

0 × 2^Position = 0

يعني ما كيضيف والو.

مثال:

10101

كنحتاجو غير:

16 + 4 + 1 = 21


7. POWERS OF 2
──────────────────────────────────────────

2⁰ = 1
2¹ = 2
2² = 4
2³ = 8
2⁴ = 16
2⁵ = 32
2⁶ = 64
2⁷ = 128
2⁸ = 256


8. NUMBER OF COMBINATIONS
──────────────────────────────────────────
إلى كان عندنا n Bits:

Number of combinations = 2ⁿ

مثال:

3 Bits
→ 2³ = 8 combinations

4 Bits
→ 2⁴ = 16 combinations

8 Bits
→ 2⁸ = 256 combinations


9. MAXIMUM UNSIGNED VALUE
──────────────────────────────────────────
إلى كان عندنا n Bits:

Maximum value = 2ⁿ − 1

مثال:

3 Bits:
2³ − 1 = 7

4 Bits:
2⁴ − 1 = 15

8 Bits:
2⁸ − 1 = 255


10. 1 BYTE
──────────────────────────────────────────
1 Byte = 8 Bits

8 Bits:

2⁸ = 256 combinations

Unsigned values:

0 → 255

Maximum:

255


11. 2 BYTES
──────────────────────────────────────────
2 Bytes = 16 Bits

Combinations:

2¹⁶ = 65,536

Maximum unsigned:

2¹⁶ − 1 = 65,535

Range:

0 → 65,535


12. DECIMAL → BINARY
──────────────────────────────────────────
كنمشي من أكبر Power of 2 للصغير.

كل مرة:

إذا كانت القيمة ≤ الباقي:
→ نحطو 1
→ نطرح القيمة من الباقي

إذا كانت القيمة > الباقي:
→ نحطو 0
→ ما نطرح والو


مثال:

45₁₀ → Binary

Powers:

32   16   8   4   2   1

45 - 32 = 13
16 > 13 → 0
13 - 8 = 5
5 - 4 = 1
2 > 1 → 0
1 - 1 = 0

إذن:

32   16   8   4   2   1
 1    0   1   1   0   1

45₁₀ = 101101₂


مثال:

37₁₀

32   16   8   4   2   1
 1    0   0   1   0   1

32 + 4 + 1 = 37

37₁₀ = 100101₂


13. MENTAL MODEL
──────────────────────────────────────────

BINARY → DECIMAL
─────────────────
"كنجمع القيم اللي عندها 1"

1011

8 + 2 + 1 = 11


DECIMAL → BINARY
─────────────────
"كنبني العدد باستعمال Powers of 2"

11

8 + 2 + 1

↓  ↓   ↓

1  0  1  1

= 1011


14. GOLDEN RULES
──────────────────────────────────────────

15) 1 Byte = 8 Bits

16) n Bits → 2ⁿ combinations

17) n Bits → 2ⁿ − 1 maximum unsigned value

18) Binary → Decimal:
   Bit × 2^Position
   ثم نجمعو

19) Decimal → Binary:
   كنستعملو Powers of 2
   من الكبير للصغير

20) 1 = ناخدو القيمة

21) 0 = ما ناخدوش القيمة

22) Binary = Base 2
    Decimal = Base 10


══════════════════════════════════════════




tamarin fi kolchi men lawal dial liom kamel

آه فهمتك دابا 😄 بغيتي **تمارين شاملة من اللول ديال درس اليوم كامل**، ماشي غير Position.

غادي نعطيك واحد **سلسلة مرتبة من الساهل للصعيب**، و**بلا حلول**. خدمهم بوحدك.

## 🟢 المرحلة 1 — Data / Information / Instruction

### 1

صنّف كل واحد: **Data ولا Information**

- `25`
- `Ahmed is 25 years old`
- `Safi`
- `The temperature is 25°C`

### 2

صنّف:

- `10`
- `20`
- `Add 10 and 20`
- `Multiply the result by 2`

كل واحد **Data ولا Instruction؟**

### 3

عطيني من عندك:

- مثال ديال Data
- مثال ديال Information
- مثال ديال Instruction

---

## 🟢 المرحلة 2 — Computer

### 4

كمّل:

```
Input → ______ → ______ → Output
```

### 5

عندنا:

```
10
20
Add
```

شنو:

- Input؟
- Data؟
- Instruction؟
- Processing؟
- Output؟

---

## 🟢 المرحلة 3 — Hardware / Software

### 6

صنّف:

- CPU
- RAM
- Linux
- Keyboard
- Firefox
- SSD
- VS Code
- Mouse

إلى **Hardware / Software**.

### 7

شرح بجملة وحدة:

**شنو الفرق بين Hardware و Software؟**

---

# 🔵 المرحلة 4 — Bit

### 8

شحال من Bits فكل واحد؟

```
0
1
101
101101
11111111
```

### 9

شنو هو الـBit؟

شرحها بطريقتك، بلا تعريف محفوظ.

---

# 🔵 المرحلة 5 — Byte

### 10

```
1 Byte = ? Bits
```

### 11

```
2 Bytes = ? Bits
4 Bytes = ? Bits
16 Bits = ? Bytes
32 Bits = ? Bytes
```

### 12

علاش 8 Bits كيقدرو يعطيو:

```
2⁸ = 256
```

combinations؟

---

# 🟡 المرحلة 6 — Binary

### 13

شنو هو Binary؟

وشحال من symbols كيستعمل؟

### 14

كتب Powers of 2 من:

```
2⁰
```

حتى:

```
2⁸
```

### 15

عندنا:

```
10101
```

كتب:

```
Position:
Power:
```

لكل Bit.

---

# 🟠 المرحلة 7 — Binary → Decimal

حوّل:

### 16

```
101₂ = ?
```

### 17

```
1101₂ = ?
```

### 18

```
10110₂ = ?
```

### 19

```
110011₂ = ?
```

### 20

```
101101₂ = ?
```

### 21 🔥

```
11111111₂ = ?
```

وحاول تشرح **علاش**.

---

# 🟠 المرحلة 8 — Decimal → Binary

حوّل:

### 22

```
5₁₀ = ?
```

### 23

```
18₁₀ = ?
```

### 24

```
27₁₀ = ?
```

### 25

```
42₁₀ = ?
```

### 26

```
75₁₀ = ?
```

### 27 🔥

```
100₁₀ = ?
```

---

# 🔴 المرحلة 9 — Bits / Combinations / Max Unsigned

### 28

عندنا **3 Bits**:

- Combinations؟
- Max unsigned؟
- Range؟

### 29

عندنا **5 Bits**:

- Combinations؟
- Max unsigned؟
- Range؟

### 30

عندنا **8 Bits**:

- Combinations؟
- Max unsigned؟
- Range؟

### 31

عندنا **10 Bits**:

- Combinations؟
- Max unsigned؟
- Range؟

---

# 🔥 المرحلة 10 — Reverse

### 32

عندنا:

```
32 combinations
```

- Bits؟
- Max unsigned؟

### 33

```
64 combinations
```

- Bits؟
- Max unsigned؟

### 34

```
256 combinations
```

- Bits؟
- Max unsigned؟

### 35

```
1024 combinations
```

- Bits؟
- Max unsigned؟
- Range؟

---

# 🧠 المرحلة 11 — Position

### 36

عندنا **4 Bits**:

```
Bit:       1  0  1  1
Position:  ?  ?  ?  ?
Power:     ?  ?  ?  ?
```

### 37

عندنا **8 Bits**:

- أول Position؟
- آخر Position؟
- شنو هي Power ديال آخر Position؟

### 38

عندنا **10 Bits**.

شرح:

> علاش عندنا 10 Bits ولكن الـPositions كيمشيو من `0` حتى `9`؟

---

# 🧠🔥 المرحلة الأخيرة — فهم حقيقي

### 39

واحد قال:

> "`2⁵ = 32` إذن Max Unsigned ديال 5 Bits هو 32."

واش صحيح؟ **فسّر علاش.**

### 40

واحد قال:

> "Position 0 يعني ما عندناش Bit، حيث العد كيبدأ من 0."

صحح ليه الفكرة.

### 41

عندك:

```
11111₂
```

بلا آلة حاسبة:

- شحال Decimal؟
- شحال Bits؟
- شحال combinations كاينة فهاد العدد ديال Bits؟
- شنو هو Max Unsigned؟

### 42 🔥🔥 Challenge

عندك:

```
101101₂
```

بغيت منك:

1. عدد الـBits
2. Positions
3. Powers of 2
4. Decimal value
5. عدد الـCombinations الممكنة باستعمال نفس عدد الـBits
6. Max Unsigned
7. Range

هاد **42 تمرين** كيغطي تقريباً كلشي داز اليوم من **Data حتى Binary وBits/Combinations/Positions**.

**ما تحاولش تحلهم كاملين فجلسة وحدة.** دير مثلاً **1 → 10**، وصيفط ليا الأجوبة، وأنا نصححهم معاك وحدة بوحدة.
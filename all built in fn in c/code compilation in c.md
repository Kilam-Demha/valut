t9dar dwi lia ala mara7el lcode fi c

آه، وهاد الموضوع مهم بزاف حيث دابا نقدر نجمعو ليك **Preprocessor + Compiler + Memory + Linker** فـصورة وحدة.

ملي كتكتب C code، راه ما كيمشيش مباشرة من `.c` للبرنامج. كيدوز من **عدة مراحل**.

# 🧠 الصورة الكبيرة

```
          code.c
             │
             ▼
    ┌─────────────────┐
    │ 1. PREPROCESSOR │
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 2. COMPILER     │
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │ 3. ASSEMBLER    │
    └────────┬────────┘
             │
             ▼
          code.o
             │
             ▼
    ┌─────────────────┐
    │ 4. LINKER       │
    └────────┬────────┘
             │
             ▼
       executable
             │
             ▼
    ┌─────────────────┐
    │ 5. LOADER / OS  │
    └────────┬────────┘
             │
             ▼
          RUN 🚀
```

دابا نشرحوهم **واحد بواحد**.

---

# 1. Preprocessor

أول مرحلة.

عندك:

```
#include <stdio.h>

#define MAX 100

int main(void)
{
    printf("%d\n", MAX);
    return 0;
}
```

الـPreprocessor كيشوف directives اللي كيبداو بـ:

```
#
```

بحال:

```
#include
#define
#if
#ifdef
#ifndef
#endif
```

مثلاً:

```
#define MAX 100
```

كيتم التعامل معاها قبل compilation.

و:

```
#include <stdio.h>
```

كيتم إدخال محتوى الـheader المناسب فمرحلة preprocessing.

تقريباً:

```
code.c
  │
  ▼
PREPROCESSOR
  │
  ├── #include
  ├── #define
  ├── #if...
  │
  ▼
code مُحضّر
```

**مهم:** الـPreprocessor ماشي هو اللي كيفهم C language كاملة.

هو كيحضّر النص/translation unit قبل compiler.

---

# 2. Compiler

دابا كيجي الدور ديال **Compiler**.

هنا كيبدأ الفهم الحقيقي ديال C.

مثلاً:

```
int main(void)
{
    int x = 10;
    return 0;
}
```

الـcompiler كيحلل:

```
int
main
(
void
)
{
...
}
```

وكيشوف واش الكود عندو معنى صحيح بالنسبة للغة C.

مثلاً إلا كتبتي:

```
int x = "hello";
```

ممكن compiler يعطيك diagnostic/error أو warning حسب الحالة والإعدادات.

كيحلل كذلك:

- syntax
- types
- expressions
- declarations
- functions
- operators
- conversions
- وغيرها

ومن بعد كيحوّل C إلى **assembly** أو representation وسيطة/مناسبة للـtarget قبل المرحلة التالية.

---

# 3. Assembler

دابا عندنا Assembly.

مثلاً بشكل مبسط:

```
mov eax, 10
```

الـAssembler كيحوّل Assembly إلى **machine code** ويخرج غالباً object file:

```
code.o
```

يعني:

```
C
 ↓
Compiler
 ↓
Assembly
 ↓
Assembler
 ↓
Machine code
 ↓
.o
```

الـ`.o` مازال **ماشي البرنامج النهائي**.

---

# 4. Linker

هاد المرحلة مهمة بزاف.

تخيل عندك:

```
main.c
functions.c
```

و:

```
// functions.c

int add(int a, int b)
{
    return a + b;
}
```

و:

```
// main.c

int add(int a, int b);

int main(void)
{
    int x = add(10, 20);
    return 0;
}
```

كل `.c` ممكن يتحول بشكل مستقل:

```
main.c
  ↓
main.o

functions.c
  ↓
functions.o
```

دابا شكون غادي يربطهم؟

**Linker.**

```
main.o ───────┐
              │
              ▼
           LINKER
              │
functions.o ──┘
              │
              ▼
          executable
```

الـLinker كيحل references بين object files والمكتبات المطلوبة، وكيخرج البرنامج النهائي.

---

# 5. مثال ديال `printf`

هنا غادي تفهم علاش Linker مهم.

إلا كتبت:

```
#include <stdio.h>

int main(void)
{
    printf("Hello\n");
    return 0;
}
```

`stdio.h` كيعطي compiler declaration ديال `printf`.

ولكن **definition/implementation ديال `printf` ماشي مكتوبة فـ`stdio.h`**.

كاينة فـlibrary.

يعني عندك تقريباً:

```
stdio.h
   │
   │ declaration
   ▼
Compiler يعرف printf
```

ومن بعد:

```
printf implementation
        │
        ▼
      LINKER
```

والـLinker كيربط البرنامج ديالك مع المكتبة المناسبة.

مع GCC، الأمر:

```
gcc main.c -o program
```

كيخبي عليك بزاف من هاد المراحل وكيقوم بهم.

---

# 6. شنو كيدير `gcc` بالضبط؟

ملي كتكتب:

```
gcc main.c -o program
```

`gcc` كيقوم بسلسلة ديال العمليات.

تقريباً:

```
main.c
  ↓
Preprocess
  ↓
Compile
  ↓
Assemble
  ↓
Link
  ↓
program
```

يعني `gcc` هنا **driver** كينظم هاد المراحل.

---

# 7. نقدر نشوفو المراحل بوحدهم

هادشي مفيد ليك باش تفهم عملياً.

## المرحلة 1: Preprocessor

```
gcc -E main.c -o main.i
```

غادي يخرج:

```
main.i
```

وهاد الملف فيه الكود بعد preprocessing.

---

## المرحلة 2: Compilation حتى Assembly

```
gcc -S main.c -o main.s
```

غادي يخرج:

```
main.s
```

فيه Assembly.

---

## المرحلة 3: Assembler

```
gcc -c main.c -o main.o
```

غادي يخرج:

```
main.o
```

Object file.

---

## المرحلة 4: Linker

```
gcc main.o -o program
```

غادي يخرج:

```
program
```

Executable.

---

# 8. ومن بعد كاين Runtime

دابا البرنامج النهائي موجود.

ملي كتدير:

```
./program
```

الـOS كيبدأ **تحميل البرنامج للـmemory**.

وهنا كنرجعو للموضوع اللي شرحنا:

```
Executable
    │
    ▼
OS / Loader
    │
    ▼
Memory
    │
    ├── Code
    ├── Data
    ├── BSS
    ├── Heap
    └── Stack
```

ومن بعد CPU كيبدأ ينفذ instructions.

---

# 9. مثال كامل من أول سطر حتى التنفيذ

عندنا:

```
#include <stdio.h>

#define NUMBER 10

int main(void)
{
    int x = NUMBER;

    printf("%d\n", x);

    return 0;
}
```

شنو كيوقع؟

### المرحلة 1

```
PREPROCESSOR

#define NUMBER 10
        ↓
NUMBER → 10

#include <stdio.h>
        ↓
header information/content incorporated
```

---

### المرحلة 2

```
COMPILER

C code
 ↓
تحليل syntax/types
 ↓
Assembly / target representation
```

---

### المرحلة 3

```
ASSEMBLER

Assembly
 ↓
Machine code
 ↓
main.o
```

---

### المرحلة 4

```
LINKER

main.o
  +
libraries / runtime
  ↓
program
```

---

### المرحلة 5

```
./program

OS
 ↓
loads program into memory
 ↓
CPU
 ↓
executes instructions
```

والنتيجة:

```
10
```

---

# 🔥 دابا جمع ليا هاد المفاهيم

من اللي شرحنا لك دابا:

```
                  C PROGRAM

                     .c
                      │
                      ▼
             ┌────────────────┐
             │  PREPROCESSOR  │
             │                │
             │ #include       │
             │ #define        │
             │ #if...         │
             └───────┬────────┘
                     │
                     ▼
             ┌────────────────┐
             │    COMPILER    │
             │                │
             │ C → Assembly   │
             └───────┬────────┘
                     │
                     ▼
             ┌────────────────┐
             │    ASSEMBLER   │
             │                │
             │ Assembly →     │
             │ Machine Code   │
             └───────┬────────┘
                     │
                     ▼
                    .o
                     │
                     ▼
             ┌────────────────┐
             │     LINKER     │
             │                │
             │ .o + libraries │
             └───────┬────────┘
                     │
                     ▼
                EXECUTABLE
                     │
                     ▼
                   LOADER
                     │
                     ▼
                  MEMORY
                     │
                     ▼
                    CPU
                     │
                     ▼
                  PROGRAM
```

## 🎯 الفرق اللي خاصك تحفظ

**Preprocessor**  
→ كيحضّر الكود.

**Compiler**  
→ كيترجم C وكيحلل اللغة والـtypes وكيخرج target code/Assembly.

**Assembler**  
→ كيحوّل Assembly لـmachine/object code.

**Linker**  
→ كيجمع ويربط object files والمكتبات.

**Loader/OS**  
→ كيحمّل البرنامج للـmemory باش يقدر CPU ينفذو.

وأهم تصحيح للفكرة اللي كانت عندك قبل:

> **الـPreprocessor ما كيعلمش الـcompiler باش ما يديرش errors؛ هو كيحضّر الـsource قبل ما الـcompiler يبدأ التحليل والـtranslation.**
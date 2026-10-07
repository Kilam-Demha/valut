

# 🧠 Blueprint ديال `make`

## 1. شنو هي `make`؟

`make` هي **Build Automation Tool**.

يعني كتعاونك تنظم وتـautomate عملية بناء المشروع.

```
Source Code
    ↓
  make
    ↓
 gcc / compiler
    ↓
 Object Files
    ↓
  linker
    ↓
 Executable
```

**مهم:**

```
gcc  → compiler
gdb  → debugger
make → build automation
```

`make` ماشي compiler.

---

# 2. علاش محتاج `make`؟

إلا كان عندك مشروع صغير:

```
main.c
```

تقدر:

```
gcc main.c -o program
```

ولكن المشروع يكبر:

```
project/
├── main.c
├── math.c
├── math.h
├── array.c
├── array.h
├── stack.c
├── stack.h
└── ...
```

وغادي تولي كل مرة كتكتب أوامر compilation بيدك.

هنا `make` كيساعدك.

بدل:

```
gcc ...
gcc ...
gcc ...
gcc ...
```

كتكتب:

```
make
```

وهو كيعرف شنو خاصو يدير.

---

# 3. قلب `make` هو `Makefile`

`make` كيحتاج ملف غالباً سميتو:

```
Makefile
```

مثال:

```
project/
├── main.c
├── math.c
├── math.h
└── Makefile
```

ومن بعد:

```
make
```

`make` كيقلب على:

```
Makefile
```

ويقراه.

---

# 4. شكل Rule فـ Makefile

القانون الأساسي:

```
target: dependencies
	command
```

مثال:

```
program: main.o math.o
	gcc main.o math.o -o program
```

عندنا 3 أجزاء:

```
program
   ↓
TARGET
```

```
main.o math.o
      ↓
DEPENDENCIES
```

```
gcc main.o math.o -o program
          ↓
       RECIPE
```

يعني:

> باش نصايب `program` خاصني `main.o` و `math.o`.

---

# 5. Target

الـ **target** هي الحاجة اللي بغينا نصايبو.

مثلاً:

```
program:
```

يعني الهدف هو:

```
program
```

ممكن يكون:

```
program
main.o
math.o
clean
```

---

# 6. Dependencies

Dependencies هما الملفات/الأهداف اللي target محتاجهم.

مثلاً:

```
program: main.o math.o
```

المعنى:

```
program
├── main.o
└── math.o
```

---

# 7. Recipe

Recipe هي الأوامر اللي `make` غادي ينفذ.

```
program: main.o math.o
	gcc main.o math.o -o program
```

هاد:

```
gcc main.o math.o -o program
```

هي الـ recipe.

⚠️ خاصها تبدأ بـ **TAB**.

---

# 8. كيفاش C كيتبنى؟

مثلاً:

```
main.c
math.c
math.h
```

أولاً:

```
gcc -c main.c
```

كيخرج:

```
main.o
```

وثانياً:

```
gcc -c math.c
```

كيخرج:

```
math.o
```

ومن بعد:

```
gcc main.o math.o -o program
```

كيخرج:

```
program
```

يعني:

```
main.c ──→ main.o ──┐
                    │
math.c ──→ math.o ──┼──→ program
                    │
```

و`make` كينظم هاد العملية.

---

# 9. مثال كامل

### `main.c`

```
#include <stdio.h>
#include "math.h"

int main(void)
{
    printf("%d\n", add(5, 3));
    return 0;
}
```

### `math.c`

```
#include "math.h"

int add(int a, int b)
{
    return a + b;
}
```

### `math.h`

```
int add(int a, int b);
```

### `Makefile`

```
program: main.o math.o
	gcc main.o math.o -o program

main.o: main.c math.h
	gcc -c main.c

math.o: math.c math.h
	gcc -c math.c

clean:
	rm -f *.o program
```

---

# 10. شنو كيوقع ملي كتكتب `make`؟

كتكتب:

```
make
```

`make` كيشوف:

```
program
 ↓
main.o + math.o
```

ولكن `main.o` ما كاينش.

إذن:

```
gcc -c main.c
```

كيصايبو.

نفس الشيء:

```
gcc -c math.c
```

كيصايب:

```
math.o
```

ومن بعد:

```
gcc main.o math.o -o program
```

والنتيجة:

```
program
```

---

# 11. علاش `make` ذكي؟

هاد النقطة مهمة بزاف.

إلا كتبت:

```
make
```

مرة ثانية وما تبدل والو:

```
make
 ↓
شنو تبدل؟
 ↓
والو
 ↓
ما ندير والو
```

وغالباً يعطيك:

```
make: 'program' is up to date.
```

---

# 12. إلا بدلتي `math.c`

مثلاً:

```
math.c
```

تبدل.

`make` كيشوف:

```
math.c → math.o → program
```

إذن:

```
math.c تبدل
    ↓
math.o قديم
    ↓
عاود compile
    ↓
program خاصو يتعاود build
```

ولكن:

```
main.c
```

ما تبدلش.

إذن **ما محتاجش يعاود `main.o`**.

هاد الشي هو واحد من أهم أسباب استعمال `make`.

---

# 13. `make clean`

فـ Makefile عندنا:

```
clean:
	rm -f *.o program
```

هادشي ماشي compilation.

`clean` هو target.

ملي تكتب:

```
make clean
```

كيحيد:

```
main.o
math.o
program
```

ويبقى:

```
main.c
math.c
math.h
Makefile
```

---

# 14. علاش `clean` ما عندهاش dependencies؟

حيت:

```
clean:
	rm -f *.o program
```

ماشي target حقيقي كيتولد من ملفات.

هي غير **command نطلبوها من make**.

يعني:

```
make
```

→ build

```
make clean
```

→ cleanup

---

# 15. Targets بحال Commands

تقدر تعتبر:

```
make
```

بحال:

```
make program
```

و:

```
make clean
```

بحال command أخرى.

مثلاً:

```
make program
```

كيبني `program`.

---

# 16. الصورة الكبيرة

حفظ هاد الرسم:

```
                    Makefile
                       │
                       ↓
                     make
                       │
              ┌────────┴────────┐
              ↓                 ↓
          Dependencies       Recipes
              │                 │
              ↓                 ↓
         main.c/math.c       gcc commands
              │                 │
              └────────┬────────┘
                       ↓
                 Object Files
                       │
                       ↓
                    Linking
                       │
                       ↓
                  Executable
```

---

# 17. العلاقة بين الأدوات اللي عندك

دابا عندك:

```
┌──────────────────────────────┐
│             C                │
└──────────────┬───────────────┘
               ↓
              gcc
               │
               ↓
          Build/Compile
               │
               ↓
           program
               │
               ↑
             make
        automation/build
```

وإذا وقع bug:

```
program
   ↓
gdb
   ↓
Debug
```

يعني:

```
gcc  → Build/Compile
make → Organize/Automate Build
gdb  → Debug
```

---

# 18. شنو خاصك تحفظ دابا؟

ما تحفظش syntax كامل.

حفظ غير هاد الفكرة:

```
Makefile
   ↓
Target
   ↓
Dependencies
   ↓
Recipe
```

والـ syntax:

```
target: dependencies
	TAB command
```

مثال:

```
program: main.o math.o
	gcc main.o math.o -o program
```

والاستعمال:

```
make
```

أو:

```
make clean
```

---

# 🎯 المستوى ديالك دابا

بالنسبة للمسار ديالك **C → Memory → Data Structures → Algorithms**:

```
C basics
   ↓
gcc
   ↓
gdb
   ↓
make  ← أنت هنا
   ↓
multi-file C projects
   ↓
pointers
   ↓
dynamic memory
   ↓
data structures
   ↓
algorithms
```

**ما تحتاجش تدخل CMake دابا.** `make + Makefile` كافيين باش تفهم أولاً شنو هو build system وكيفاش المشاريع ديال C كيتبناو.
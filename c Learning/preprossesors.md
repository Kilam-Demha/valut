
أكيد. نخليو **macros** و **header files** من الصفر، وبالطريقة اللي غادي تحتاجها فـC وخصوصاً من بعد فـEmbedded.

# 1. أولاً: شنو هو الـMacro؟

الـ**macro** فـC هو تعليمات كيتعامل معاها **preprocessor** قبل ما الـcompiler يبدا يcompile الكود.

يعني عندنا تقريباً هاد المراحل:

```
.c file
   ↓
Preprocessor
   ↓
Compiler
   ↓
Assembler
   ↓
Linker
   ↓
Executable
```

الـmacro كيتخدم فمرحلة:

```
        PREPROCESSOR
             ↓
         #define
```

---

# 2. أبسط Macro

مثلاً:

```
#define PI 3.14159
```

ومن بعد:

```
#include <stdio.h>

#define PI 3.14159

int main(void)
{
    printf("%f\n", PI);

    return 0;
}
```

قبل ما الـcompiler يشوف الكود، الـpreprocessor كيبدل:

```
PI
```

بـ:

```
3.14159
```

يعني تقريباً:

```
printf("%f\n", 3.14159);
```

إذن:

```
#define PI 3.14159
        ↑
      Macro
```

---

# 3. واش Macro variable؟

**لا.**

وهدي مهمة بزاف.

إلا كتبتي:

```
#define MAX 100
```

`MAX` ماشي variable.

ما عندهاش:

```
RAM
address
type
```

بالطريقة ديال variable.

هي غير **استبدال نصي preprocessing**.

مثلاً:

```
#define MAX 100

int x = MAX;
```

الـpreprocessor كيخليها تقريباً:

```
int x = 100;
```

ومن بعد الـcompiler كيكمل خدمتو.

---

# 4. علاش كنستعملو Macros؟

كاينين بزاف ديال الاستعمالات.

مثلاً constants:

```
#define MAX_USERS 100
#define BUFFER_SIZE 256
#define PI 3.14159
```

بدل ما تكتب:

```
char buffer[256];
```

تقدر:

```
char buffer[BUFFER_SIZE];
```

الميزة هي إلا بغيتي تبدل `256` إلى `512` كتبدل غير:

```
#define BUFFER_SIZE 512
```

---

# 5. Macro يقدر حتى يكون بحال function

مثلاً:

```
#define SQUARE(x) ((x) * (x))
```

ومن بعد:

```
int x = SQUARE(5);
```

الـpreprocessor تقريباً كيحولها لـ:

```
int x = ((5) * (5));
```

والنتيجة:

```
25
```

ولكن **رد بالك**: Macro function ماشي function حقيقية.

وهذا الفرق مهم:

```
int square(int x)
{
    return x * x;
}
```

هاد **function**.

أما:

```
#define SQUARE(x) ((x) * (x))
```

هاد **macro**.

---

# 6. علاش كنكتبوا الأقواس؟

شوف هاد macro الخايب:

```
#define SQUARE(x) x * x
```

إلا درنا:

```
SQUARE(2 + 3)
```

الـpreprocessor يقدر يعطي:

```
2 + 3 * 2 + 3
```

وبسبب precedence غادي تكون:

```
11
```

ماشي:

```
25
```

لهذا كنكتبوا:

```
#define SQUARE(x) ((x) * (x))
```

باش تكون أكثر أماناً.

---

# 7. دابا Header File شنو هو؟

الـ**header file** هو غالباً ملف عندو extension:

```
.h
```

مثلاً:

```
stdio.h
stdlib.h
string.h
math.h
my_functions.h
```

الفكرة ديالو هي أنه كيحتوي على **declarations / definitions / macros / types** اللي بغيتي تستعملهم فـملفات `.c`.

---

# 8. علاش محتاجين Header Files؟

تخيل عندك جوج files:

```
main.c
functions.c
```

وفـ`functions.c` عندك:

```
int add(int a, int b)
{
    return a + b;
}
```

وفـ`main.c` بغيتي تستعمل:

```
add(10, 20);
```

الـcompiler خاصو يعرف:

> شنو هي `add`؟  
> شنو parameters ديالها؟  
> شنو return type ديالها؟

لهذا كنحطو declaration فـheader:

```
int add(int a, int b);
```

---

# 9. مثال كامل

عندنا:

```
project/
│
├── main.c
├── functions.c
└── functions.h
```

### `functions.h`

```
#ifndef FUNCTIONS_H
#define FUNCTIONS_H

int add(int a, int b);

#endif
```

### `functions.c`

```
#include "functions.h"

int add(int a, int b)
{
    return a + b;
}
```

### `main.c`

```
#include <stdio.h>
#include "functions.h"

int main(void)
{
    int result = add(10, 20);

    printf("%d\n", result);

    return 0;
}
```

ومن بعد:

```
gcc -Wall -Wextra -Werror main.c functions.c -o program
```

---

# 10. شنو كيدير `#include`؟

مثلاً:

```
#include "functions.h"
```

ماشي معناها أن `functions.h` كيتخدم بوحدو.

الـpreprocessor كيدير تقريباً:

```
خذ محتوى functions.h
وحطو هنا
```

يعني:

```
#include "functions.h"

int main(void)
{
    ...
}
```

تقريباً كيولي:

```
int add(int a, int b);

int main(void)
{
    ...
}
```

---

# 11. الفرق بين `< >` و `" "`

عندك:

```
#include <stdio.h>
```

و:

```
#include "functions.h"
```

بشكل مبسط:

### `< >`

كتستعمل غالباً مع system / installed headers:

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>
```

### `" "`

كتستعمل غالباً مع headers ديالك:

```
#include "functions.h"
#include "config.h"
#include "utils.h"
```

---

# 12. دابا العلاقة بين Macro و Header

وهنا غادي تبدا الصورة تكمل.

تقدر تحط macros داخل `.h`.

مثلاً:

### `config.h`

```
#ifndef CONFIG_H
#define CONFIG_H

#define BUFFER_SIZE 128
#define MAX_USERS 50

#endif
```

ومن بعد:

```
#include "config.h"

int main(void)
{
    char buffer[BUFFER_SIZE];

    return 0;
}
```

يعني الـheader يقدر يجمع ليك الأشياء اللي غادي تحتاجها فـعدة `.c` files.

---

# 13. شنو هادو `#ifndef` و `#define` و `#endif`؟

غادي تلقاهم بزاف فـheader files:

```
#ifndef FUNCTIONS_H
#define FUNCTIONS_H

int add(int a, int b);

#endif
```

هادشي كيتسمى:

**include guard**

الفكرة ديالو هي يمنع أن نفس الـheader يتحط أكثر من مرة بطريقة تسبب مشاكل.

كتخيل:

```
functions.h
     ↓
   include
     ↓
   include
     ↓
   include
```

الـinclude guard كيقول:

```
واش FUNCTIONS_H متعرف من قبل؟

   NO → دخل المحتوى
   YES → ما تدخل والو
```

---

# 14. أهم حاجة: `.h` ماشي بالضرورة فيه implementation

غالباً كنفرقو:

### Header `.h`

فيه:

```
int add(int a, int b);
```

يعني **declaration**.

### Source `.c`

فيه:

```
int add(int a, int b)
{
    return a + b;
}
```

يعني **implementation**.

الصورة:

```
functions.h
     │
     │ declaration
     ▼
int add(int, int);


functions.c
     │
     │ implementation
     ▼
int add(int a, int b)
{
    return a + b;
}
```

---

# 15. Header files ديال C Standard Library

من أشهرهم:

```
stdio.h
stdlib.h
string.h
math.h
ctype.h
stdbool.h
stdint.h
stddef.h
```

مثلاً:

```
#include <stdio.h>
```

باش تستعمل:

```
printf()
scanf()
```

---

### `stdlib.h`

فيه حاجات بحال:

```
malloc()
free()
atoi()
exit()
```

---

### `string.h`

فيه:

```
strlen()
strcmp()
strcpy()
strcat()
```

---

### `math.h`

فيه:

```
sqrt()
pow()
sin()
cos()
fmod()
```

وفحال ما شفنا قبل، إلى استعملتي بعض math functions مع GCC ممكن تحتاج:

```
-lm
```

مثلاً:

```
gcc main.c -lm
```

---

# 16. وهادشي مهم ليك فـEmbedded

من بعد ملي تدخل Embedded غادي تلقى headers بحال:

```
#include <stdint.h>
```

ومن بعد:

```
uint8_t
uint16_t
uint32_t
uint32_t
```

مثلاً:

```
uint8_t value;
```

يعني integer unsigned عندو **8 bits**.

وغادي تلقى حتى macros بحال:

```
#define LED_PIN 5
```

ولا:

```
#define CPU_FREQ 16000000
```

والـheaders ديال microcontroller ممكن يكونو عامرين بـ:

```
#define
typedef
struct
enum
extern
```

وهنا غادي تبدأ تشوف علاش الـEmbedded كيعتمد بزاف على `.h`.

---

# الخلاصة اللي خاصك تديرها فالكناش

```
MACRO
│
├── كيتعالج بواسطة Preprocessor
│
├── #define
│
├── غالباً constant
│     #define MAX 100
│
└── ممكن function-like macro
      #define SQUARE(x) ((x) * (x))


HEADER FILE
│
├── extension: .h
│
├── declarations
│
├── macros
│
├── typedefs
│
├── structs / enums
│
└── declarations ديال functions


#include
│
└── كيدخل محتوى header فـsource file
```

والـflow كامل:

```
             main.c
               │
               │ #include "functions.h"
               ▼
        ┌────────────────┐
        │  PREPROCESSOR  │
        │                │
        │ #include       │
        │ #define        │
        └───────┬────────┘
                │
                ▼
          code جاهز
                │
                ▼
            COMPILER
                │
                ▼
           OBJECT FILE
                │
                ▼
             LINKER
                │
                ▼
          EXECUTABLE
```

**النقطة الذهبية:**  
`#define` و`#include` بجوجهم كيبداو بـ `#` حيت هما **preprocessor directives**، وماشي C functions.



--------------
ya3ni homa kitsamaw preprosessor o ki t9raw 9bal l compilation bach ay cod fi time dial compilation ykon deja arfo compailer omaiderch errors

إييه، **قريب بزاف من الفكرة الصحيحة**، غير خاصنا نصححو واحد التفصيل مهم.

الـ**Preprocessor** كيقرا الكود **قبل الـcompiler**، ولكن ماشي الهدف ديالو هو "يعلم الـcompiler باش ما يديرش errors".

هو كيقوم أولاً بتحضير الكود.

مثلاً عندك:

```
#include <stdio.h>

#define MAX 100

int main(void)
{
    printf("%d\n", MAX);
    return 0;
}
```

الترتيب تقريباً:

```
        الكود ديالك
             │
             ▼
      ┌─────────────┐
      │ PREPROCESSOR│
      └──────┬──────┘
             │
       #include
       #define
       #if...
             │
             ▼
      كود مُحضَّر
             │
             ▼
      ┌─────────────┐
      │   COMPILER  │
      └──────┬──────┘
             │
             ▼
          Object
             │
             ▼
          LINKER
             │
             ▼
        Executable
```

مثلاً:

```
#define MAX 100
```

الـPreprocessor يبدل `MAX` بـ `100`.

و:

```
#include "functions.h"
```

كيجيب محتوى الـheader ويدخلو فالكود.

**من بعد** كيجي الـcompiler وكيحلل C الحقيقي.

---

### ولكن انتبه لهادي 👇

حتى إلا الـPreprocessor وجد الكود، **الـcompiler يقدر يعطي errors عادي جداً**.

مثلاً:

```
#define MAX 100

int main(void)
{
    printf("%d\n", MAX)
}
```

الـPreprocessor يقدر يحضر الكود، ولكن الـcompiler غادي يقول:

```
error: expected ';' before '}'
```

يعني:

```
Preprocessor
    ↓
يحضّر الكود

Compiler
    ↓
يفهم C syntax/types
    ↓
يكتشف errors
```

إذن العبارة الأدق هي:

> **الـPreprocessor كيجهز الكود قبل الـcompilation، والـcompiler من بعد كيتعامل مع الكود الناتج وكيقدر يكتشف فيه errors.**

وواحد الحاجة أخرى مهمة:  
**Header files ماشي باش يمنعو errors**؛ هما كيعطيو الـcompiler المعلومات اللي محتاجها، بحال declarations ديال functions وtypes وmacros، باش يقدر يفهم الكود ويتحقق منو مزيان.
إييه، بالضبط. إلى قلتي ليا **"بغيت أهم المكتبات فـ C، وأهم functions اللي ضروري نعرف"**، غادي نعطيك **الخريطة ديال C** ماشي غير functions عشوائية.

وبما أنك باغي C مزيان ومن بعد Systems/Embedded، هادي هي الأولوية:

## 1. `<stdio.h>` ⭐⭐⭐⭐⭐

**Standard Input / Output**

هاد المكتبة من أهم المكتبات فـ C.

أهم functions:

```
printf()
scanf()
getchar()
putchar()
fgets()
puts()
```

ولـ files:

```
fopen()
fclose()
fread()
fwrite()
fprintf()
fscanf()
fgets()
fputs()
fgetc()
fputc()
feof()
ferror()
```

خاصك تفهم مزيان خصوصاً:

```
printf
scanf
fgets
fopen
fclose
fread
fwrite
```

---

# 2. `<stdlib.h>` ⭐⭐⭐⭐⭐

مهمة بزاف.

أهم functions:

```
malloc()
calloc()
realloc()
free()
```

هادشي ديال **Dynamic Memory**.

وزيد:

```
exit()
atoi()
strtol()
strtod()
qsort()
bsearch()
```

مثلاً:

```
int *p = malloc(10 * sizeof(int));

if (p == NULL)
{
    // error
}

free(p);
```

بالنسبة ليك هادي مكتبة **ضرورية جداً**.

---

# 3. `<string.h>` ⭐⭐⭐⭐⭐

ديال التعامل مع strings وmemory.

أهم functions:

```
strlen()
strcpy()
strncpy()
strcat()
strncat()
strcmp()
strncmp()
strchr()
strstr()
strtok()
```

وزيد functions ديال memory:

```
memcpy()
memmove()
memset()
memcmp()
```

خصوصاً:

```
strlen
strcmp
strcpy
memcpy
memmove
memset
```

---

# 4. `<ctype.h>` ⭐⭐⭐⭐

كتعاونك تفحص characters.

```
isalpha()
isdigit()
isalnum()
isspace()
islower()
isupper()
tolower()
toupper()
```

مثلاً:

```
if (isdigit(c))
{
    ...
}
```

مهمة فـ input validation وparsing.

---

# 5. `<stdbool.h>` ⭐⭐⭐⭐

باش تستعمل Boolean:

```
bool
true
false
```

مثلاً:

```
bool is_valid = true;
```

---

# 6. `<stdint.h>` ⭐⭐⭐⭐⭐

**مهمة بزاف ليك خصوصاً Embedded.**

كتعطيك integer types بأحجام محددة:

```
uint8_t
uint16_t
uint32_t
uint64_t

int8_t
int16_t
int32_t
int64_t
```

مثلاً:

```
uint8_t byte = 255;
```

هادشي غادي يكون مهم جداً ملي تربط C بالـ **binary / memory / hardware**.

---

# 7. `<stddef.h>` ⭐⭐⭐⭐

مهمة خصوصاً مع pointers وmemory.

أهم حاجة:

```
size_t
NULL
ptrdiff_t
```

مثلاً:

```
size_t length = strlen("Ahmed");
```

`size_t` غادي تشوفها **بزاف** فـ C.

---

# 8. `<math.h>` ⭐⭐⭐

للرياضيات:

```
sqrt()
pow()
fabs()
floor()
ceil()
round()
sin()
cos()
tan()
log()
exp()
```

وإلا استعملتي math library مع GCC غالباً:

```
gcc file.c -lm
```

---

# 9. `<time.h>` ⭐⭐⭐

للوقت والتاريخ:

```
time()
clock()
localtime()
gmtime()
strftime()
```

---

# 10. `<assert.h>` ⭐⭐⭐

للـ debugging:

```
assert()
```

مثلاً:

```
assert(ptr != NULL);
```

---

# 11. `<errno.h>` ⭐⭐⭐⭐⭐

هاد المكتبة مرتبطة مباشرة بالـ **Error Handling** اللي كنا كنهدرو عليه:

```
errno
```

وغالباً معها:

```
perror()
strerror()
```

ولكن:

```
errno.h → errno
stdio.h → perror()
string.h → strerror()
```

---

# 12. `<limits.h>` ⭐⭐⭐⭐

باش تعرف حدود أنواع integer:

```
INT_MIN
INT_MAX
UINT_MAX
CHAR_BIT
LONG_MAX
```

مهمة ملي تفهم **data types + memory + binary**.

---

# 13. `<float.h>` ⭐⭐⭐

حدود floating-point:

```
FLT_MAX
FLT_MIN
DBL_MAX
DBL_MIN
```

---

# 14. `<unistd.h>` ⭐⭐⭐⭐⭐

⚠️ هادي **POSIX** وماشي ISO C standard، ولكن بما أنك باغي **Linux + Systems** فهي مهمة جداً.

غادي تلقى فيها:

```
read()
write()
close()
sleep()
usleep()
getpid()
fork()
exec()
```

وهنا غادي تبدأ تدخل من C لـ **Linux/System Programming**.

---

# 15. `<fcntl.h>` ⭐⭐⭐⭐

مهمة مع Linux files:

```
open()
```

وflags بحال:

```
O_RDONLY
O_WRONLY
O_RDWR
O_CREAT
O_APPEND
```

هنا غادي تبدا تشوف الفرق بين:

```
fopen()
```

و:

```
open()
```

---

# 16. `<sys/types.h>` / `<sys/stat.h>` ⭐⭐⭐⭐

مهمين مع Linux/system calls.

مثلاً:

```
stat()
```

وpermissions/file metadata.

---

# الخريطة اللي أنصحك بها

ما تحاولش تحفظهم كاملين دابا. تعلمهم بهاد الترتيب:

```
C FUNDAMENTALS
      │
      ├── stdio.h
      │
      ├── stdlib.h
      │
      ├── string.h
      │
      ├── ctype.h
      │
      ├── stdbool.h
      │
      ├── stdint.h
      │
      ├── stddef.h
      │
      ├── errno.h
      │
      ├── assert.h
      │
      ├── limits.h
      │
      └── math.h
             │
             ▼
       LINUX / SYSTEMS
             │
             ├── unistd.h
             ├── fcntl.h
             ├── sys/types.h
             └── sys/stat.h
```

### والأهم بالنسبة ليك دابا

إلى بغينا **C قوية**، ركز أولاً على هادو:

**`stdio.h` → `stdlib.h` → `string.h` → `ctype.h` → `stdint.h` → `stddef.h` → `errno.h`**

ومن بعد ندوزو لـ Linux:

**`unistd.h` → `fcntl.h` → `sys/stat.h`**

وماشي الهدف تحفظ أسماء functions؛ الهدف هو تعرف **علاش كاينة، شنو كتدخل ليها، شنو كترجع، وشنو errors ممكن توقع**.

ومن هنا نقدر ندير لك **كل مكتبة بوحدها: concept → أهم functions → شرح كل function → examples → من بعد exercises بلا حلول**.

قدم لي كل مكتبة بوحدها مع concept، أهم functions، شرح كل function، examples، وexercises بلا حلول

أكيد. وغادي نديروها بطريقة **C Pro**: كل مكتبة بوحدها، نفهمو الـconcept، علاش كنحتاجوها، أهم functions، parameters/return، examples، ومن بعد exercises **بلا حلول**.

ما غاديش نحاول نحفظوك 100 function؛ غادي نركز على **اللي فعلاً خاصك تعرف** فـ C + Linux + Embedded.

# الخطة الكاملة

```
1. stdio.h       → Input / Output / Files
2. stdlib.h      → Memory / Conversion / Program control
3. string.h      → Strings / Memory
4. ctype.h       → Characters
5. stdbool.h     → Boolean
6. stdint.h      → Fixed-width integers
7. stddef.h      → size_t / NULL / pointer-related types
8. errno.h       → Error codes
9. assert.h      → Debugging
10. limits.h      → Integer limits
11. float.h       → Floating-point limits
12. math.h        → Mathematics

        ↓ Linux / System Programming

13. unistd.h       → POSIX system functions
14. fcntl.h        → File descriptors / open()
15. sys/types.h    → System types
16. sys/stat.h     → File information / permissions
```

---

# 01 — `<stdio.h>`

## Concept

`stdio` = **Standard Input / Output**

يعني التعامل مع:

```
Keyboard → program → screen
                ↓
              files
```

هي من أهم المكتبات فـ C.

```
#include <stdio.h>
```

---

## أهم functions

### `printf()`

كتطبع output.

```
printf("Hello\n");
```

مع variable:

```
int age = 28;

printf("Age = %d\n", age);
```

أهم format specifiers:

```
%d → int
%u → unsigned int
%ld → long
%f → floating-point
%c → char
%s → string
%p → pointer
```

---

### `scanf()`

كتقرا input formatted.

```
int age;

scanf("%d", &age);
```

الفكرة:

```
keyboard
   ↓
scanf()
   ↓
variable
```

⚠️ `scanf()` خاصك تفهم مزيان المشاكل ديالها، خصوصاً مع strings وbuffer.

---

### `getchar()`

كتقرا **character واحد**.

```
char c;

c = getchar();
```

مثلاً user يكتب:

```
A
```

`getchar()` تقرا `A`.

---

### `putchar()`

كتطبع character واحد.

```
char c = 'A';

putchar(c);
```

---

### `fgets()`

مهمة بزاف لقراءة strings/lines.

```
char name[50];

fgets(name, sizeof(name), stdin);
```

غالباً أفضل من `scanf("%s", ...)` ملي كتحتاج تقرا line.

---

### `puts()`

كتطبع string.

```
puts("Hello Ahmed");
```

وكتزيد newline.

---

# Files

هاد الجزء مهم بزاف.

## `fopen()`

كتفتح file.

```
FILE *file = fopen("data.txt", "r");
```

Modes المهمة:

```
"r"  → read
"w"  → write
"a"  → append
"r+" → read + write
"w+" → write + read
"a+" → append + read
```

مثلاً:

```
FILE *file = fopen("data.txt", "r");

if (file == NULL)
{
    perror("fopen");
}
```

لاحظ هنا دخلنا لـ **Error Handling**.

---

## `fclose()`

كتسد file.

```
fclose(file);
```

قاعدة:

```
fopen()
   ↓
استعمل file
   ↓
fclose()
```

---

## `fprintf()`

بحال `printf()` ولكن للـ file.

```
fprintf(file, "Age: %d\n", age);
```

---

## `fscanf()`

بحال `scanf()` ولكن من file.

```
fscanf(file, "%d", &age);
```

---

## `fgetc()`

كتقرا character واحد من file.

```
int c;

c = fgetc(file);
```

لاحظ `int` ماشي `char`، وهذا مهم بسبب `EOF`.

---

## `fputc()`

كتكتب character واحد.

```
fputc('A', file);
```

---

## `fgets()` مع file

```
char buffer[100];

fgets(buffer, sizeof(buffer), file);
```

---

## `fputs()`

كتكتب string للـ file.

```
fputs("Hello\n", file);
```

---

## `fread()`

كتقرا **blocks of bytes**.

```
fread(buffer, sizeof(char), 100, file);
```

غادي تولي مهمة مع binary files.

---

## `fwrite()`

كتكتب blocks of bytes.

```
fwrite(buffer, sizeof(char), 100, file);
```

هاد جوج مهمين بزاف ملي غادي تدخل للـ low-level C.

---

## `feof()`

كتشوف واش وصلتي لنهاية file.

```
if (feof(file))
{
    printf("End of file\n");
}
```

---

## `ferror()`

كتشوف واش وقع file error.

```
if (ferror(file))
{
    printf("File error\n");
}
```

---

# Exercises — stdio.h

بلا حلول:

### Exercise 1

برنامج يطلب من user:

```
name
age
```

ومن بعد يطبعهم.

### Exercise 2

برنامج يقرا character واحد ويحدد واش هو vowel ولا لا.

### Exercise 3

برنامج يقرا line كاملة باستعمال `fgets()` ويطبعها.

### Exercise 4

صايب برنامج يفتح `data.txt` ويكتب فيه:

```
Hello
C Programming
```

### Exercise 5

افتح file للقراءة وطبع المحتوى ديالو.

### Exercise 6

قرا file character by character باستعمال `fgetc()`.

### Exercise 7

قرا file line by line باستعمال `fgets()`.

### Exercise 8

نسخ محتوى file إلى file آخر.

### Exercise 9

حسب عدد characters فـ file.

### Exercise 10

حسب عدد lines فـ file.

---

# 02 — `<stdlib.h>`

## Concept

`stdlib.h` = **General Utilities**

أهم المجالات:

```
Memory
Conversion
Random numbers
Program termination
Searching/sorting
```

```
#include <stdlib.h>
```

---

## `malloc()`

كتطلب memory dynamically.

```
int *p = malloc(5 * sizeof(int));
```

الفكرة:

```
Stack
Heap
 ↑
malloc() → memory من Heap
```

خاصك دائماً تتحقق:

```
if (p == NULL)
{
    // allocation failed
}
```

ومن بعد:

```
free(p);
```

---

## `calloc()`

بحال `malloc()` ولكن كتـinitialize memory بـ zero.

```
int *p = calloc(5, sizeof(int));
```

---

## `realloc()`

كتبدل size ديال allocated memory.

```
p = realloc(p, 10 * sizeof(int));
```

⚠️ هادي خاصها تعامل حذر، حيث ممكن تفشل.

---

## `free()`

كتحرر memory.

```
free(p);
```

من أهم functions فـ C.

```
malloc()
calloc()
realloc()
      ↓
    free()
```

---

## `exit()`

كتوقف البرنامج.

```
exit(1);
```

عادة:

```
exit(0) → success
non-zero → failure
```

---

## `atoi()`

تحويل string إلى integer.

```
int n = atoi("123");
```

ولكن فـ production code غالباً `strtol()` أفضل حيث كتسمح بـ error checking أحسن.

---

## `strtol()`

تحويل string إلى `long` مع إمكانية اكتشاف errors.

```
long n = strtol("123", NULL, 10);
```

غادي نركزو عليها ملي نوصلو لـ parsing/error handling.

---

## `qsort()`

Sorting.

```
qsort(array, size, sizeof(int), compare);
```

كتحتاج comparison function.

---

## `bsearch()`

Binary search فـ array مرتبة.

```
bsearch(key, array, size, sizeof(int), compare);
```

---

# Exercises — stdlib.h

1. Allocate array ديال 5 integers بـ `malloc`.
2. عمر array بالقيم.
3. حرر memory بـ `free`.
4. دير نفس الشيء بـ `calloc`.
5. كبر array من 5 إلى 10 elements بـ `realloc`.
6. تعامل مع failure ديال `malloc`.
7. حول `"12345"` إلى integer.
8. جرب input غير صالح مع conversion.
9. رتب array باستعمال `qsort`.
10. قلب على element باستعمال `bsearch`.

---

# 03 — `<string.h>`

## Concept

التعامل مع:

```
Strings
Memory blocks
```

---

## `strlen()`

كتحسب طول string.

```
size_t len = strlen("Ahmed");
```

النتيجة:

```
5
```

ما كتعدش `'\0'`.

---

## `strcpy()`

كتنسخ string.

```
strcpy(destination, source);
```

⚠️ destination خاصها تكون فيها مساحة كافية.

---

## `strncpy()`

نسخة محدودة بعدد characters.

```
strncpy(destination, source, n);
```

⚠️ عندها nuances مهمة مع null termination.

---

## `strcmp()`

كتقارن strings.

```
strcmp(a, b);
```

النتيجة:

```
0   → equal
<0  → a قبل b
>0  → a بعد b
```

---

## `strncmp()`

بحال `strcmp()` ولكن حتى عدد معين.

---

## `strcat()`

كتلصق string مع string.

```
strcat(a, b);
```

---

## `strchr()`

كتقلب على character.

```
strchr(text, 'a');
```

---

## `strstr()`

كتقلب على substring.

```
strstr(text, "cat");
```

---

## `strtok()`

كتقسم string إلى tokens.

مثلاً:

```
"Ahmed,28,Safi"
```

تقدر تقسمها بـ `,`.

مهمة فـ parsing، ولكن خاص تفهم أنها كتعدل string الأصلية.

---

## Memory functions

### `memcpy()`

نسخ bytes.

```
memcpy(destination, source, size);
```

### `memmove()`

نسخ bytes حتى إلا كان overlap.

```
memmove(destination, source, size);
```

### `memset()`

كتعمر memory بقيمة.

```
memset(buffer, 0, sizeof(buffer));
```

### `memcmp()`

كتقارن memory blocks.

---

# Exercises — string.h

1. حسب length ديال string بلا `strlen()`.
2. استعمل `strlen()`.
3. قارن جوج strings.
4. نسخ string.
5. جمع جوج strings.
6. قلب على character.
7. قلب على substring.
8. قسم CSV string باستعمال `strtok()`.
9. استعمل `memset()` لتصفير array.
10. استعمل `memcpy()` لنسخ array.
11. فهم الفرق بين `memcpy()` و`memmove()` بتجربة overlap.

---

# 04 — `<ctype.h>`

## Concept

Character classification/conversion.

```
#include <ctype.h>
```

أهم functions:

```
isalpha()
isdigit()
isalnum()
isspace()
islower()
isupper()
tolower()
toupper()
```

مثلاً:

```
if (isdigit(c))
{
    printf("Digit\n");
}
```

`tolower()`:

```
char c = tolower('A');
```

---

# Exercises

1. تحقق واش character digit.
2. تحقق واش alphabetic.
3. حول uppercase إلى lowercase.
4. حول lowercase إلى uppercase.
5. عدّ digits فـ string.
6. عدّ spaces.
7. عدّ vowels.

---

# 05 — `<stdbool.h>`

## Concept

Boolean values:

```
bool
true
false
```

```
#include <stdbool.h>
```

مثال:

```
bool is_valid = true;

if (is_valid)
{
    printf("Valid\n");
}
```

مهمة ولكن بسيطة.

### Exercises

1. `is_even()`.
2. `is_positive()`.
3. `is_valid_age()`.
4. function ترجع `true/false` واش string خاوية.

---

# 06 — `<stdint.h>`

هاد المكتبة **مهمة جداً ليك** بسبب Binary + Embedded.

```
#include <stdint.h>
```

كتعطيك sizes واضحة:

```
uint8_t
uint16_t
uint32_t
uint64_t

int8_t
int16_t
int32_t
int64_t
```

مثلاً:

```
uint8_t value = 255;
```

المعنى:

```
uint8_t
unsigned
8 bits
0 → 255
```

وهنا غادي تربط مباشرة مع اللي تعلمتي:

```
8 bits = 1 byte
2^8 = 256 values
0 → 255
```

### Exercises

1. صايب `uint8_t` وعمرو.
2. جرب values خارج range.
3. صايب `uint16_t`.
4. احسب أكبر value لكل type.
5. استعمل `uint8_t` لتمثيل byte.
6. دير program كيحول byte لـ binary.

---

# 07 — `<stddef.h>`

أهم الحوايج:

```
size_t
NULL
ptrdiff_t
```

## `size_t`

نوع unsigned مناسب للأحجام.

مثلاً:

```
size_t len = strlen("Ahmed");
```

وغادي تشوفو بزاف مع:

```
sizeof
strlen
malloc
arrays
```

## `NULL`

مهم مع pointers:

```
int *p = NULL;
```

## `ptrdiff_t`

كيستعمل للفروقات بين pointer values فالسياقات المناسبة.

---

# 08 — `<errno.h>`

هاد المكتبة ديال **error reporting**.

```
#include <errno.h>
```

أهم حاجة:

```
errno
```

مثلاً عملية فشلات وlibrary/system function كتحدد `errno`.

ومن بعد:

```
perror("operation");
```

ولا:

```
strerror(errno);
```

---

## `perror()`

موجودة فـ `<stdio.h>`.

```
perror("fopen");
```

كتطبع message مرتبطة بالـ current `errno`.

---

## `strerror()`

موجودة فـ `<string.h>`.

```
printf("%s\n", strerror(errno));
```

الفرق:

```
perror()
→ كتطبع

strerror()
→ كترجع string
```

---

# 09 — `<assert.h>`

للـ debugging.

```
#include <assert.h>
```

```
assert(x > 0);
```

إلا الشرط false، البرنامج كيوقف ويعطيك معلومات على assertion failure.

استعملها باش تكتاشف **programmer bugs**، ماشي باش تعالج user input العادي.

---

# 10 — `<limits.h>`

كتعطيك limits ديال integer types.

مثلاً:

```
INT_MAX
INT_MIN
UINT_MAX
LONG_MAX
CHAR_BIT
```

مثلاً:

```
printf("%d\n", INT_MAX);
```

مهمة لفهم:

```
bits
types
overflow
ranges
```

---

# 11 — `<float.h>`

للـ floating-point limits.

```
FLT_MAX
FLT_MIN
DBL_MAX
DBL_MIN
```

مهمة ملي تدخل لـ:

```
float
double
precision
overflow
underflow
```

---

# 12 — `<math.h>`

للرياضيات.

أهم functions:

```
sqrt()
pow()
fabs()
floor()
ceil()
round()
sin()
cos()
tan()
log()
exp()
```

مثلاً:

```
double x = sqrt(25.0);
```

و:

```
gcc main.c -lm
```

---

# 13 — `<unistd.h>` — Linux/POSIX

دابا دخلنا لـ **System Programming**.

هاد المكتبة POSIX، ماشي Standard C ISO.

أهم functions:

```
read()
write()
close()
sleep()
getpid()
fork()
exec...
```

مثلاً:

```
write(1, "Hello\n", 6);
```

هنا كتبدأ تفهم العلاقة:

```
C program
   ↓
Linux system
   ↓
system calls
   ↓
kernel
```

هاد الجزء مهم جداً ليك حيث باغي Linux وSystems.

---

# 14 — `<fcntl.h>`

أهم حاجة:

```
open()
```

مثلاً:

```
int fd = open("data.txt", O_RDONLY);
```

وflags:

```
O_RDONLY
O_WRONLY
O_RDWR
O_CREAT
O_APPEND
O_TRUNC
```

هنا غادي تتعلم **file descriptors**:

```
0 → stdin
1 → stdout
2 → stderr
```

وهذا مهم جداً.

---

# 15 — `<sys/types.h>`

كتوفر system-related types.

مثلاً غادي تشوف types بحال:

```
pid_t
ssize_t
off_t
```

مثلاً:

```
pid_t pid;
```

هادشي غادي يبان ملي نتعلمو:

```
process
PID
read/write
files
Linux
```

---

# 16 — `<sys/stat.h>`

مهمة لمعرفة معلومات على files/directories.

أهم function:

```
stat()
```

مثلاً تقدر تعرف:

```
file size
permissions
type
timestamps
```

وكاينين macros باش تفرق بين:

```
regular file
directory
etc.
```

---

# 🎯 دابا شنو خاصك تتقن فعلاً؟

ماشي كل function بنفس الدرجة.

## 🔴 ضروري جداً

```
stdio.h
├── printf
├── scanf
├── fgets
├── getchar
├── fopen
├── fclose
├── fprintf
├── fgetc
├── fputc
├── fread
└── fwrite

stdlib.h
├── malloc
├── calloc
├── realloc
├── free
├── exit
└── strtol

string.h
├── strlen
├── strcpy
├── strcmp
├── strcat
├── strchr
├── strstr
├── memcpy
├── memmove
└── memset

ctype.h
├── isalpha
├── isdigit
├── isspace
├── tolower
└── toupper

stdint.h
├── uint8_t
├── uint16_t
├── uint32_t
└── uint64_t

stddef.h
├── size_t
└── NULL

errno.h
└── errno
```

## 🟠 مهم بعد ذلك

```
assert.h
limits.h
float.h
math.h
```

## 🔵 Linux / Systems

```
unistd.h
fcntl.h
sys/types.h
sys/stat.h
```

---

# المسار ديالك من هنا

ما غاديش نقفزو بين المكتبات.

غادي نخدمو هكذا:

```
stdio.h
   ↓
Exercises
   ↓
stdlib.h
   ↓
Exercises
   ↓
string.h
   ↓
Exercises
   ↓
ctype.h
   ↓
Exercises
   ↓
stdint.h
   ↓
...
   ↓
Linux APIs
```

وكل مكتبة غادي نشرحها **من الداخل: concept → function → parameters → return value → errors → example → exercises**.

**والأهم:** ما غاديش نعطيك حلول التمارين؛ نتا تحاول، وأنا نصحح ونشرح الغلط.

ok

مزيان 👍

إذن نبدأو رسمياً بـ **`stdio.h`**، ومن بعد ما تفهمها وتدير التمارين ديالها، نمشيو لـ `stdlib.h`.

**الدرس الأول: `stdio.h` → Input / Output**.
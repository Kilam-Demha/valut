## 🐛 شنو هو GDB؟

**GDB = GNU Debugger**

هو tool كيساعدك تعرف **شنو كيوقع داخل البرنامج أثناء التنفيذ**.

مثلاً عندك:

```
int a = 10;
int b = 0;

int result = a / b;
```

البرنامج غادي يطيح بـ error أثناء execution.

بـ `gdb` تقدر توقف البرنامج **قبل/وقت المشكل** وتشوف:

```
شنو قيمة a؟
شنو قيمة b؟
فين وصل البرنامج؟
شنو function اللي كان فيها؟
شنو السطر اللي تسبب فالمشكل؟
```

---

# 🧠 الفكرة الأساسية

بلا GDB:

```
Code
 ↓
gcc
 ↓
program
 ↓
💥 error
```

مع GDB:

```
Code
 ↓
gcc -g
 ↓
program
 ↓
GDB
 ↓
▶ وقف هنا
▶ شوف variables
▶ مشي للسطر التالي
▶ دخل للـ function
▶ خرج منها
▶ شوف stack
```

### أهم نقطة

خاصك وقت compilation تستعمل:

```
gcc -g main.c -o program
```

`-g` كتقول لـ GCC:

> حط معلومات debugging داخل executable باش GDB يقدر يربط machine code بالـ source code ديالي.

---

## 🎯 أهم أوامر GDB

من بعد:

```
gdb ./program
```

كتلقى prompt ديال GDB:

```
(gdb)
```

الأوامر الأساسية:

| الأمر         | المعنى                         |
| ------------- | ------------------------------ |
| `run`         | شغّل البرنامج                  |
| `break main`  | حط breakpoint فـ `main`        |
| `next`        | مشي للسطر الموالي              |
| `step`        | دخل داخل function              |
| `continue`    | كمل التنفيذ حتى breakpoint آخر |
| `print x`     | شوف قيمة `x`                   |
| `info locals` | شوف local variables            |
| `backtrace`   | شوف call stack                 |
| `quit`        | خرج من GDB                     |

---

### مثال ذهني

عندك:

```
int main(void)
{
    int x = 10;
    int y = 20;
    int z = x + y;

    return 0;
}
```

GDB يقدر يخليك تمشي هكذا:

```
main()
  ↓
int x = 10
  ↓
int y = 20
  ↓
int z = x + y
  ↓
return 0
```

وفي كل مرحلة تسول البرنامج:

```
(gdb) print x
$1 = 10
```

يعني **GDB ما كيصلحش الكود بوحدو**؛ هو كيخليك **تشوف وتراقب execution ديال البرنامج** باش نتا تعرف فين المشكل.

دابا أحسن حاجة: **نجرّبو GDB بأول تمرين صغير، خطوة بخطوة، وانت اللي تكتب الأوامر.**
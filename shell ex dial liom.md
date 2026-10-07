chof fi shell exercise 3tini nkhdam ala directory jdid

آه، هادي أحسن باش ما تخربطش الملفات ديالك القديمة. 🔥

## 🐚 Shell Mission 1 — Directory جديد

خدم كلشي داخل **directory جديد** سميه:

```
shell-training
```

### المطلوب:

1. صايب الـdirectory.
2. دخل ليه.
3. تأكد من المسار الحالي.
4. صايب داخلو هاد structure:

```
shell-training/
├── projects/
├── notes/
├── backup/
└── temp/
```

5. دخل لـ`projects` وصايب:

```
projects/
├── web/
├── c/
└── scripts/
```

6. رجع لـ`shell-training`.
7. عرض الـstructure كاملة باش نتأكدو أنها صحيحة.

⚠️ **ما غاديش نعطيك حتى command.**  
نتا اختار commands بوحدك.

منين تسالي، صيفط ليا **commands + output** ديالك ونصححو قبل ما نمشيو لـMission 2.

3tini tamarin kamlin nmchi ldar onsaibhom

أكيد. غادي نعطيك **Shell Lab كامل من البداية حتى مستوى Linux Administration 1**، وكل التمارين خدامين داخل **directory جديد واحد** باش تقدر تمشي للدار وتطبقهم كاملين.

⚠️ **ما كايناش commands ولا solutions.** غير المطلوب.  
وخدمهم بالترتيب؛ إلا تمرين صعيب، ما تقفزش للحل.

# 🐚 SHELL LAB — `shell-training`

## المرحلة 1 — Navigation & Directories

### 🟢 Exercise 1 — بداية Lab

داخل `~/Desktop`:

1. صايب directory جديد: `shell-training`.
2. دخل ليه.
3. تأكد من المسار الحالي.
4. صايب:

```
shell-training/
├── projects/
├── notes/
├── backup/
└── temp/
```

5. داخل `projects` صايب:

```
projects/
├── web/
├── c/
└── scripts/
```

6. رجع لـ`shell-training`.
7. عرض structure كاملة.

---

### 🟢 Exercise 2 — Navigation

من داخل `shell-training`:

1. دخل لـ`projects/web`.
2. رجع لـ`projects`.
3. دخل لـ`projects/c`.
4. رجع مباشرة لـ`shell-training`.
5. دخل لـ`notes`.
6. رجع للـparent.
7. تأكد من المسار بعد كل مرحلة.

---

### 🟢 Exercise 3 — Files

صايب:

```
projects/web/
├── index.html
├── style.css
└── app.js

projects/c/
├── main.c
├── utils.c
└── README.txt

projects/scripts/
└── backup.sh

notes/
└── commands.txt
```

من بعد تأكد أن كلشي فالبلاصة الصحيحة.

---

# المرحلة 2 — Create / Copy / Move / Delete

### 🟢 Exercise 4 — Copy

1. نسخ `index.html` إلى `backup`.
2. نسخ `main.c` إلى `backup`.
3. نسخ directory `web` كاملة إلى `backup`.
4. تأكد من النتائج.

---

### 🟢 Exercise 5 — Move

1. نقل `README.txt` من `projects/c` إلى `notes`.
2. نقل `app.js` من `projects/web` إلى `projects/scripts`.
3. تأكد من structure الجديدة.

---

### 🟢 Exercise 6 — Rename

1. بدّل اسم `commands.txt` إلى `shell-commands.txt`.
2. بدّل اسم `style.css` إلى `main.css`.
3. تأكد من الأسماء الجديدة.

---

### 🟢 Exercise 7 — Delete

داخل `temp` صايب:

```
temp/
├── test1.tmp
├── test2.tmp
└── test3.tmp
```

1. حذف `test1.tmp`.
2. حذف `test2.tmp`.
3. خليه `test3.tmp`.
4. صايب directory داخل `temp` فيه files.
5. حذف directory كامل.
6. تأكد أن `test3.tmp` باقي.

---

# المرحلة 3 — `echo` و `cat`

### 🟢 Exercise 8 — كتابة محتوى

داخل `notes/shell-commands.txt`:

كتب 10 أسطر، كل سطر فيه اسم command مختلف.

مثلاً من النوع:

```
navigation
files
search
process
network
```

ولكن **اختار المحتوى بنفسك**.

من بعد عرض المحتوى.

---

### 🟢 Exercise 9 — Append

1. زيد 5 أسطر جداد لنفس الملف.
2. ممنوع تمسح المحتوى القديم.
3. تأكد أن عندك 15 سطر.

---

### 🟢 Exercise 10 — Overwrite

صايب:

```
temp/test.txt
```

1. كتب فيه عدة أسطر.
2. تأكد من المحتوى.
3. استبدل المحتوى كامل بمحتوى جديد.
4. تأكد أن القديم اختفى.

🎯 خاصك تعرف الفرق بين **overwrite** و **append**.

---

# المرحلة 4 — Redirection

### 🟡 Exercise 11 — Output → File

اختار command كيخرج معلومات مفيدة.

1. وجه output ديالو لملف داخل `notes`.
2. عرض الملف.
3. زيد output ثاني لنفس الملف بدون حذف الأول.
4. تأكد من النتيجة.

---

### 🟡 Exercise 12 — Errors

دير command غادي ينتج error.

1. خلي error يمشي لملف.
2. عرض الملف.
3. دير command صحيح ووجه output ديالو لملف آخر.

🎯 فرق بين:

```
stdout
stderr
```

---

### 🟡 Exercise 13 — Combine

دير تجربة فيها:

- output عادي
- error
- ملف واحد فالآخر فيه بجوج

---

# المرحلة 5 — Pipes

### 🟡 Exercise 14 — Basic Pipe

عندك directory فيه files بزاف.

1. جيب list ديال files.
2. مررها لـcommand آخر.
3. خلي النتيجة تبين غير `.txt`.
4. رتب النتيجة.

---

### 🟡 Exercise 15 — Count

استعمل pipeline باش تعرف:

- عدد `.txt`
- عدد `.c`
- عدد `.sh`

داخل `shell-training`.

---

### 🟡 Exercise 16 — Pipeline Challenge

من output كبير:

1. صفي النتائج.
2. رتبها.
3. خذ جزء محدد منها.
4. حسب العدد.

ممنوع intermediate files.

---

# المرحلة 6 — grep

### 🟡 Exercise 17 — Search

صايب:

```
notes/users.txt
```

وحط فيه على الأقل 15 اسم.

خلي بعض الأسماء يتعاودو.

المطلوب:

1. البحث عن اسم معين.
2. البحث case-insensitive.
3. البحث على pattern.
4. حساب عدد النتائج.

---

### 🟡 Exercise 18 — OR

من نفس الملف:

البحث على:

```
Name A OR Name B
```

ومن بعد:

```
Name A OR Name B OR Name C
```

---

### 🟡 Exercise 19 — grep + Pipe

عندك output فيه معلومات كثيرة.

استعمل pipeline باش:

1. تصفي lines معينة.
2. تقلب على pattern.
3. تحسب عدد النتائج.

---

# المرحلة 7 — find

### 🟠 Exercise 20 — Find by Name

داخل `shell-training`:

1. لقا جميع `.txt`.
2. لقا جميع `.c`.
3. لقا جميع `.sh`.
4. لقا `index.html` بالاسم.
5. لقا جميع directories.

---

### 🟠 Exercise 21 — Find by Size

صايب files بأحجام مختلفة.

المطلوب:

1. الملفات الأكبر من حجم معين.
2. الملفات الأصغر من حجم معين.
3. عرض paths فقط.

---

### 🟠 Exercise 22 — Find + Delete

صايب عدة `.tmp`.

1. لقاهم.
2. تأكد منهم.
3. حذفهم.
4. تأكد أنهم اختفاو.

⚠️ ديما **find أولاً → verify → delete**.

---

# المرحلة 8 — Permissions

### 🟠 Exercise 23 — Read / Write / Execute

صايب:

```
notes/private.txt
notes/public.txt
projects/scripts/test.sh
```

المطلوب:

- `private.txt`: owner فقط عندو read/write.
- `public.txt`: يكون readable للآخرين.
- `test.sh`: owner يقدر execute.

تأكد من permissions.

---

### 🟠 Exercise 24 — Numeric Permissions

طبق وفهم:

```
600
644
755
```

على files مختلفة.

قبل كل تغيير، كتب فدفترك شنو كتعني الأرقام.

---

### 🟠 Exercise 25 — Permission Experiment

صايب script.

1. حاول تنفذه قبل permission المناسبة.
2. لاحظ error.
3. أعطِ permission المناسبة.
4. جرب مرة أخرى.

🎯 هنا خاصك تفهم علاش `x` مهمة للـscript.

---

# المرحلة 9 — Processes

### 🔴 Exercise 26 — Process Inspection

المطلوب:

1. عرض processes.
2. تعرف PID ديال process معينة.
3. تعرف user ديالها.
4. تشوف CPU/RAM information.
5. قلب على process بالاسم.

---

### 🔴 Exercise 27 — Kill Process

شغل process طويلة المدة.

1. لقا PID.
2. حاول توقفها بطريقة graceful.
3. تأكد أنها توقفت.
4. جرب signal أقوى على process تجريبية أخرى.

🎯 فهم:

```
PID
SIGTERM
SIGKILL
```

---

# المرحلة 10 — Environment

### 🔴 Exercise 28 — Variables

المطلوب تعرف:

1. user الحالي.
2. home directory.
3. current directory.
4. `PATH`.
5. shell المستعمل.

من بعد:

6. صايب environment variable مؤقتة.
7. استعملها فـcommand.
8. فتح terminal جديد وشوف واش بقات.

---

### 🔴 Exercise 29 — PATH

1. عرض `PATH`.
2. عرف فين كاين executable ديال command معين.
3. صايب directory خاص بيك.
4. حط فيه executable تجريبي.
5. خليه accessible من أي directory عبر `PATH`.
6. جربه.
7. رجع `PATH` للحالة الأصلية.

---

# المرحلة 11 — Shell Scripting

### 🔴 Exercise 30 — First Script

داخل:

```
projects/scripts/
```

صايب:

```
system-info.sh
```

خاصو يعرض:

```
User:
Home:
Current directory:
Date:
Shell:
```

المعلومات خاصها تجي من النظام.

---

### 🔴 Exercise 31 — Arguments

طور script آخر:

```
hello.sh
```

المستخدم يعطيه name.

خاصو يطبع greeting باستعمال argument.

🎯 فهم:

```
$0
$1
$2
$#
```

---

### 🔴 Exercise 32 — File Checker

صايب script كيأخذ path.

خاصو يحدد واش:

```
File
Directory
Does not exist
```

---

### 🔴 Exercise 33 — Conditions

صايب script كيأخذ filename.

خاصو:

1. يتأكد واش الملف موجود.
2. يتأكد واش readable.
3. يتأكد واش writable.
4. يعطي message مناسبة لكل حالة.

---

### 🔴 Exercise 34 — Loop

صايب script كيأخذ directory.

خاصو:

1. يدوز على files.
2. يطبع `.txt`.
3. يطبع `.c`.
4. يطبع `.sh`.
5. يحسب العدد ديال كل نوع.

---

### 🔴 Exercise 35 — Backup Script

صايب:

```
backup.sh
```

خاصو:

1. ياخذ source directory.
2. يتأكد أن directory موجود.
3. يصايب backup.
4. يعطي success message.
5. إذا وقع error يعطي error message.
6. يرجع exit status مناسب.

---

# المرحلة 12 — Linux Administration Level 1

### 🔥 Exercise 36 — Users

المطلوب تعرف:

- current user
- UID
- GID
- groups
- users الموجودين فالنظام

---

### 🔥 Exercise 37 — Disk

المطلوب:

- disk space
- used
- available
- filesystem
- حجم `~/Desktop`
- أكبر directories فـhome

---

### 🔥 Exercise 38 — Memory

جيب:

- Total RAM
- Used
- Free
- Available
- Swap

ومن بعد فسر الفرق بين **free** و **available**.

---

### 🔥 Exercise 39 — Network

المطلوب تعرف:

- network interfaces
- IP address
- default gateway
- DNS
- connectivity

---

### 🔥 Exercise 40 — Services

اختار service موجودة فالنظام وماشي critical.

1. شوف status.
2. وقفها.
3. تأكد.
4. شغلها.
5. تأكد مرة أخرى.

---

### 🔥 Exercise 41 — Logs

قلب فـsystem logs على:

- errors
- warnings
- authentication events

ومن بعد:

1. filter.
2. search بـpattern.
3. count results.

---

# 🧨 Exercise 42 — Mini Linux Admin Project

دابا استعمل نفس `shell-training`.

خاصك تدير workflow كامل:

```
shell-training/
├── projects/
│   ├── web/
│   ├── c/
│   └── scripts/
├── notes/
├── backup/
└── temp/
```

وتطبق:

**Navigation → Files → Copy/Move → Delete → echo/cat → Redirection → Pipes → grep → find → Permissions → Processes → Variables → PATH → Scripts → Users → Disk → RAM → Network → Services → Logs**

وفي الأخير صايب script واحد اسميه:

```
admin-report.sh
```

يخرج تقرير فيه:

```
===== SYSTEM =====

User:
Hostname:
Date:
Shell:

===== DISK =====

...

===== MEMORY =====

...

===== NETWORK =====

...

===== PROJECT =====

Number of .c:
Number of .sh:
Number of .txt:
```

🔥 **هاد Exercise 42 هو الامتحان ديالك.**

وبالنسبة للدار: **ما تحتاجش تحفظ الأوامر قبل ما تبدأ**. حاول تحل كل Exercise من الذاكرة، وإذا نسيت command، رجع للـ`man` أو `tldr` وشوف غير syntax ديالو، ومن بعد كمل بوحدك.
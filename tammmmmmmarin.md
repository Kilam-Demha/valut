chof mat3tinich lcommands rah baghi nt3alam

عندك الحق 👍 غلطتي مني. إلا عطيتك الـcommands، كنحيد عليك أهم جزء من التعلم: **التفكير واختيار الأمر المناسب**.

من دابا فتمارين Git غادي نعطيك **الوضعية + المطلوب فقط**، وانت اللي خاصك تحدد commands.

### 🧠 Homework — بلا حتى command

#### 1. Lost Commit

عندك:

```
	A---B---C---D
            ↑
           main
```

بالغلط رجعتي `main` لـ `B`.

**المطلوب:**

- `C` و`D` ما بقاوش باينين فـ history العادية.
- خاصك تلقى `D`.
- رجع `main` لـ `D`.

---

#### 2. Soft / Mixed / Hard

عندك commit `C` وعندك changes فـ working directory.

بغيت ترجع commit واحد للور، ولكن:

**A)** تبقى changes فـ staging.

**B)** تبقى changes فالـworking directory ولكن ماشي staged.

**C)** تتحيد changes نهائياً.

حدد شنو العملية المناسبة لكل حالة، **بلا ما تنفذها دابا**.

---

#### 3. Merge Conflict

عندك:

```
main:
A---B---C

feature:
    \
     D
```

نفس السطر تبدل فـ `C` و `D`.

منين تجمع `feature` مع `main` وقع conflict.

**المطلوب:**

- كيفاش تعرف شنو جا من `main` وشنو جا من `feature`؟
- من بعد ما تصلح الملف، شنو المراحل اللي خاص Git يدوز منها حتى يكمل merge؟

---

#### 4. Rebase

عندك:

```
A---B---C  main
     \
      D---E  feature
```

بغيت `feature` تبني خدمتها فوق آخر `main`.

**المطلوب:**  
رسم الـhistory من بعد العملية، وشرح علاش commits ديال `feature` غادي يكون عندها SHA جديد.

---

#### 5. Stash

أنت خدام على feature ومازال ما ساليتش.

عندك changes مهمة، وفجأة خاصك تبدل لـ`main` باش تصلح bug.

**المطلوب:**

كيفاش:

```
تحفظ الخدمة المؤقتة
        ↓
تمشي للـmain
        ↓
تصلح bug
        ↓
ترجع للـfeature
        ↓
ترجع خدمتك
```

**بلا commands.** غير شرح الـworkflow.

---

#### 6. Remote

عندك:

```
LOCAL:
A---B

REMOTE:
A---B---C
```

بغيت **تشوف شنو كاين فالـremote بلا ما تدخل C مباشرة فـlocal branch**.

**المطلوب:**

شنو المفهوم/العملية اللي خاصك تستعمل؟ وعلاش؟

---

#### 7. Push Rejected

عندك:

```
REMOTE:
A---B---C

LOCAL:
A---B---D
```

درت محاولة باش تصيفط `D` ولكن Git رفض.

**المطلوب:**

فسر علاش وقع الرفض، وشنو خاصك تدير باش تجمع `C` و`D` بطريقة آمنة.

---

#### 8. Final Boss 🧠

عندك:

```
A---B---C---D  main
     \
      E---F---G  feature
```

بالغلط حركتي `feature` للور، ومن بعد درتي commits جداد.

دابا ما بقاتش `F` و`G` ظاهرة فـ`git log`.

**المطلوب:**

- فين غادي تقلب عليهم؟
- كيفاش غادي تتأكد أنهم هما commits الصحيحة؟
- كيفاش ترجعهم **بلا ما تضيع commits الجديدة**؟

---

**هاد المرة ما كاين حتى command مقترح.** 😄  
نتا فكر، كتب الحل ديالك، وأنا نصحح **غير التفكير ديالك** قبل ما نوريك أي command.

chof zid chi wahdin akhrin

أكيد. هاد المرة غادي نعطيك **تمارين أكثر وواقعية أكثر**، وبلا حتى command. الهدف هو تخدم الـlogic ديالك، ماشي تحفظ الأوامر.

# 🧠 Git Brain Training — مجموعة جديدة

## 🟢 المستوى 1 — فهم الـHistory

### 1. شكون واقف فين؟

عندك:

```
A---B---C---D  main
         \
          E---F  feature
```

أنت حالياً خدام على `feature`.

حدد:

- فين كيشاور `HEAD`؟
- فين كيشاور `main`؟
- فين كيشاور `feature`؟
- شكون parent ديال `F`؟
- شنو آخر commit مشترك بين `main` و`feature`؟

---

### 2. Branch ماشي نسخة

عندك:

```
A---B---C
        ↑
       main
```

صايبتي branch جديدة من `C`.

من بعد ديرتي commit جديد فالـbranch.

**المطلوب:**

واش `main` غادي تتحرك معاه؟

فسر علاش.

---

### 3. حذف Branch

عندك:

```
A---B---C---D
        \
         E---F
```

`feature` فيها `E` و`F`.

تحيدات branch `feature`.

**المطلوب:**

- واش `E` و`F` تحيدو مباشرة؟
- واش مازال ممكن تلقاهم؟
- شنو الفرق بين "branch تحيدات" و"commit تحيد"؟

---

# 🟡 المستوى 2 — Staging / Working Tree

### 4. جوج ملفات

عندك:

```
app.c
README.md
```

بدلتي بجوج.

ولكن بغيتي commit غير `app.c`.

**المطلوب:**

شنو خاصك تدير باش:

```
app.c    → داخل commit
README   → يبقى modified
```

---

### 5. Partial Commit

عندك `app.c` فيه:

```
change 1
change 2
change 3
```

بغيتي commit غير `change 1` و`change 3`.

**المطلوب:**

كيفاش تقدر تخلي جزء من modifications يدخل للـstaging وجزء يبقى؟

---

### 6. Commit غلط

درت commit ولكن نسيت file واحد.

دابا:

```
A---B
```

و`B` فيها modifications، ولكن واحد الملف ما دخلش.

**المطلوب:**

بغيتي تصلح آخر commit **بدون إنشاء commit جديد**.

شنو المفهوم اللي خاصك تفكر فيه؟

---

# 🟠 المستوى 3 — Reset / Revert

### 7. Local mistake

عندك:

```
A---B---C
```

`C` فيها mistake، ومازال ما صيفطتيهاش لأي remote.

بغيتي تمحي `C` وكأنها ما كانتش.

شنو النوع ديال العملية اللي كتفكر فيها؟

---

### 8. Public mistake

نفس الحالة:

```
A---B---C
```

ولكن `C` راه already pushed والناس خدامين عليها.

بغيتي تلغي effect ديال `C` **مع الحفاظ على history**.

شنو المفهوم المناسب؟

---

### 9. الفرق الحقيقي

عندك:

```
A---B---C---D
```

بغيتي تلغي `C`.

**السؤال:**

شنو الفرق فالـhistory إذا:

- رجعتي branch للور؟
- ولا أنشأتي commit جديدة كتعاكس `C`؟

رسم الجوج.

---

# 🔵 المستوى 4 — Merge / Rebase

### 10. Fast-forward ولا لا؟

الحالة الأولى:

```
A---B---C  main
         \
          D---E feature
```

الحالة الثانية:

```
A---B---C---X  main
     \
      D---E    feature
```

**المطلوب:**

فأي حالة ممكن Git يدير Fast-Forward؟

وعلاش؟

---

### 11. Merge Commit

عندك:

```
A---B---C  main
     \
      D---E feature
```

كل branch تطور بوحدو.

من بعد merge.

**المطلوب:**

رسم شكل history من بعد merge، وحدد:

- parents ديال merge commit
- branch اللي غادي يتحرك
- commits القديمة اللي غادي تبقى

---

### 12. Rebase ومشكلة الـHistory

عندك:

```
A---B---C  main
     \
      D---E feature
```

درت rebase.

**المطلوب:**

علاش ما خاصكش تعتبر `D'` هو نفس `D`؟

جاوب من ناحية:

```
parent
SHA
identity of commit
```

---

# 🔴 المستوى 5 — Conflict

### 13. Conflict ولا لا؟

عندك file:

```
line 1
line 2
line 3
```

`main` بدلات `line 1`.

`feature` بدلات `line 3`.

**المطلوب:**

واش كتوقع conflict؟

وعلاش؟

---

### 14. Conflict حقيقي

`main`:

```
printf("Hello");
```

`feature`:

```
printf("Hi");
```

نفس السطر تبدل فالجوج.

**المطلوب:**

علاش Git ما يقدرش يختار بوحدو؟

وشكون خاصو ياخذ القرار؟

---

### 15. Conflict أثناء Rebase

وقع conflict أثناء rebase.

**المطلوب:**

شنو الفرق فالتفكير بين:

```
merge conflict
```

و:

```
rebase conflict
```

واش الهدف النهائي مختلف؟

---

# 🟣 المستوى 6 — Remote

### 16. Local commit

عندك:

```
LOCAL:
A---B---C

REMOTE:
A---B
```

`C` غير local.

**المطلوب:**

فين كاينة `C`؟

وشكون يقدر يشوفها؟

---

### 17. Remote commit

عندك:

```
LOCAL:
A---B

REMOTE:
A---B---C
```

بغيت تعرف `C` ولكن ما بغيتيش تبدل files ديالك.

**المطلوب:**

شنو العملية اللي كتفكر فيها؟

---

### 18. Pull

عندك:

```
LOCAL:
A---B---D

REMOTE:
A---B---C
```

درت pull.

**المطلوب:**

شنو ممكن يوقع؟

عطي **جوج احتمالات** حسب configuration/strategy.

---

# ⚫ المستوى 7 — Git Stash

### 19. Stash واحد

عندك:

```
feature
```

وفيها changes مازال ما كملتيش.

بغيتي تبدل branch بلا ما تعمل commit.

**المطلوب:**

شنو المفهوم اللي كيخليك تخبي changes مؤقتاً؟

---

### 20. جوج Stashes

درت:

```
stash A
stash B
```

وبغيتي ترجع غير `A`.

**المطلوب:**

كيفاش غادي تعرف شنو فيه كل واحد قبل ما تطبقو؟

---

# ☠️ المستوى 8 — Recovery

### 21. Accident

كنت هنا:

```
A---B---C---D
```

درت reset للور.

من بعد ساعة:

```
git log
```

ما بقاتش `D`.

**المطلوب:**

شنو أول مكان غادي تقلب فيه؟

وعلاش؟

---

### 22. Branch Deleted

عندك branch:

```
feature → F
```

تحيدات بالغلط.

ولكن آخر commit ديالها كان `F`.

**المطلوب:**

واش commit `F` ضاعت بالضرورة؟

فين غادي تقلب؟

---

# ☠️☠️ المستوى 9 — Team Scenarios

### 23. أنت وواحد آخر

نتا:

```
A---B---D
```

زميلك:

```
A---B---C
```

`C` و`D` مختلفين.

كل واحد دفع changes ديالو.

**المطلوب:**

كيفاش تفكر باش تجمع بجوج التغييرات بلا ما تضيع حتى واحد؟

---

### 24. Force Push Disaster

عندك remote:

```
A---B---C---D
```

واحد دار force push وولات:

```
A---B---X---Y
```

`C` و`D` ما بقاوش فالـremote branch.

**المطلوب:**

واش `C` و`D` بالضرورة ضاعو من كل machines؟

فين يمكن تلقاهم؟

---

### 25. Rebase بعد Push

عندك branch `feature`، درتي عليها commits ودفعتيها للـremote.

من بعد درتي rebase محلياً.

**المطلوب:**

علاش push عادي ممكن يترفض؟

شنو تبدل فالـhistory من وجهة نظر Git؟

---

# ☠️☠️☠️ Final Boss

### 26. Team Incident

الحالة:

```
                D---E---F  feature
               /
A---B---C-----G---H  main
```

واحد من team دار rebase لـ`feature` فوق `H`.

من بعد شخص آخر خدم على نفس `feature` ودفع changes.

دابا الناس مختلفين فـhistory.

**المطلوب:**

حلل المشكلة فقط:

1. شنو تبدل؟
2. علاش SHA ديال commits تبدلات؟
3. علاش Git كيعتبر بعض commits مختلفة؟
4. شنو الخطر ملي تدير rebase على branch مشتركة؟
5. كيفاش الفريق يقدر يتعامل مع هاد الحالة بأمان؟

---

### 🎯 قانون التمرين

فأي تمرين، **ممنوع تبدأ بالـcommand**.

أولاً كتب:

```
WHAT HAPPENED?
WHY?
WHAT DO I WANT?
WHAT GIT CONCEPT FITS?
```

ومن بعد **نتا** اختار command.

هاد الطريقة هي اللي غادي تخليك تفهم Git فعلاً، ماشي غير تحفظ `reset / rebase / merge / stash`.


أكيد. غادي ندير ليك **Shell Brain Training** بنفس الطريقة: **الوضعيات والمشاكل فقط، بلا commands**. نتا خاصك تفكر وتختار command/concept بوحدك. 🧠

# 🧠 Shell Brain Training

## 🟢 Level 1 — Files & Directories

### 1. Directory Detective

عندك:

```
project/
├── src/
│   ├── main.c
│   └── utils.c
├── include/
│   └── utils.h
└── README.md
```

**المطلوب:**

أنت واقف داخل `project`.

- دخل لـ`src`.
- رجع لـ`project`.
- دخل لـ`include`.
- رجع مباشرة للـhome directory.
- رجع لـ`project` باستعمال path مناسب.

---

### 2. Create Structure

خاصك تصايب هاد structure:

```
myapp/
├── src/
│   ├── main.c
│   └── utils.c
├── include/
│   └── utils.h
├── tests/
└── README.md
```

**المطلوب:** صايبها كاملة بأقل عدد ممكن من العمليات.

---

### 3. Move Files

عندك:

```
project/
├── main.c
├── old.c
└── src/
```

بغيتي:

```
project/
├── src/
│   ├── main.c
│   └── old.c
```

**المطلوب:** نقل الملفات، ماشي نسخهم.

---

### 4. Rename

عندك:

```
notes.txt
```

بغيتي تولي:

```
git-notes.txt
```

**المطلوب:** غير تبديل الاسم، بلا إنشاء نسخة جديدة.

---

# 🟡 Level 2 — Copy / Remove

### 5. Backup

عندك:

```
project/
└── src/
    ├── main.c
    ├── utils.c
    └── test.c
```

بغيتي تصايب:

```
backup/
└── src/
    ├── main.c
    ├── utils.c
    └── test.c
```

**المطلوب:** `backup` تكون نسخة مستقلة من `src`.

---

### 6. Delete Carefully

عندك:

```
project/
├── temp.txt
├── notes.txt
└── backup/
    ├── old1.txt
    └── old2.txt
```

بغيتي:

- تحيد `temp.txt`
- تحيد `backup` كاملة بمحتوياتها
- تخلي `notes.txt`

**المطلوب:** فكر مزيان فكل عملية قبل التنفيذ.

---

### 7. Copy vs Move

عندك:

```
downloads/
└── file.txt
```

بغيتي توصل لـ:

```
documents/
└── file.txt
```

ولكن:

**A)** `file.txt` يبقى حتى فـdownloads.

**B)** `file.txt` ما يبقاش فـdownloads.

حدد فكل حالة شنو العملية المناسبة.

---

# 🟠 Level 3 — Viewing Files

### 8. Large File

عندك:

```
server.log
```

فيه **مئات الآلاف ديال السطور**.

بغيتي تشوف:

- البداية فقط
- النهاية فقط
- آخر السطور اللي كيزيدهم البرنامج باستمرار

**المطلوب:** اختار الأدوات المناسبة لكل حالة.

---

### 9. Search Inside File

عندك:

```
server.log
```

فيه:

```
INFO User connected
ERROR Database failed
INFO Request received
WARNING Memory high
ERROR Connection refused
```

بغيتي:

- تلقى جميع `ERROR`
- تلقى `ERROR` بلا ما تكون case-sensitive
- تعرف عدد المرات اللي ظهر فيها `ERROR`

---

### 10. Search Multiple Files

عندك:

```
src/
├── main.c
├── utils.c
├── parser.c
└── test.c
```

بغيتي تعرف **فين مستعمل `printf`**.

**المطلوب:** قلب داخل جميع الملفات.

---

# 🔵 Level 4 — Pipes & Redirection

### 11. Pipeline

عندك directory فيه بزاف ديال الملفات.

بغيتي:

```
files
 ↓
sort
 ↓
choose only some results
```

**المطلوب:** فكر كيفاش تربط output ديال command بـinput ديال command أخرى.

---

### 12. Save Output

بغيتي نتيجة command معينة:

**A)** تظهر فـterminal وتبقى حتى فـfile.

**B)** تمشي للـfile فقط.

**C)** تزيد النتيجة الجديدة للـfile القديمة بلا ما تمسحها.

حدد concept المناسب لكل حالة.

---

### 13. Error Redirection

عندك command كتنتج:

```
normal output
+
error messages
```

بغيتي:

- normal output يبقى فـterminal
- errors يمشيو لـ`errors.txt`

---

### 14. Everything to File

بغيتي تجمع:

```
stdout
stderr
```

بجوجهم فـ:

```
output.log
```

**المطلوب:** فكر فـfile descriptors والـredirection.

---

# 🔴 Level 5 — grep / find

### 15. Find by Name

عندك:

```
project/
├── src/
│   ├── main.c
│   ├── test.c
│   └── helper.py
├── backup/
│   └── old.c
└── README.md
```

بغيتي تلقى **جميع `.c` files** داخل `project` وجميع subdirectories.

---

### 16. Find by Type

بغيتي تلقى:

- جميع directories
- جميع regular files
- جميع `.txt` files

**المطلوب:** استعمل التفكير ديال `find` conditions.

---

### 17. Find + Action

عندك:

```
project/
├── a.tmp
├── b.tmp
├── c.c
└── d.tmp
```

بغيتي تلقى جميع `.tmp` files.

ولكن **ما تحيدهمش مباشرة**.

أولاً بغيت تشوف شنو غادي يتحيد.

من بعد فقط تنفذ الحذف.

---

# 🟣 Level 6 — Permissions

### 18. Permission Analysis

عندك:

```
-rwxr-x---
```

**المطلوب:**

فسر:

```
owner
group
others
```

وشنو يقدر كل واحد يدير.

---

### 19. Make Script Executable

عندك:

```
backup.sh
```

الـscript ما كيتنفذش مباشرة.

**المطلوب:** بدل permissions بحيث owner يقدر execute.

وخلي permissions الأخرى كما هي.

---

### 20. Shared Script

بغيتي:

```
owner  → read/write/execute
group  → read/execute
others → read فقط
```

حدد permission representation المناسبة.

---

# ⚫ Level 7 — Processes

### 21. Find Process

برنامج ديالك خدام فالخلفية.

بغيتي تعرف:

- PID ديالو
- شكون user اللي شغلو
- شحال CPU كيستعمل
- شحال memory كيستعمل

**المطلوب:** اختار الأدوات المناسبة.

---

### 22. Kill Process

عندك process عالق.

**A)** بغيتي تطلب منو يسالي بطريقة عادية.

**B)** ما تجاوبش وبغيتي توقفو بالقوة.

شنو الفرق فالتعامل بين الحالتين؟

---

# ☠️ Level 8 — Shell Logic

### 23. AND

بغيتي:

> "نفذ command B **غير إلا نجحات** command A."

حدد operator/concept المناسب.

---

### 24. OR

بغيتي:

> "نفذ command B **غير إلا فشلات** command A."

حدد operator.

---

### 25. Chain

بغيتي:

```
create directory
      ↓
enter directory
      ↓
create file
```

ولكن إلا فشلت خطوة، **ما تكملش**.

صمم workflow مناسب.

---

# ☠️☠️ Level 9 — Variables

### 26. Variable

بغيتي تخزن:

```
Ahmed
```

فـShell variable.

من بعد تستعمل القيمة فـcommand أخرى.

**المطلوب:** فكر فـ:

```
creation
access
```

---

### 27. Environment

عندك variable وبغيتي programs اللي كتطلقهم من shell يقدرو يشوفوها.

**السؤال:**

شنو الفرق بين **shell variable** و**environment variable**؟

---

# ☠️☠️ Level 10 — Redirection Brain

### 28. Three Streams

برنامج عندو:

```
stdin
stdout
stderr
```

**المطلوب:**

شرح شنو الدور ديال كل واحد، ومن بعد تخيل أنك بغيتي:

```
stdin  ← file
stdout → output.txt
stderr → errors.txt
```

شنو concepts خاصك تجمع؟

---

### 29. Pipe + grep

عندك command كتخرج:

```
100 lines
```

بغيتي:

```
command output
       ↓
only lines containing "error"
       ↓
save them into errors.txt
```

**المطلوب:** صمم الـpipeline ذهنياً قبل ما تكتب أي command.

---

# ☠️☠️☠️ Final Boss — Shell

### 30. Log Investigation

عندك:

```
~/project/logs/
├── app.log
├── server.log
├── database.log
└── old/
    ├── app.log
    └── server.log
```

بغيتي تحقق فـمشكل وقع:

> "لقا جميع السطور اللي فيها `ERROR` داخل جميع `.log` files، عرف شحال من مرة تكررت، وخزن النتائج فـ`error-report.txt`."

**ممنوع تستعمل Python أو script.**

خاصك تفكر فـ:

```
find
   ↓
files
   ↓
search
   ↓
count
   ↓
redirect
```

---

## 🧠 طريقة الحل ديالك

قبل كل تمرين كتب:

```
WHAT DO I HAVE?
WHAT DO I WANT?
WHICH SHELL CONCEPT FITS?
WHAT COMMAND SHOULD I CHOOSE?
```

ومن بعد كتب command ديالك.

**ما غاديش نعطيك الحل حتى تحاول.**
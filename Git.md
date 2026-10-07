
aujourd’hui 20:49

سلام بغيتك تعاوني نفهم git بطريقة احترافية من الاول

وعليكم السلام أحمد 👋

أكيد. إلا بغيتي تتعلم **Git بطريقة احترافية من الصفر**، ما غاديش نبدأو بحفظ أوامر بحال `git add` و `git commit` وخلاص. غادي نبنيو الفهم ديال **كيفاش Git خدام من الداخل**، ومن بعد الأوامر غادي يولو منطقيين.

### الخطة ديالنا

غادي نمشيو بهاد الترتيب:

1. **شنو هو Git؟** وعلاش أصلاً تدار؟
2. **Repository** وشنو كيتخزن فيه
3. الفرق بين:
    - Working Directory
    - Staging Area
    - Repository
4. `git init`
5. `git status`
6. `git add`
7. `git commit`
8. كيفاش Git كيتبع التغييرات
9. `git log`
10. `git diff`
11. التراجع: `restore`, `reset`, `revert`
12. **Branches** وكيفاش خدامين فعلياً
13. `merge`
14. حل **merge conflicts**
15. GitHub وRemote
16. `push`, `pull`, `fetch`
17. `clone`
18. `.gitignore`
19. Tags
20. Git workflow احترافي
21. SSH مع GitHub
22. التعامل مع المشاريع الحقيقية والـteam

**وكل مرحلة فيها تمرين عملي**، وما نعطيكش الحل مباشرة إلا طلبتيه.

---

# الدرس 1 — شنو هو Git؟

تخيل عندك مشروع:

```
my-project/
├── index.html
├── style.css
└── script.js
```

نهار 1:

```
index.html
```

نهار 2 بدلت الكود.

نهار 3 زدت feature.

نهار 4 خربتي شي حاجة وبغيتي ترجع للحالة ديال نهار 2.

إلا كنت خدام غير بالملفات، تقدر تدير:

```
project-final/
project-final-2/
project-final-new/
project-final-new2/
project-final-LAST/
project-final-LAST-REAL/
```

😂

Git جا باش يحل هاد المشكل.

---

# الفكرة الأساسية

**Git هو Version Control System.**

يعني نظام كيخليك تتبع **تاريخ التغييرات** ديال المشروع.

مثلاً:

```
              Git History

        ┌───────────────┐
        │  Project V1   │
        └───────┬───────┘
                │
                ▼
        ┌───────────────┐
        │  Project V2   │
        └───────┬───────┘
                │
                ▼
        ┌───────────────┐
        │  Project V3   │
        └───────┬───────┘
                │
                ▼
        ┌───────────────┐
        │  Project V4   │
        └───────────────┘
```

كل نقطة هنا كتسمى:

**Commit**

والـcommit هو بحال **snapshot** للحالة ديال المشروع فواحد اللحظة.

---

# ولكن هنا كاينة نقطة مهمة جداً

Git ماشي هو GitHub.

### Git

برنامج كيخدم عندك فالحاسوب:

```
Your Computer
     │
     └── Git
```

### GitHub

خدمة online كتقدر تخزن فيها Git repositories وتعاونك تخدم مع الآخرين.

```
Your Computer
     │
     │ Git
     ▼
   GitHub
```

يعني تقدر تستعمل Git **بلا GitHub**.

وهذه من أول الحوايج اللي خاصك تفهم مزيان.

---

# دابا أهم concept فـ Git

كاينين **3 أماكن** خاصك تفهمهم قبل ما نحفظو الأوامر:

```
Working Directory
       │
       │ git add
       ▼
Staging Area
       │
       │ git commit
       ▼
Repository
```

مثلاً عندك:

```
index.html
```

كتعدل فيه.

التغيير دابا موجود غير فـ:

```
Working Directory
```

منين تدير:

```
git add index.html
```

التغيير كيمشي للـ:

```
Staging Area
```

ومن بعد:

```
git commit
```

كيدخل للتاريخ ديال Git:

```
Repository
```

هاد الثلاثة خاصهم يرسخو عندك قبل ما نمشيو بعيد.

---

## أول تجربة عملية

بما أنك كتستعمل Linux Mint، حل Terminal ودير:

```
mkdir git-learning
cd git-learning
```

ومن بعد:

```
git init
```

غادي تشوف تقريباً:

```
Initialized empty Git repository...
```

دابا Git بدا يتبع هاد المشروع.

ثم:

```
git status
```

**ما تدير حتى حاجة أخرى دابا.**

بغيتك تجرب هاد جوج أوامر وتشوف النتيجة.

ومن بعد صيفط ليا **الـoutput ديال `git status`**، وغادي نشرح لك بالضبط شنو وقع وشنو هو `.git` وعلاش Git قدر يعرف حالة المشروع.

مزيان. دابا نكملو، ولكن غادي نزيدو شوية فالعمق باش ما يبقاش Git عندك غير أوامر محفوظة.

# 18. شنو هو Commit بالضبط؟

قلنا أن:

```
git commit -m "message"
```

كيدير snapshot.

ولكن تقنياً، الـcommit ماشي "نسخة كاملة من جميع الملفات" بالطريقة اللي ممكن تتخيل.

Git مبني على **objects** وكيستعمل hashes باش يحدد المحتوى.

الفكرة المبسطة:

```
Commit
  │
  ├── Metadata
  │     ├── author
  │     ├── date
  │     └── message
  │
  └── points to project state
```

يعني الـcommit كيقول تقريباً:

> "هاد الـcommit كيمثل هاد الحالة من المشروع، وكيجي من بعد commit سابق."

ولهذا Git يقدر يبني التاريخ:

```
A ← B ← C ← D
```

كل commit مرتبط باللي قبله.

---

# 19. علاش Git سريع؟

حيت Git كيستعمل **hashing**.

مثلاً عندك محتوى:

```
Hello
```

Git كيحسب ليه identifier.

إلا تبدل المحتوى:

```
Hello Ahmed
```

كيكون identifier مختلف.

الفكرة:

```
Content
   │
   ▼
Hash
```

ولهذا Git يقدر يميز بين المحتويات والتغييرات.

ما محتاجش دابا تدخل فالتفاصيل الرياضية ديال SHA-1/SHA-256؛ المهم تفهم المبدأ.

---

# 20. `HEAD` — واحد المفهوم مهم

غادي تسمع بزاف:

```
HEAD
```

شنو هو؟

بشكل مبسط جداً:

> **HEAD كيشير للمكان اللي Git واقف فيه دابا.**

مثلاً:

```
A ─── B ─── C
            ▲
           HEAD
```

يعني Git حالياً واقف عند `C`.

إلا مشينا لشي commit آخر:

```
A ─── B ─── C
      ▲
     HEAD
```

HEAD ولى كيشير لـB.

هاد المفهوم غادي يولي مهم جداً ملي نشرحو:

```
git checkout
git switch
git reset
```

---

# 21. `HEAD` و Branch

هنا غادي نربطو جوج concepts.

مثلاً:

```
A ─── B ─── C
            ▲
           main
            ▲
           HEAD
```

هنا:

```
HEAD → main → C
```

يعني HEAD كيشير للـbranch، والـbranch كتشير لآخر commit.

إلا زدنا commit:

```
A ─── B ─── C ─── D
                 ▲
                main
                 ▲
                HEAD
```

الـbranch كتتحرك للـcommit الجديد.

---

# 22. Branch بالتدريج

عندنا:

```
A ─── B ─── C
            ▲
           main
```

بغينا نخدمو feature جديدة.

نديرو:

```
git switch -c login
```

دابا:

```
A ─── B ─── C
            ▲
           main
            ▲
          login
            ▲
           HEAD
```

لاحظ:

**ما تصاوبش project جديد.**

غير صاوبنا branch جديدة سميتها `login`.

---

من بعد درنا commit:

```
A ─── B ─── C ─── D
            │      ▲
            │     login
            │      ▲
            │     HEAD
            │
           main
```

دابا:

```
main  → C
login → D
HEAD  → login
```

وهذا هو مفهوم الـbranch الحقيقي.

---

# 23. علاش Branch مهمة؟

تخيل أنت خدام على website.

عندك:

```
main
```

وفيه النسخة المستقرة.

بغيتي تزيد:

```
Dark Mode
```

بدل ما تخاطر بـ`main`:

```
main
```

كتدير:

```
feature/dark-mode
```

وتخدم تما:

```
main
   │
   ●
   │
   ●───────────────
                  \
                   ●
                   ●
                dark-mode
```

منين تسالي ونتأكد أن كلشي خدام، غادي نتعلمو كيفاش ندمجوها مع `main`.

هاد العملية سميتها:

**Merge**

---

# 24. Merge

مثلاً:

```
A ─── B ─── C
            \
             D ─── E
```

عندنا:

```
main → C
feature → E
```

بغينا ندخلو feature لـmain.

نديرو merge.

النتيجة ممكن تكون:

```
A ─── B ─── C ─── D ─── E
```

أو Git يقدر يصاوب **merge commit** حسب الحالة:

```
        D ─── E
       /       \
A ─── B ─── C ─── M
```

وغادي نشرح الفرق بين الحالات ملي نوصلو للـmerge.

---

# 25. Merge Conflict

دابا تخيل:

أنت بدلت نفس السطر:

```
<h1>Hello Ahmed</h1>
```

وشخص آخر بدلو لـ:

```
<h1>Hello World</h1>
```

Git يقدر ما يعرفش شنو تختار.

كيقول:

```
CONFLICT
```

مثلاً الملف يقدر يولي:

```
<<<<<<< HEAD
<h1>Hello Ahmed</h1>
=======
<h1>Hello World</h1>
>>>>>>> feature
```

هنا **Git ما غاديش يقرر بدالك**.

أنت خاصك تختار شنو بغيتي:

```
<h1>Hello Ahmed</h1>
```

أو:

```
<h1>Hello World</h1>
```

أو حتى تجمع بجوج.

ومن بعد كتصلح conflict وكتكمل الـmerge.

---

# 26. دابا Remote

حتى الآن كلشي كان فالحاسوب:

```
Your PC
└── repository
```

ولكن فالمشاريع الحقيقية، غالباً عندك remote:

```
Your PC                    GitHub
   │                          │
   │──────── push ───────────►│
   │                          │
   │◄──────── pull ───────────│
```

الـremote مجرد repository بعيد.

غالباً كتسميه:

```
origin
```

مثلاً:

```
origin → GitHub repository
```

---

# 27. `push`

عندك:

```
Local:

A ─── B ─── C
```

وGitHub عندو:

```
Remote:

A ─── B
```

درت:

```
git push
```

كيولي:

```
Local:   A ─── B ─── C
                       │
Remote:  A ─── B ──────┘
```

يعني بعثتي الـcommit الجديد للـremote.

---

# 28. `pull`

العكس تقريباً.

شخص آخر دار commit فـGitHub:

```
Remote:

A ─── B ─── C
```

وأنت عندك:

```
Local:

A ─── B
```

درت:

```
git pull
```

Git كيجيب التغييرات من remote وكيحدّث الـlocal repository.

---

# 29. ولكن `fetch`؟

هنا كنزيدو شوية احترافية.

عندك:

```
git fetch
```

و:

```
git pull
```

ماشي نفس الحاجة.

بشكل مبسط:

```
git fetch
```

يعني:

> "جيب ليا معلومات وتغييرات remote، ولكن ما تدمجهمش مباشرة فالشغل ديالي."

بينما:

```
git pull
```

غالباً:

```
fetch + integrate
```

يعني جيب التغييرات ودمجها/طبّقها حسب الحالة.

هاد الفرق مهم بزاف فالشغل الحقيقي.

---

# 30. `.gitignore`

كاينين ملفات **ما خاصناش ندخلوهم للـGit**.

مثلاً فـNode.js:

```
node_modules/
```

ما بغيناش نديرو:

```
git add node_modules/
```

لأنها ضخمة وممكن تتولد من جديد.

كنستعملو:

```
.gitignore
```

مثلاً:

```
node_modules/
.env
*.log
```

يعني:

```
node_modules/ → تجاهل
.env           → تجاهل
*.log          → تجاهل
```

وهذا مهم جداً خصوصاً:

```
.env
```

حيت ممكن يحتوي:

```
API_KEY=...
DATABASE_PASSWORD=...
```

**الأسرار ما خاصهاش تدخل للـrepository.**

---

# دابا الصورة الكبيرة ديال Git

حاول تشوفها هكذا:

```
                     Git
                      │
          ┌───────────┴───────────┐
          │                       │
       Local                    Remote
          │                       │
    ┌─────┴─────┐                 │
    │           │                 │
 Working     Staging          GitHub
 Directory    Area               │
    │           │                 │
    │ add       │ commit          │
    └─────►────┴──────────────► push
                                  │
                                  │
                               pull/fetch
```

وفوق هادشي:

```
Commits
   │
   ▼
Branches
   │
   ▼
Merge
   │
   ▼
History
```

---

## ودابا غادي نوقف الشرح النظري هنا شوية

حيت إلا بقينا غير نشرحو، غادي تولي عندك معلومات كثيرة بلا ممارسة.

**المرحلة الجاية: Lab 1 🧪**

غادي نبنيو repository حقيقي من الصفر، ونخليك أنت اللي تدير:

```
git init
git status
git add
git commit
git diff
git log
```

ولكن **ما غاديش نعطيك جميع الأوامر دفعة وحدة**.

غادي نعطيك مهمة صغيرة، أنت تنفذها، وترجع ليا النتيجة، ومن بعد نعطيك المهمة اللي بعدها. هكذا غادي نبنيو Git logic ديالك فعلاً.

كيفاش كنقدر نرجع باللوراء لكوميت شنو هوما الاوامر reset reverte و restore

آه، هادي بالضبط من أهم الحوايج فـGit. والفرق بين **`restore` و`reset` و`revert`** خاصك تفهمو مزيان، حيث كل واحد كيرجعك بطريقة مختلفة.

خلينا ناخدو مثال واحد:

```
A ─── B ─── C
```

ودابا أنت واقف فـ`C`.

---

# 1. `git restore` — رجّع الملفات

`restore` كيتعامل أساساً مع **files**، ماشي مع تاريخ الـcommits.

مثلاً:

```
آخر commit:
Hello

أنت بدلت الملف:
Hello Ahmed
```

وبغيتي تلغي التغيير اللي مازال **ما دارتش ليه commit**:

```
git restore hello.txt
```

يرجع:

```
Hello Ahmed
      ↓
Hello
```

يعني:

> "حيد التغييرات اللي درتها فالملف ورجعو للحالة اللي عند Git."

⚠️ التغيير اللي حيدتي بـ`restore` ممكن يضيع، لذلك استعملو وأنت عارف شنو كتدير.

### مثال:

```
Working Directory
     │
     └── hello.txt = "Hello Ahmed"

          git restore

     ↓

hello.txt = "Hello"
```

---

# 2. `git reset` — حرّك HEAD/branch للوراء

هاد واحد أقوى وأخطر.

عندنا:

```
A ─── B ─── C
          ▲
         main
          ▲
         HEAD
```

درت:

```
git reset --hard B
```

النتيجة:

```
A ─── B
      ▲
     main
      ▲
     HEAD
```

يعني branch رجعات لـ`B`.

الـcommit `C` ما بقاش فالتاريخ الحالي ديال branch.

---

## ولكن `reset` عندو 3 modes مهمين

### `--soft`

```
git reset --soft B
```

كيحرك HEAD/branch فقط.

التغييرات ديال `C` كيبقاو **staged**.

```
HEAD → B

Changes from C
      ↓
Staging Area
```

مفيد مثلاً إلا بغيتي تعاود تصاوب commit بطريقة مختلفة.

---

### `--mixed` — default

```
git reset B
```

أو:

```
git reset --mixed B
```

كيحرك HEAD، وكيخرج التغييرات من Staging Area.

```
HEAD → B

Changes
   ↓
Working Directory
```

يعني الملفات باقيين بالتغييرات، ولكن ما بقاوش staged.

---

### `--hard`

```
git reset --hard B
```

هاد أخطر واحد.

كيحرك HEAD **وكيبدل الملفات حتى هي** للحالة ديال `B`.

يعني:

```
C changes
   ↓
❌ staged
❌ working changes
```

لذلك:

> `reset --hard` = استعملو بحذر.

---

# 3. `git revert` — عكس Commit

هنا الفرق المهم جداً.

عندنا:

```
A ─── B ─── C
```

وبغيتي تلغي تأثير `C`.

ما كنرجعوش branch لـB.

كنقولو:

```
git revert C
```

Git كينشئ **commit جديد** كيعاكس التغييرات ديال `C`.

النتيجة:

```
A ─── B ─── C ─── D
```

فين:

```
D = عكس C
```

مثلاً:

```
C:
+ login page
```

`revert` يقدر يصاوب:

```
D:
- login page
```

ولكن `C` باقي موجود فالتاريخ.

---

# الفرق الأساسي 🔥

خلي هاد الصورة فدماغك:

```
             عندك تغييرات؟
                  │
          ┌───────┴───────┐
          │               │
      مازال ما          عندك Commit
       commit             │
          │               │
      restore        واش بغيتي نبدلو
                         التاريخ؟
                           │
                    ┌──────┴──────┐
                    │             │
                   نعم            لا
                    │             │
                  reset         revert
```

---

## مثال حقيقي

عندك:

```
A = Create website
B = Add navbar
C = Add broken login
```

### الحالة 1: غير عدلتي الملف ومازال ما عملتيش commit

استعمل:

```
git restore file
```

---

### الحالة 2: درتي commit ولكن أنت بوحدك وبغيتي تمحي commits من التاريخ

مثلاً:

```
A ─── B ─── C
```

وتبغي ترجع لـB:

```
git reset --hard B
```

النتيجة:

```
A ─── B
```

---

### الحالة 3: الـcommit سبق وشاركتيه مع الفريق/GitHub

مثلاً:

```
A ─── B ─── C
```

و`C` فيه bug.

الأفضل عادةً ما تمحيش التاريخ المنشور بـ`reset`.

استعمل:

```
git revert C
```

فتولي:

```
A ─── B ─── C ─── D
```

والـ`D` كيلغي تأثير `C`.

---

# جدول صغير تحفظو

|الأمر|كيخدم على|كيحذف التاريخ؟|الاستعمال|
|---|---|---|---|
|`restore`|الملفات|لا|إلغاء تغييرات الملف|
|`reset`|HEAD / branch / staging / files|ممكن|الرجوع لحالة commit|
|`revert`|commit|لا|عكس commit بــcommit جديد|

### قاعدة ذهبية 🧠

**`restore` = رجّع الملف**

**`reset` = حرّك التاريخ ديالك**

**`revert` = عاكس commit بدون محو التاريخ**

وأهم حاجة: **ما تستعملش `reset --hard` بشكل عشوائي**، خصوصاً إلا كان عندك تغييرات مهمة أو كنت خدام مع فريق.

عطيني خلاصة قوية

أكيد. هادي **الخلاصة اللي خاصها تبقى فدماغك**، بلا تعقيد.

# 🧠 Git — الخلاصة القوية

## 1. Git عندو 3 مناطق

```
WORKING DIRECTORY
       │
       │ git add
       ▼
STAGING AREA
       │
       │ git commit
       ▼
REPOSITORY
```

### المعنى:

- **Working Directory** → الملفات اللي كتخدم عليهم دابا.
- **Staging Area** → التغييرات اللي اخترتي باش تدخل للـcommit.
- **Repository** → التاريخ ديال المشروع والـcommits.

---

# 2. أهم الأوامر

```
git init
```

➡️ بدا Git فالمشروع.

```
git status
```

➡️ شوف الحالة الحالية.

```
git add file.txt
```

➡️ حط التغيير فالـStaging.

```
git commit -m "message"
```

➡️ سجل التغييرات فالتاريخ.

```
git log
```

➡️ شوف تاريخ الـcommits.

```
git diff
```

➡️ شوف شنو تبدل ومازال ما دخلش للـstaging.

---

# 3. الفرق بين `restore`, `reset`, `revert` 🔥

هاد الثلاثة **ماشي نفس الحاجة**.

## 🟢 `restore`

**المعنى: رجّع الملف.**

مثلاً:

```
آخر commit:
Hello

دابا:
Hello Ahmed
```

بغيتي تلغي التعديل:

```
git restore hello.txt
```

فتولي:

```
Hello
```

احفظ:

> **restore = file**

---

# 🟠 `reset`

**المعنى: حرّك HEAD/branch للخلف.**

عندك:

```
A ─── B ─── C
```

درت:

```
git reset B
```

كتولي:

```
A ─── B
```

وكاينين modes:

```
git reset --soft B
```

➡️ يرجع HEAD، والتغييرات تبقى **staged**.

```
git reset --mixed B
```

➡️ يرجع HEAD، والتغييرات تبقى فالـ**Working Directory**.

```
git reset --hard B
```

➡️ يرجع HEAD **والملفات** للحالة ديال B.

⚠️ `--hard` خطير إلا كانت عندك تغييرات ما بغيتش تضيعها.

احفظ:

> **reset = move HEAD / rewrite local history**

---

# 🔴 `revert`

**المعنى: عاكس commit بــcommit جديد.**

عندك:

```
A ─── B ─── C
```

بغيتي تلغي تأثير `C`:

```
git revert C
```

كيولي:

```
A ─── B ─── C ─── D
```

فين:

```
D = عكس C
```

يعني **C ما تمحاش**.

احفظ:

> **revert = reverse a commit safely by creating another commit**

---

# ⚡ الفرق فـ3 كلمات

```
restore → FILE
reset   → HEAD
revert  → COMMIT
```

أو بطريقة أخرى:

```
restore = رجّع الملف

reset   = رجّع المؤشر/التاريخ

revert  = عاكس commit
```

---

# 4. قاعدة عملية مهمة

إلى سولت راسك:

### "بدلت ملف وما بغيتش التغيير؟"

```
git restore file
```

### "درت commits محلياً وبغيت نرجع لور؟"

```
git reset ...
```

### "عندي commit مسجل ومشارك مع الفريق وبغيت نلغي تأثيرو؟"

```
git revert ...
```

---

# 5. Git History

```
A ─── B ─── C ─── D
```

كل وحدة:

```
A = commit
B = commit
C = commit
D = commit
```

و:

```
HEAD
```

كيحدد فين Git واقف دابا.

مثلاً:

```
A ─── B ─── C
            ▲
           HEAD
```

---

# 6. Branches

Branch ماشي folder جديد.

هي **pointer كيشير لـcommit**.

```
A ─── B ─── C
            ▲
           main
```

درت branch:

```
A ─── B ─── C
            ├── main
            │
            └── feature
```

ومن بعد feature دارت commit:

```
             ┌── D ─── E
            /
A ─── B ─── C
            ▲
           main
```

---

# 7. Merge

بغيتي تدخل feature لـmain:

```
main       ─── C
              \
feature        D ─── E
```

نديرو:

```
git merge feature
```

باش نجمعو التغييرات.

---

# 8. Git vs GitHub

**Git:**

```
برنامج Version Control
```

**GitHub:**

```
Online platform
```

العلاقة:

```
PC
 │
 │ Git
 ▼
Local Repository
 │
 │ push
 ▼
GitHub
 │
 │ pull/fetch
 ▼
Local Repository
```

---

# 9. أهم أوامر Git اللي خاصك تبني عليهم

```
git init
git status

git add
git commit

git log
git diff

git restore
git reset
git revert

git branch
git switch
git merge

git remote
git fetch
git pull
git push

git clone
```

ما تحفظهمش كاملين دابا.

خاصك تفهم **شنو المشكلة اللي كل command كيحلها**.

---

# 🎯 الصورة النهائية

إلى فهمتي هاد الرسم، راك فهمتي أساس Git:

```
                    PROJECT
                       │
                       ▼
              Working Directory
                       │
                    git add
                       │
                       ▼
                Staging Area
                       │
                   git commit
                       │
                       ▼
                  Repository
                       │
                       ▼
                 Commit History
                       │
              ┌────────┴────────┐
              ▼                 ▼
           Branches            HEAD
              │
            merge
              │
              ▼
             main
              │
             push
              ▼
            GitHub
              │
         fetch / pull
              │
              ▼
             Local
```

**وأهم 3 كلمات دابا:**

> 🟢 `restore` → **FILE**  
> 🟠 `reset` → **HEAD / HISTORY**  
> 🔴 `revert` → **COMMIT**

من بعد هاد الخلاصة، أحسن خطوة هي **تمارين عملية حقيقية** على `restore → reset → revert`، لأن الفرق بينهم ما كيثبتش غير بالشرح؛ خاصك تشوف بنفسك شنو كيوقع فالـhistory والـfiles.
9bal mankamlo bghit sumury pro fi revert o restore o reset o7ta use cases dialhom

أكيد 👍 قبل ما ندوزو للـ Branches، نخليو هاد 3 أوامر راسخين عندك بحال **Professional Cheat Sheet**.

# 🧠 Git Pro Summary — `restore` / `reset` / `revert`

الفكرة الأساسية هي أن كل واحد فيهم كيتعامل مع **حاجة مختلفة**:

```
                 Git
                  │
       ┌──────────┼──────────┐
       │          │          │
    restore      reset     revert
       │          │          │
      FILE      HEAD       COMMIT
       │          │          │
   الملفات      التاريخ     التاريخ
                 │          │
              محلياً      بطريقة آمنة
```

---

# 1️⃣ `git restore`

## 🎯 الدور ديالو

`restore` كيتعامل أساساً مع **الملفات**.

يعني كتقول لـ Git:

> "رجّع ليا هاد الملف لحالة معينة."

### الحالة 1: عندك modification ومازال ما درتيش `add`

```
git restore app.c
```

مثلاً:

```
آخر Commit:
app.c = A

دابا:
app.c = A + تغييرات

git restore app.c

النتيجة:
app.c = A
```

⚠️ التغييرات اللي ما كانتش committed كتضيع.

---

## الحالة 2: Unstage

إلا درتي:

```
git add app.c
```

ومن بعد بغيتي تحيدو من Staging:

```
git restore --staged app.c
```

النتيجة:

```
قبل:

Working Directory → modified
        ↓
Staging Area       → staged


بعد:

Working Directory → modified
Staging Area       → clean
```

المهم:

> `--staged` ما كيمسحش التعديل من الملف.

---

## الحالة 3: رجّع ملف من Commit معين

مثلاً:

```
A → B → C
        ↑
       HEAD
```

بغيتي غير `app.c` يرجع للحالة ديال B:

```
git restore --source=B app.c
```

أو:

```
git restore --source=HEAD~1 app.c
```

وهنا:

```
HEAD باقي فـ C
```

يعني **ما حركناش التاريخ**.

---

# 🧠 الخلاصة ديال `restore`

```
restore = FILE
```

استعملو ملي كتقول:

> "بغيت نصلح/نرجع ملف."

### أهم Use Cases

|الحالة|الأمر|
|---|---|
|حذف modification من ملف|`git restore file`|
|Unstage ملف|`git restore --staged file`|
|استرجاع ملف من Commit|`git restore --source=COMMIT file`|

---

# 2️⃣ `git reset`

هنا دخلنا لمنطقة مختلفة.

`reset` كيتعامل مع **HEAD والتاريخ المحلي**.

```
reset
  │
  └── تحريك HEAD / branch
```

مثلاً:

```
A → B → C
        ↑
       HEAD
```

درتي:

```
git reset ...
```

يمكن `HEAD` يرجع:

```
A → B
    ↑
   HEAD
```

---

# 🟢 `git reset --soft`

مثلاً:

```
A → B → C
        ↑
       HEAD
```

درتي:

```
git reset --soft HEAD~1
```

النتيجة:

```
A → B
    ↑
   HEAD

تغييرات C
   ↓
STAGING AREA
```

يعني:

> رجعت Commit، ولكن خليت التغييرات **staged**.

### Use Case

مثلاً درتي:

```
git commit -m "bad commit message"
```

ومن بعد اكتاشفتي:

> بغيت نبدل commit message أو نزيد شي تغييرات.

تقدر ترجع commit واحد بـ:

```
git reset --soft HEAD~1
```

ومن بعد تعاود commit.

---

# 🟡 `git reset --mixed`

وهو الـ default ديال `reset`.

```
git reset --mixed HEAD~1
```

النتيجة:

```
A → B
    ↑
   HEAD

تغييرات C
   ↓
Working Directory
```

ولكن:

```
Staging Area = فارغة
```

يعني:

> رجع Commit، وخلي التغييرات فالملفات ولكن **unstaged**.

### Use Case

مثلاً:

```
Commit C فيه بزاف ديال التغييرات
```

وبغيتي تحيد C من التاريخ وتعاود تختار شنو بالضبط غادي تدير ليه `git add`.

تستعمل:

```
git reset --mixed HEAD~1
```

ومن بعد تقدر تختار:

```
git add file1
git add file2
```

---

# 🔴 `git reset --hard`

هاد واحد خاصك تكون حذر معاه.

```
git reset --hard HEAD~1
```

النتيجة:

```
قبل:

A → B → C
        ↑
       HEAD


بعد:

A → B
    ↑
   HEAD
```

والتغييرات ديال C كتتحيد من Working Directory كذلك.

يعني:

```
Commit C ❌
Changes ديال C ❌
Staging ديال C ❌
```

### Use Case

مثلاً خدمتي locally:

```
A → B → C
```

وكتقول:

> "C كارثة وما بغيت حتى أثر ديالو، ومازال ما درتش push."

هنا ممكن:

```
git reset --hard HEAD~1
```

⚠️ ولكن خاصك تعرف أن التغييرات غير المحفوظة ممكن تضيع.

---

# 🚨 قاعدة مهمة جداً مع `reset`

قبل ما تستعمل:

```
git reset
```

سول راسك:

> **واش هاد التاريخ راه pushed/shared مع الآخرين؟**

إلا كان:

```
Local only
```

`reset` ممكن يكون مناسب حسب الحالة.

ولكن إلا كان:

```
GitHub / Shared repository
```

خاصك تكون حذر بزاف، خصوصاً مع إعادة كتابة التاريخ.

---

# 3️⃣ `git revert`

هنا كيتبدل التفكير كامل.

`revert` ما كيمسحش Commit قديم.

كيصاوب **Commit جديد** كيعكس التغييرات ديالو.

مثلاً:

```
A → B → C
        ↑
       HEAD
```

درتي:

```
git revert HEAD
```

النتيجة:

```
A → B → C → R
            ↑
           HEAD
```

فين:

```
R = Revert Commit
```

وR كيعكس تأثير C.

---

# 🎯 علاش `revert` مهم؟

حيت C بقى فالتاريخ:

```
A → B → C → R
```

ما مسحناهش.

وهذا مهم خصوصاً ملي C راه:

```
pushed → GitHub
```

أو:

```
shared → team
```

---

# 🧠 مثال احترافي

عندك:

```
A → B → C
```

C فيه bug.

C راه pushed:

```
Local + GitHub + Team
```

ماشي فكرة أنك تبدل التاريخ المشترك بلا سبب.

بدل ذلك:

```
git revert C
```

كتولي:

```
A → B → C → R
```

وR كيلغي تأثير C.

---

# 🔥 الفرق الكبير

حفظ هاد الجدول:

|Command|كيتعامل مع|كيبدل التاريخ؟|كيخلق Commit؟|
|---|---|---|---|
|`restore`|Files|❌|❌|
|`reset --soft`|HEAD/History|✅|❌|
|`reset --mixed`|HEAD/History|✅|❌|
|`reset --hard`|HEAD + Files|✅|❌|
|`revert`|Commit|❌|✅|

---

# 🧩 الثلاثة فصورة وحدة

```
              ┌─────────────────────┐
              │       Git State     │
              └──────────┬──────────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
    RESTORE           RESET           REVERT
        │                │                │
        ▼                ▼                ▼
      FILE            HEAD          COMMIT
        │                │                │
        │          ┌─────┼─────┐          │
        │          │     │     │          │
        │        soft  mixed  hard        │
        │          │     │     │          │
        │        staged │     │           │
        │              unstaged │         │
        │                    delete       │
        │                                 │
        └─────────────────────────────────┘
                                          │
                                      NEW COMMIT
```

---

# 🧠 الطريقة الاحترافية باش تختار

قبل أي command، سول راسك 3 أسئلة:

### السؤال 1:

**واش المشكل غير فـ File؟**

```
YES → restore
```

---

### السؤال 2:

**بغيت نرجع HEAD/التاريخ المحلي؟**

```
YES → reset
```

ومن بعد اختار:

```
soft  → نخلي التغييرات staged

mixed → نخلي التغييرات unstaged

hard  → نحيد التغييرات
```

---

### السؤال 3:

**بغيت نلغي Commit موجود، خصوصاً راه pushed/shared؟**

```
YES → revert
```

---

# ⭐ احفظها بهاد الجملة

```
RESTORE → FILE
RESET   → HEAD
REVERT  → COMMIT
```

وزيد عليها:

```
SOFT  → STAGED
MIXED → UNSTAGED
HARD  → DELETE CHANGES
REVERT → NEW COMMIT
```

هاد القاعدة بوحدها غادي تعاونك بزاف ملي تبدا تشوف Git commands فـ projects حقيقية.
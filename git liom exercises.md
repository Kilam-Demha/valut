## 🧪 Git Pro Lab — تمارين الدار

رتبتهم تصاعدياً، وكل تمرين فيه واحد الـtrap باش ما يكونش غير حفظ.

---

### 🟢 Mission 4 — Selective Commit

**الهدف:** تتأكد أن commit كيأخذ غير Staging Area.

1. بدّل `index.html`.
2. بدّل `app.js`.
3. صايب ملف جديد.
4. دير staging غير لبعض التغييرات.
5. خلّي `app.js` modified ولكن unstaged.
6. خلّي الملف الجديد untracked.
7. دير commit.
8. تأكد شنو دخل للـcommit وشنو بقى.

---

### 🟢 Mission 5 — Understand `diff`

1. دير تغيير فـ `index.html`.
2. قبل staging، شوف الفرق بين آخر commit والـWorking Directory.
3. دير staging للتغيير.
4. شوف الفرق بين الـStaging Area وآخر commit.
5. زيد تغيير آخر لنفس الملف **بعد staging**.
6. شوف الفرق مرة أخرى.
7. حاول تفسر علاش نفس الملف قدر يكون عندو تغيير staged وتغيير آخر unstaged.

🎯 خاصك توصل لهاد الصورة:

```
HEAD
 │
 │
 ▼
Staging Area
 │
 │
 ▼
Working Directory
```

---

### 🟡 Mission 6 — Two Commits, Two Purposes

1. صايب تغييرات كتخص **HTML**.
2. صايب تغييرات كتخص **JavaScript**.
3. دير commit للـHTML فقط.
4. تأكد أن JavaScript ما دخلش.
5. من بعد دير commit للـJavaScript.
6. شوف history.
7. خاص يكون عندك جوج commits وكل واحد عندو purpose واضح.

🎯 تعلم تفكر:

> Commit = وحدة منطقية من التغيير.

---

### 🟡 Mission 7 — Branching

1. انطلاقاً من آخر commit، صايب branch جديد.
2. تأكد أنك واقف فيه.
3. دير جوج commits فهاد branch.
4. ما تبدل والو فـ`main`.
5. رجع لـ`main`.
6. تأكد أن commits ديال branch ما بانوش كجزء من `main`.
7. ارسم graph ديال history فدفترك.

---

### 🟡 Mission 8 — Fast-Forward Merge

عندك:

```
A → B → C
         ↑
       feature
```

و`main` باقي فـB.

1. دمج `feature` داخل `main`.
2. خاص الدمج يكون **Fast-Forward**.
3. تأكد واش Git خلق merge commit ولا لا.
4. شوف graph ديال history.
5. فسر علاش Git قدر يدير Fast-Forward.

---

### 🟠 Mission 9 — Divergence

دابا من جديد:

```
        C → D   feature
       /
A → B
       \
        E → F   main
```

المطلوب:

1. صايب branch.
2. دير commit فيه.
3. رجع لـ`main`.
4. دير commit مختلف.
5. دابا عندك جوج خطوط مختلفين.
6. حاول تدمج branch.
7. شوف نوع الـmerge اللي وقع.
8. تأكد واش كاين merge commit.
9. شوف parents ديال merge commit.

🎯 خاصك تفهم علاش هادي **ماشي Fast-Forward**.

---

### 🔴 Mission 10 — Real Merge Conflict

هاد المرة بغيتك تصنع conflict عمداً.

1. صايب ملف `config.txt`.
2. commit أول.
3. صايب branch.
4. فـbranch بدّل نفس السطر.
5. رجع لـ`main`.
6. بدّل **نفس السطر** بطريقة مختلفة.
7. commit.
8. حاول merge.
9. Git خاصو يوقف بسبب conflict.
10. قرا conflict markers.
11. قرر نتا شنو المحتوى النهائي.
12. حل conflict.
13. تأكد أن الملف ما بقاش فيه markers.
14. كمّل merge.
15. شوف history.

🎯 **ممنوع تحفظ الحل. خاصك تفهم:**

```
<<<<<<<
=======
>>>>>>>
```

---

### 🔴 Mission 11 — Conflict أكثر واقعية

نفس الفكرة ولكن:

- الملف فيه 15–20 سطر.
- كل branch يبدل أسطر مختلفة.
- خليه حتى يكون عندك conflict واحد على الأقل.
- وحاول تعرف شنو Git قدر يدمجو بوحدو وشنو ما قدرش.

🎯 الهدف:

**Git ماشي كيقول "جوج branches تبدلو" = conflict.**

الـconflict كيتعلق بالتغييرات المتعارضة فـنفس المنطقة تقريباً.

---

### 🟠 Mission 12 — `restore`

صايب تغيير فملف tracked.

1. ما تديرش staging.
2. شوف الفرق.
3. قرر أنك ما بغيتيش هاد التغيير.
4. رجّع الملف للحالة السابقة.
5. تأكد أن التغيير اختفى.
6. تأكد أن الـcommit history ما تبدلش.

🎯 خاصك تفهم:

```
restore
   ↓
Working Directory
```

---

### 🔴 Mission 13 — Restore Staged

1. بدّل ملف.
2. دخلو للـstaging.
3. تأكد أنه staged.
4. قرر أنك ما بغيتيش **تحيدو من staging** ولكن ما بغيتيش تحيد التغيير من الملف.
5. رجّع الملف من Staging إلى Working Directory.
6. تأكد أن المحتوى باقي موجود.
7. ولكن الملف ما بقاش staged.

🎯 فرق بين:

```
إلغاء التغيير
      ≠
إلغاء staging
```

---

### 🔴 Mission 14 — Revert

1. دير commit فيه تغيير واضح.
2. من بعد دير commit آخر.
3. قرر أن التغيير ديال الـcommit الأول خاصو يتلغا.
4. ممنوع تمسح history.
5. استعمل الطريقة اللي كتخلق **commit جديد** كيعكس التغيير.
6. شوف history.

🎯 خاصك توصل:

```
A → B → C → D
```

وماشي:

```
A → B
```

---

### 🔴 Mission 15 — Reset

دير history فيه:

```
A → B → C → D
```

1. خلي `D` هو current commit.
2. رجع branch pointer لـ`C`.
3. شوف history.
4. حاول تفهم فين مشى `D`.
5. ما تستعملش هاد التمرين فـrepo مهم؛ غير `git-pro-lab`.

🎯 الفرق اللي خاصك يكون واضح:

```
reset  → كيحرك branch pointer
revert → كيخلق commit جديد
```

---

### 🔴 Mission 16 — Detached HEAD

1. عندك على الأقل 3 commits.
2. انتقل مباشرة لواحد commit قديم **بدون الانتقال لbranch**.
3. تأكد أن HEAD detached.
4. دير commit جديد.
5. شوف فين ولى commit الجديد.
6. رجع لـ`main`.
7. لاحظ أن commit الجديد ما بقاش تابع لـ`main`.
8. حاول تفهم كيفاش تحافظ عليه قبل ما يضيع من references.

🎯 خاصك ترسم:

```
Normal:

HEAD → main → C


Detached:

HEAD → B
       ↑
     commit
```

---

### 🟣 Mission 17 — Reflog

1. دير commit.
2. دير reset وخلي commit القديم ما يبقاش ظاهر فـnormal history.
3. استعمل history ديال references باش تلقى commit اللي تحرك.
4. تأكد من hash ديالو.
5. رجّع repository لحالة سليمة.

🎯 هنا غادي تفهم علاش `reflog` مهم بزاف.

---

### 🟣 Mission 18 — Tags

1. عندك commit كيمثل version مستقرة.
2. علّم عليه بـtag.
3. شوف tags.
4. شوف commit اللي كيشير ليه tag.
5. دير commit جديد.
6. تأكد أن tag باقي كيشير للـcommit القديم.

🎯 الفرق:

```
branch → pointer كيتحرك
tag    → pointer غالباً ثابت
```

---

# 🌐 Remote Git

من هنا غادي نبدأو simulation ديال GitHub.

### 🟠 Mission 19 — Remote

1. أنشئ repository remote جديد فارغ وآمن للتجربة.
2. اربط local repository بالـremote.
3. تأكد أن remote مسجل.
4. تأكد من URL ديالو.
5. ما تديرش push باقي.

---

### 🟠 Mission 20 — First Push

1. عندك local `main`.
2. دفع history للـremote.
3. تأكد أن remote وlocal عندهم نفس الـcommit.
4. تأكد من العلاقة بين local branch وremote-tracking branch.

---

### 🟠 Mission 21 — Clone

1. خرج من `git-pro-lab`.
2. صايب clone جديد من remote.
3. دخل للنسخة الجديدة.
4. تأكد أن history موجود.
5. تأكد أن remote موجود.
6. قارنها مع repository الأصلي.

🎯 خاصك تفهم:

> clone ≠ download فقط.

---

### 🔴 Mission 22 — Fetch

خلي repository A وrepository B.

1. فـA دير commit وpush.
2. فـB **ممنوع تدير pull**.
3. جيب معلومات remote فقط.
4. شوف local `main`.
5. شوف remote-tracking branch.
6. تأكد أن `main` ما تحركش.
7. فسر الفرق بين:

```
main
origin/main
```

---

### 🔴 Mission 23 — Pull

نفس السيناريو.

1. Remote فيه commit جديد.
2. Local مازال قديم.
3. استعمل الطريقة اللي كتجيب remote changes وكتدمجها.
4. شوف شنو وقع للـlocal branch.
5. حدد واش وقع Fast-Forward ولا merge.

---

### 🔴 Mission 24 — Push Rejected

هاد واحد مهم بزاف.

خلي:

```
Remote:
A → B → D

Local:
A → B → C
```

1. حاول تدفع local.
2. Git خاصو يرفض العملية.
3. ما تستعملش force.
4. فهم علاش ترفض.
5. جيب remote changes.
6. حل divergence بالطريقة اللي تختارها.
7. من بعد دفع history الصحيح.

🎯 ممنوع تقول:

> "حيت التاريخ مختلف."

خاصك تشرح **علاش Git ما يقدرش يحرك remote pointer من D إلى C بطريقة Fast-Forward**.

---

### 🔴 Mission 25 — Pull + Rebase

عاود نفس السيناريو:

```
Remote:
A → B → D

Local:
A → B → C
```

ولكن هاد المرة بغينا history خطي.

1. جيب remote changes.
2. أعد تطبيق local commit فوق remote.
3. لاحظ أن commit المحلي الأصلي تبدل.
4. تأكد من الـhash.
5. دفع النتيجة.

🎯 خاصك تشوف:

```
قبل:

A → B → C
     \
      D

بعد:

A → B → D → C'
```

---

# 🧨 Advanced Git

### 🔥 Mission 26 — Rebase Conflict

1. صايب divergence.
2. branchين يبدلو نفس الجزء.
3. حاول rebase.
4. خلي Git يوقف بسبب conflict.
5. حل conflict.
6. كمل rebase.
7. شوف history النهائي.

🎯 هنا غادي تجمع:

**rebase + conflict + resolution + rewritten commits**

---

### 🔥 Mission 27 — Rebase vs Merge

نفس المشروع ديرو جوج مرات.

**Scenario A:** merge

**Scenario B:** rebase

قارن:

```
History
Number of commits
Graph
Parent relationships
Commit hashes
Linear/non-linear history
```

ممنوع تختار "الأفضل"؛ غير فسّر الفرق التقني.

---

### 🔥 Mission 28 — Stash

1. عندك modification خدام عليه.
2. مازال ما واجدش للـcommit.
3. جاك طلب آخر خاصك تبدل branch ليه.
4. حافظ على work ديالك بلا commit.
5. بدّل branch.
6. خدم الحاجة الأخرى.
7. رجع.
8. استرجع work القديم.

🎯 خاصك تفهم:

```
Working Directory
       ↓
    temporary shelf
       ↓
Working Directory
```

---

### 🔥 Mission 29 — Stash Conflict

نفس Mission 28 ولكن:

1. stash تغيير.
2. بدّل نفس الجزء فـbranch آخر.
3. رجع stash.
4. خلي conflict يوقع.
5. حل conflict.

---

### 🔥 Mission 30 — Git Forensics 🕵️

هاد هو الامتحان.

نعطيك history:

```
A ── B ── C ── D
     \
      E ── F
```

وكنقول ليك:

- `main` كيشير لـD
- `feature` كيشير لـF
- `HEAD` على feature
- `origin/main` كيشير لـC

المطلوب منك **بلا ما تشوف history الحقيقي**:

1. ترسم state كامل.
2. تحدد branches.
3. تحدد HEAD.
4. تحدد remote-tracking branch.
5. تحدد parent ديال كل commit.
6. تقول شنو يوقع إذا درتي merge `feature` داخل `main`.
7. تقول واش Fast-Forward ولا Merge Commit.
8. تقول شنو يوقع إذا درتي rebase للـfeature فوق main.
9. تحدد شنو commits غادي يتعاودو.
10. تحدد شنو hashes ممكن يتبدلو.

---

# 🏆 Final Challenge — Git Pro Simulation

دير project جديد كأنه project حقيقي:

```
main
│
├── feature/login
├── feature/dashboard
└── bugfix/navbar
```

وخدم السيناريو كامل:

1. initial commit
2. feature branch
3. عدة commits
4. main changes
5. divergence
6. merge
7. conflict
8. conflict resolution
9. remote
10. clone
11. fetch
12. pull
13. push
14. rejected push
15. rebase
16. rebase conflict
17. stash
18. restore
19. revert
20. reset
21. detached HEAD
22. reflog
23. tag
24. final clean history

وفي الأخير خاصك تكون قادر ترسم هادشي **من راسك**:

```
                 origin/main
                      │
                      ▼
A ── B ── C ───────── D
      \              / 
       E ── F ──────
             │
          feature
             │
            HEAD
```

### 📌 الترتيب اللي أنصحك تخدم به اليوم

ما تحاولش تديرهم كاملين دفعة وحدة:

**4 → 5 → 6 → 7 → 8 → 9 → 10 → 11**

ومن بعد:

**12 → 13 → 14 → 15 → 16 → 17 → 18**

ومن بعد Remote:

**19 → 20 → 21 → 22 → 23 → 24 → 25**

وأخيراً:

**26 → 27 → 28 → 29 → 30 → Final Challenge**

و**Mission 4 هي اللي وصلنا ليها دابا**. ما تحتاجش تعاود Mission 1–3.
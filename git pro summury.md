
## 🧠 الخلاصة الكبرى ديال Pro Git

فكر فـ Git بهاد الصورة:

```
Working Directory
      ↓ git add
Staging Area
      ↓ git commit
Repository
      ↓ git push
Remote Repository (GitHub)
```

### 1. Git شنو هو؟

Git هو **Version Control System**.

يعني كيخليك تحتافظ بتاريخ المشروع ديالك:

```
v1 → v2 → v3 → v4
```

وتقدر:

- تعرف شنو تبدل
- شكون بدل
- ترجع لنسخة قديمة
- تدير branches
- تدمج التغييرات
- تخدم مع الآخرين

---

# 2. أهم 4 حالات خاصك تفهمهم

### Working Directory

هنا الملفات اللي خدام عليهم دابا.

```
git status
```

كيوريك شنو تبدل.

### Staging Area

كتقول لـ Git:

> هاد التغييرات بالضبط بغيت ندخلهم للكوميت.

```
git add file.c
```

أو:

```
git add .
```

### Repository

هنا كيتسجل التاريخ ديالك.

```
git commit -m "Add login validation"
```

### Remote

نسخة المشروع الموجودة مثلاً فـ GitHub.

```
git push
```

---

# 3. البداية ديال أي مشروع

```
git init
```

من بعد:

```
git status
```

ثم:

```
git add .
```

ثم:

```
git commit -m "Initial commit"
```

إذا عندك GitHub repository:

```
git remote add origin URL
git push -u origin main
```

---

# 4. Commit

الـ commit هو **نقطة محفوظة فالتاريخ**.

مثلاً:

```
A ---- B ---- C ---- D
```

كل حرف = commit.

Commit مزيان خاصو يكون عندو message واضح:

```
git commit -m "Add user authentication"
```

ماشي:

```
git commit -m "update"
```

---

# 5. Git History

باش تشوف التاريخ:

```
git log
```

أو بشكل مختصر:

```
git log --oneline
```

مثلاً:

```
a82f91c Add authentication
31de7ab Fix validation
9c821aa Initial commit
```

هاد:

```
a82f91c
```

هو جزء من **commit hash**.

---

# 6. Branches 🌿

Branch هو خط مستقل للتطوير.

مثلاً:

```
main
 |
 A ---- B ---- C
              \
               D ---- E
                feature-login
```

إنشاء branch:

```
git branch feature-login
```

الانتقال ليه:

```
git switch feature-login
```

أو مباشرة:

```
git switch -c feature-login
```

تشوف branches:

```
git branch
```

---

# 7. Merge

منين تسالي feature:

```
git switch main
```

ثم:

```
git merge feature-login
```

يعني كتدمج التغييرات ديال branch داخل `main`.

---

# 8. Merge Conflict

إلا جوج branches بدلو نفس الجزء من نفس الملف، Git يقدر يقول:

```
CONFLICT
```

مثلاً:

```
<<<<<<< HEAD
code ديال main
=======
code ديال feature
>>>>>>> feature-login
```

أنت كتختار الكود الصحيح، كتصلح الملف، ومن بعد:

```
git add .
git commit
```

---

# 9. الفرق المهم جداً: restore / reset / revert

هاد النقطة مهمة حيث كنا هضرنا عليها.

## `git restore`

كيعاونك تلغي تغييرات فـ working directory أو staging.

مثلاً:

```
git restore file.c
```

يعني رجع `file.c` لآخر نسخة محفوظة.

---

## `git reset`

كيحرك `HEAD` للخلف.

مثلاً:

```
A ---- B ---- C
             ↑
            HEAD
```

درت:

```
git reset --hard B
```

تصبح:

```
A ---- B
      ↑
     HEAD
```

و C كيتحيد من المسار الحالي.

⚠️ `--hard` خاصك تكون حذر معاه حيث يقدر يحذف تغييرات مازال ما تحفظوش.

---

## `git revert`

ما كيمسحش التاريخ.

مثلاً:

```
A ---- B ---- C
```

بغيتي تلغي C.

Git كيصنع commit جديد:

```
A ---- B ---- C ---- D
                       ↑
                  revert C
```

هادشي غالباً هو الأسلوب الآمن ملي commit راه **pushed** للـ remote.

---

# 10. الفرق بينهم فجدول

|الأمر|الفكرة|
|---|---|
|`restore`|رجع تغييرات ملف|
|`reset`|رجع HEAD/branch للخلف|
|`revert`|دير commit جديد كيلغي commit قديم|

احفظها هكا:

```
restore → FILE
reset   → HISTORY / HEAD
revert  → NEW COMMIT
```

---

# 11. Remote و GitHub

ربط المشروع:

```
git remote add origin URL
```

شوف remotes:

```
git remote -v
```

جيب التغييرات:

```
git fetch
```

جيب ودمج:

```
git pull
```

صيفط commits:

```
git push
```

---

# 12. الفرق بين fetch و pull

مهم جداً:

```
fetch
```

كيجيب معلومات وتغييرات remote **بلا ما يدمجهم مباشرة**.

أما:

```
pull
```

تقريباً:

```
fetch + merge/rebase
```

يعني:

```
git pull
```

كيجيب التغييرات وكيحاول يدخلها للمشروع ديالك.

---

# 13. `.gitignore`

كتقول لـ Git:

> هاد الملفات ما تبقاش تتبعهم.

مثلاً:

```
node_modules/
.env
*.log
```

مهم جداً خصوصاً:

```
.env
```

حيت ممكن يكون فيه passwords وAPI keys.

---

# 14. HEAD

`HEAD` هو تقريباً:

> فين واقف دابا فـ Git history.

مثلاً:

```
A ---- B ---- C
             ↑
            HEAD
```

إلا رجعتي:

```
git switch --detach B
```

غادي تولي فـ commit B.

هاد الحالة كتسمى:

**detached HEAD**

---

# 15. Tag

Tag كتستعمل باش تعلم نسخة مهمة:

```
git tag v1.0.0
```

مثلاً:

```
v1.0.0
v1.1.0
v2.0.0
```

مفيدة للإصدارات.

---

# 16. Rebase

واحد من المفاهيم المتقدمة.

عندك:

```
A ---- B ---- C
       \
        D ---- E
```

Rebase كيحاول يخلي التاريخ خطي:

```
A ---- B ---- C ---- D' ---- E'
```

ولكن مهم:

> `rebase` كيعاود يكتب التاريخ.

لهذا خاص الحذر خصوصاً مع branches اللي خدامين عليها مع ناس آخرين.

---

# 17. Stash

عندك تغييرات مازال ما بغيتيش تدير ليها commit، ولكن خاصك تبدل branch.

تقدر:

```
git stash
```

التغييرات كتتحط مؤقتاً بعيد.

ومن بعد:

```
git stash pop
```

كتردهم.

تشوف stash:

```
git stash list
```

---

# 18. Cherry-pick

إلا بغيتي تاخذ **commit واحد فقط** من branch آخر:

```
git cherry-pick COMMIT_HASH
```

مثلاً:

```
main:    A ---- B
              \
feature:        C ---- D
```

بغيتي غير C:

```
git cherry-pick C
```

---

# 19. Git diff

باش تشوف شنو تبدل:

```
git diff
```

تشوف الفرق بين working directory و staging:

```
git diff
```

وبين staging وآخر commit:

```
git diff --staged
```

هاد الأوامر مهمين جداً قبل commit.

---

# 20. Workflow احترافي بسيط

فمشروع حقيقي، تقدر تخدم هكا:

```
git status

git switch -c feature-login

# تخدم...

git diff

git add .

git diff --staged

git commit -m "Add login validation"

git push -u origin feature-login
```

ومن بعد Pull Request فـ GitHub.

---

# 🧠 الخريطة اللي خاصك تحفظ

```
                    Git
                     │
       ┌─────────────┴─────────────┐
       ↓                           ↓
    Local                        Remote
       │                           │
       ↓                           ↓
 Working Directory             GitHub
       │
    git add
       ↓
 Staging Area
       │
   git commit
       ↓
 Repository
       │
    git push
       ↓
 GitHub
```

والأوامر الأساسية:

```
git init
git status
git add
git commit
git log
git diff

git branch
git switch
git merge

git remote
git fetch
git pull
git push

git restore
git reset
git revert

git stash
git tag
git rebase
git cherry-pick
```

## 🎯 ولكن أهم حاجة

ما تحفظش Git كـ **لائحة ديال الأوامر**.

فهم هاد السلسلة:

```
نبدل الملفات
     ↓
git diff
     ↓
git add
     ↓
Staging
     ↓
git diff --staged
     ↓
git commit
     ↓
Local history
     ↓
git push
     ↓
GitHub
```

ومن بعد ملي توقع مشكلة، كتسول:

> **فين وقعات المشكلة؟**

```
Working Directory؟
Staging؟
Commit؟
Branch؟
Remote؟
```

إلى فهمتي هاد المنطق، Git غادي يولي عندك **نظام مفهوم** ماشي غير أوامر كتنسخهم.

إلى بغيتي نمشيو **كتاب Pro Git chapitre par chapitre**، نقدر ندير لك خلاصة كل Chapter + الأوامر + تمارين عملية، وبالترتيب ديال الكتاب.
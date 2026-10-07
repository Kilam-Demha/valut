chof bghit nt3alem git pro bghitak tchra7 lia git chno howa kifach kikhdam o les command li ghadi nhtaj kamlin o 3tini summury 3afak

أكيد. غادي نشرح ليك **Git من الصفر حتى المستوى اللي تقدر تخدم به فـprojets حقيقيين**، ولكن ماشي غير نحفظوك commands: غادي نفهموك **كيفاش Git كيفكر وكيفاش خدام من الداخل**.

## 1. شنو هو Git؟

**Git هو Version Control System**، يعني نظام كيسجل التغييرات اللي كتدير فـprojet ديالك.

مثلاً عندك:

```
my-project/
├── index.html
├── style.css
└── script.js
```

خدمتي اليوم:

```
Version 1
```

من بعد بدلت الكود:

```
Version 2
```

ومن بعد خربتي شي حاجة:

```
Version 3 ❌
```

Git كيخليك ترجع لـ:

```
Version 1 ✅
Version 2 ✅
```

بلا ما تبقى دير:

```
project-final
project-final2
project-final-vraiment-final
project-final-final-2
```

😄

---

# 2. Git ≠ GitHub

هاد النقطة مهمة بزاف.

### Git

برنامج كيخدم **محلياً فـPC ديالك**.

```
Your PC
   │
   └── Git
```

### GitHub

خدمة Online كتخليك تخزن Git repositories وتشاركها.

```
Your PC                  GitHub
   │                       │
   │       push ─────────► │
   │                       │
   │ ◄───────── pull       │
```

يعني:

> **Git = الأداة**  
> **GitHub = مكان Online لاستضافة repositories**

كاينين حتى GitLab و Bitbucket وغيرهم.

---

# 3. كيفاش Git كيفكر؟

هادشي هو **أهم مفهوم فـGit كامل**.

Git عندو تقريباً 4 أماكن خاصك تفرق بينهم:

```
             ┌─────────────────┐
             │   Working Tree  │
             │   ملفاتك دابا   │
             └────────┬────────┘
                      │
                 git add
                      ↓
             ┌─────────────────┐
             │  Staging Area   │
             │ الملفات واجدين  │
             │    للـcommit    │
             └────────┬────────┘
                      │
                git commit
                      ↓
             ┌─────────────────┐
             │ Local Repository│
             │    التاريخ      │
             └────────┬────────┘
                      │
                  git push
                      ↓
             ┌─────────────────┐
             │     GitHub      │
             │ Remote Repo     │
             └─────────────────┘
```

حفظ هاد السلسلة:

```
WORKING TREE
     ↓
  git add
     ↓
STAGING
     ↓
git commit
     ↓
LOCAL REPO
     ↓
 git push
     ↓
 GITHUB
```

---

# 4. البداية ديال أي Project

مثلاً:

```
mkdir my-project
cd my-project
```

نقول لـGit:

```
git init
```

هاد الأمر كيحول directory عادي إلى Git repository.

كيخلق directory مخفي:

```
.git/
```

هاد `.git` هو **المخزن الحقيقي ديال Git**.

⚠️ ما تحيدوش.

---

# 5. أول command خاصك تعرف

```
git status
```

هاد command غادي تستعملو **بزاف**.

كيقول ليك:

- شنو تبدل
- شنو staged
- شنو مازال ما tracked
- branch اللي نتا فيه
- واش عندك changes

مثلاً:

```
git status
```

يعطيك:

```
Untracked files:
    index.html
```

يعني Git شاف الملف ولكن مازال ما بداش يتبعو.

---

# 6. git add

```
git add index.html
```

أو جميع الملفات:

```
git add .
```

دابا الملف مشى للـ:

```
STAGING AREA
```

ولكن **مازال ما تسجلش فالتاريخ**.

---

# 7. git commit

```
git commit -m "Add homepage"
```

Commit هو بحال **Snapshot** للحالة ديال المشروع.

مثلاً:

```
A ─── B ─── C ─── D
```

كل حرف = commit.

مثلاً:

```
A = initial project
B = add navbar
C = add login
D = fix validation
```

وهنا Git كيبدأ يكون عندك **history**.

باش تشوفو:

```
git log
```

أو بشكل مختصر:

```
git log --oneline
```

مثلاً:

```
8f31abc Fix validation
42aa12e Add login
91bc321 Add navbar
1a2b3c4 Initial commit
```

---

# 8. Commit Hash

كل commit عندو ID:

```
8f31abc...
```

هادشي كنسميوه:

**commit hash**

تقدر تستعملو باش تحدد commit معين.

مثلاً:

```
git show 8f31abc
```

---

# 9. أهم commands ديال Git

دابا نعطيك **الخريطة الكبيرة**.

## 🔵 البداية

```
git init
git clone <url>
```

### `git init`

إنشاء repository جديد.

### `git clone`

تحميل repository موجود:

```
git clone https://github.com/user/project.git
```

---

# 🟢 معرفة الحالة والتاريخ

```
git status
git log
git log --oneline
git log --graph --oneline --all
git show
git diff
```

### `git diff`

كيوريك التغييرات اللي مازال ما staged.

### `git diff --staged`

كيوريك التغييرات اللي staged.

---

# 🟡 إضافة وحذف الملفات

```
git add file.txt
git add .
```

حذف file مع تسجيل الحذف:

```
git rm file.txt
```

Rename:

```
git mv old.txt new.txt
```

---

# 🔴 التراجع

هاد الباب مهم بزاف.

كاين فرق بين:

```
restore
reset
revert
```

## `git restore`

كتستعملو باش ترجع تغييرات فـworking tree.

مثلاً:

```
git restore index.html
```

يعني:

> رجع الملف لآخر version مسجلة.

---

## `git restore --staged`

كتخرج الملف من staging:

```
git restore --staged index.html
```

يعني:

```
STAGING
   ↓
WORKING TREE
```

ولكن التعديل نفسه ما كيمسحوش.

---

# 10. git reset

`reset` أقوى.

مثلاً:

```
git reset --soft HEAD~1
```

كيحيد آخر commit ولكن التغييرات كيبقاو staged.

```
git reset --mixed HEAD~1
```

كيحيد commit والتغييرات كيبقاو فـworking tree.

```
git reset --hard HEAD~1
```

⚠️ قوي وخطير.

كيقدر يحيد commit والتغييرات ديالو.

فكر فيها:

```
A ─── B ─── C
          ↑
         HEAD
```

بعد:

```
git reset --hard HEAD~1
```

كتولي:

```
A ─── B
      ↑
     HEAD
```

---

# 11. git revert

مهم جداً خصوصاً فالـteam.

```
git revert <commit>
```

ما كيمسحش التاريخ.

كيخلق commit جديد كيعاكس التغيير.

مثلاً:

```
A ─── B ─── C
```

C فيه bug.

بدل ما تمسح C:

```
A ─── B ─── C ─── D
              ↑
         revert C
```

D كيعكس C.

لهذا:

> `reset` = تحريك/تغيير التاريخ  
> `revert` = إنشاء commit جديد يعكس commit قديم

---

# 12. Branches

هنا Git كيولي قوي بزاف.

عندك:

```
main
 │
 A
 │
 B
 │
 C
```

بغيتي تخدم feature جديدة:

```
git branch login
```

ومن بعد:

```
git switch login
```

أو مباشرة:

```
git switch -c login
```

دابا:

```
          D ─── E
         /
A ─── B ─── C
          main
```

عندك:

```
main
login
```

---

# 13. أهم Branch commands

```
git branch
```

تشوف branches.

```
git branch login
```

تصنع branch.

```
git switch login
```

تمشي للـbranch.

```
git switch -c login
```

تصنع + تمشي.

حذف:

```
git branch -d login
```

---

# 14. Merge

منين تسالي feature:

```
main
 │
 A ─── B
       \
        C ─── D
             login
```

كتقدر ترجع main:

```
git switch main
```

ومن بعد:

```
git merge login
```

والهدف:

```
A ─── B ───────── E
       \         /
        C ─── D
```

---

# 15. Merge Conflict

إلا جوج branches بدلو نفس الجزء:

```
main:
Hello Ahmed

login:
Hello Ahmed
Welcome!
```

وmain تبدلات حتى هي:

```
Hello Ahmed
Good morning!
```

Git يقدر يقول:

```
CONFLICT
```

فملف غادي تلقى:

```
<<<<<<< HEAD
Good morning!
=======
Welcome!
>>>>>>> login
```

نتا خاصك تختار شنو يبقى.

من بعد:

```
git add .
git commit
```

---

# 16. Remote

دابا ندخلو GitHub.

تشوف remotes:

```
git remote -v
```

تضيف GitHub:

```
git remote add origin <URL>
```

مثلاً:

```
local repository
      │
      │ origin
      ↓
GitHub repository
```

---

# 17. Push

```
git push
```

أول مرة غالباً:

```
git push -u origin main
```

معناها:

```
local main
     │
     │ push
     ↓
origin/main
```

---

# 18. Fetch vs Pull

هاد الفرق خاصك تفهمو مزيان.

## `git fetch`

كيجيب معلومات جديدة من remote:

```
git fetch
```

ولكن ما كيدمجهاش مباشرة فـbranch ديالك.

---

## `git pull`

تقريباً:

```
git fetch
+
git merge
```

يعني:

```
git pull
```

كيجيب التغييرات وكيحاول يدمجها.

---

# 19. Tracking Branch

مثلاً:

```
git push -u origin main
```

`-u` كتربط:

```
local main
      ↕
origin/main
```

من بعد تقدر غير:

```
git push
git pull
```

---

# 20. HEAD

واحد من أهم المفاهيم.

`HEAD` كيشير للمكان اللي نتا واقف فيه.

مثلاً:

```
A ─── B ─── C
          ↑
         HEAD
```

يعني نتا حالياً فـC.

إلا درتي:

```
git switch main
```

HEAD كيتحرك للـmain.

---

# 21. HEAD~1 / HEAD~2

```
HEAD
 ↓
 C
 ↓
 B
 ↓
 A
```

```
HEAD~1 = B
HEAD~2 = A
```

مثلاً:

```
git reset HEAD~1
```

يعني رجع commit واحد للور.

---

# 22. Stash

عندك changes:

```
working tree
   ↓
changes
```

ولكن خاصك تبدل branch بسرعة.

تقدر:

```
git stash
```

Git كيخبي التغييرات مؤقتاً.

تشوفهم:

```
git stash list
```

ترجعهم:

```
git stash pop
```

أو:

```
git stash apply
```

الفرق:

```
pop
= apply + remove stash

apply
= apply فقط
```

---

# 23. Tag

Tags كتستعمل غالباً للإصدارات.

مثلاً:

```
git tag v1.0.0
```

ثم:

```
git push origin v1.0.0
```

كتقدر تقول:

```
v1.0.0
v1.1.0
v2.0.0
```

---

# 24. .gitignore

ملف مهم جداً:

```
.gitignore
```

مثلاً Node.js:

```
node_modules/
.env
```

يعني Git ما يتبعش هادو.

مهم جداً:

```
.env
```

غالباً فيه passwords/API keys.

ما خاصوش يطلع لـGitHub.

---

# 25. Git Config

شوف configuration:

```
git config --list
```

حدد الاسم:

```
git config --global user.name "Ahmed"
```

الإيميل:

```
git config --global user.email "email@example.com"
```

---

# 26. Git Aliases

تقدر تختصر commands.

مثلاً:

```
git config --global alias.st status
```

دابا:

```
git st
```

بدل:

```
git status
```

---

# 27. Rebase

هاد الموضوع مهم فـGit Pro.

مثلاً:

```
A ─── B ─── C
       \
        D ─── E
```

تقدر تستعمل:

```
git rebase main
```

والتاريخ كيولي linear أكثر.

ولكن:

⚠️ `rebase` كيعاود يكتب التاريخ.

قاعدة مهمة:

> ما تديرش rebase عشوائياً على commits shared مع الفريق إلا كنت فاهم العواقب.

---

# 28. Interactive Rebase

مفيد باش تنظف commits:

```
git rebase -i HEAD~3
```

تقدر:

```
pick
reword
edit
squash
fixup
drop
```

مثلاً:

```
fix typo
fix typo again
add login
```

تقدر تجمع commits:

```
Add login
```

هادشي كنسميوه:

**squashing commits**

---

# 29. Cherry-pick

عندك commit واحد من branch آخر وبغيتي غير هو:

```
git cherry-pick <commit>
```

مثلاً:

```
main:
A ─── B

feature:
     └── C ─── D
```

بغيتي C فقط:

```
git cherry-pick C
```

---

# 30. Git Bisect

هاد واحد pro بزاف.

عندك:

```
100 commits
```

وكتعرف أن bug كان ما كاينش فواحد commit قديم ولكن موجود فآخر commit.

بدل تقلب على 100 commit، Git يقدر يدير **binary search**.

```
git bisect start
git bisect bad
git bisect good <commit>
```

ومن بعد كتقول ليه:

```
git bisect good
```

أو:

```
git bisect bad
```

حتى يلقا commit اللي دخل bug.

---

# 31. Git Reflog

هاد command مهم جداً:

```
git reflog
```

كيوريك تحركات `HEAD`.

مثلاً درتي:

```
git reset --hard
```

وبغيتي ترجع commit اللي ضاع.

غالباً:

```
git reflog
```

تلقى:

```
abc123 HEAD@{0}
def456 HEAD@{1}
ghi789 HEAD@{2}
```

ومن بعد تقدر ترجع.

لهذا:

> `reflog` = واحد من أهم أدوات الإنقاذ فـGit.

---

# 32. Git Clean

كيحيد untracked files:

```
git clean
```

⚠️ خاص الحذر.

قبل:

```
git clean -n
```

هاد `-n` غير كيوريك شنو غادي يتحيد.

ومن بعد إذا كنت متأكد:

```
git clean -f
```

---

# 33. Git log الاحترافي

واحد command زوين:

```
git log --oneline --graph --decorate --all
```

يعطيك graph ديال التاريخ:

```
* 91ab Fix login
* 82bc Add login
| * 72cd Add dashboard
|/
* 61aa Initial project
```

---

# 34. Workflow احترافي

فـproject حقيقي، workflow بسيط ممكن يكون:

```
             main
              │
              ↓
       git switch -c feature
              │
              ↓
        Write code
              │
              ↓
         git status
              │
              ↓
          git diff
              │
              ↓
           git add
              │
              ↓
          git commit
              │
              ↓
          git push
              │
              ↓
        Pull Request
              │
              ↓
           Review
              │
              ↓
           Merge
              │
              ↓
            main
```

---

# 🧠 الخلاصة القوية ديال Git

إلى بغيتي تحفظ **العقلية** ديال Git، حفظ هاد الصورة:

```
                     GIT
                      │
       ┌──────────────┼──────────────┐
       │              │              │
    HISTORY        BRANCHES       REMOTE
       │              │              │
     commit          switch          push
     log             branch          pull
     diff            merge           fetch
     show            rebase          clone
       │
       │
   UNDO / RECOVERY
       │
 ┌─────┼─────────┬─────────┐
 │     │         │         │
restore reset   revert   reflog
```

وأهم commands اللي خاصك تكون حافظهم:

```
git init
git clone
git status

git add
git commit

git log
git diff
git show

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

git reflog
git bisect

git clean
```

ولكن **ما أنصحكش تحفظهم كاملين دابا**. اللي غادي يخليك Git Pro فعلاً هو أنك تفهم:

```
Working Tree
      ↓
Staging Area
      ↓
Commit
      ↓
Branch
      ↓
Remote
      ↓
GitHub
```

ومن بعد نفهمو بعمق:

**commit → branch → merge → conflict → reset/restore/revert → rebase → remote → collaboration.**

هاد الترتيب غادي يبني ليك Git مزيان من الأساس، وما غاديش تبقى غير حافظ commands.
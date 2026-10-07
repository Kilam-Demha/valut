إييه، بما أنك وصلتي فـ Linux لـ `grep` / `find` / pipes / redirection، اليوم نقدروا نزيدو **commands مهمين بزاف** بلا ما نقفزو بزاف.

### اليوم نقترح هاد المجموعة:

1. **`wc`** — تحسب lines / words / characters
2. **`sort`** — ترتب البيانات
3. **`uniq`** — تحيد التكرار / تحسب التكرارات
4. **`cut`** — تقطع أجزاء من كل line
5. **`tr`** — تبدل أو تحيد characters
6. **`head`** — تاخذ البداية ديال file/output
7. **`tail`** — تاخذ النهاية
8. **`tee`** — تشوف output وتكتبوه فـ file فنفس الوقت
9. **`xargs`** — تحول output ديال command إلى arguments لـ command آخر

هاد المجموعة غادي تعلمك واحد concept مهم فـ Linux:

**commands صغار → pipe → processing ديال data**

مثلاً من بعد غادي تولي قادر تدير pipeline بحال:

`command → grep → sort → uniq → wc`

ولكن **ما غاديش نعطيك الحلول ولا commands ديال التمارين**. نعطيك concept + المطلوب، وانت تكتبهم بيدك.

إلى بغيتي نمشيو بالطريقة ديالك، نبدأو بـ **`wc` من الصفر + تمارين واحد بواحد**.

ok

مزيان. نبدأو بـ **`wc`**.

## `wc` — Word Count

`wc` command كتستعمل باش **نحسبو معلومات على النص** داخل file ولا output ديال command.

أهم الحوايج اللي كتقدر تحسب:

- **lines** → عدد السطور
- **words** → عدد الكلمات
- **characters/bytes** → عدد الحروف أو الـ bytes

### الفكرة

إلا كان عندك file فيه:

```
hello world
linux is powerful
I am learning C
```

`wc` تقدر تعرف مثلاً:

- شحال من line؟
- شحال من word؟
- شحال من character؟

### أهم options

|Option|المعنى|
|---|---|
|`-l`|lines|
|`-w`|words|
|`-c`|bytes|
|`-m`|characters|

---

## 🧪 التمرين 1

صايب file جديد سميه:

`data.txt`

ودير فيه **5 سطور**، وكل سطر فيه كلمات مختلفة.

المطلوب:

1. عرف عدد الـ **lines**.
2. عرف عدد الـ **words**.
3. عرف عدد الـ **bytes**.
4. عرف عدد الـ **characters**.

**ممنوع تشوف الحل عندي 😄**  
نفّذها فـ terminal، وصيفط ليا غير commands اللي استعملتي والـ output ديالهم، وأنا نصحح لك.

chof ghadi dir lia list fiha 20 commands bi tamarin dialha nhal hakka char7 omen baaad tamarin

إييه، هادي أحسن طريقة ليك. غادي نعطيك **20 Linux commands** مرتبين من الساهل للصعيب، وكل command فيها:

**1. شرح concept → 2. أهم options → 3. تمارين بلا حلول**

وما غاديش نعطيك commands ديال الحلول فالتداريب؛ **نتا اللي تكتبهم وتنفذهم**.

# 🐧 Linux — 20 Commands

## المستوى 1 — Text & Files

### 1. `wc`

**Concept:** حساب المعلومات على النصوص.

خاصك تعرف:

- `-l` → lines
- `-w` → words
- `-c` → bytes
- `-m` → characters

**تمارين:**

- صايب `data.txt` فيه 5 سطور.
- حسب عدد السطور.
- حسب الكلمات.
- حسب characters.
- استعمل `wc` مع output ديال command آخر بـ pipe.

---

### 2. `head`

**Concept:** تاخذ البداية ديال file/output.

خاصك تعرف:

- `-n`

**تمارين:**

- صايب file فيه 20 سطر.
- خرج أول 5 سطور.
- خرج أول 10 سطور.
- استعمل `head` مع command آخر.

---

### 3. `tail`

**Concept:** تاخذ النهاية ديال file/output.

خاصك تعرف:

- `-n`
- `-f` concept ديالو مهم من بعد.

**تمارين:**

- خرج آخر 5 سطور من file.
- خرج آخر 10.
- جرّب `tail` مع output ديال command آخر.

---

### 4. `sort`

**Concept:** ترتيب lines.

خاصك تعرف:

- `-r` → reverse
- `-n` → numerical
- `-u` → unique

**تمارين:**

- رتب أسماء alphabetically.
- رتب أرقام numerically.
- رتبهم بالعكس.
- جرّب ترتب data فيها duplicates.

---

### 5. `uniq`

**Concept:** التعامل مع **lines المتكررة**.

خاصك تعرف:

- `-c` → count
- `-d` → duplicates فقط
- `-u` → unique lines

⚠️ نقطة مهمة: `uniq` كيخدم أساساً مع **duplicates المتتابعين**.

**تمارين:**

- صايب file فيه أسماء مكررة.
- اكتشف التكرارات.
- حسب شحال تكررات كل قيمة.
- استعمل `sort` مع `uniq`.

---

## المستوى 2 — Processing Text

### 6. `cut`

**Concept:** تقطع جزء من كل line.

خاصك تعرف:

- `-d` → delimiter
- `-f` → fields
- `-c` → characters

مثلاً data بحال:

```
Ahmed:28:Safi
Ali:25:Marrakech
Omar:30:Agadir
```

**تمارين:**

- خرج غير الأسماء.
- خرج غير الأعمار.
- خرج غير المدن.
- جرّب delimiter مختلف.

---

### 7. `tr`

**Concept:** تحويل أو حذف characters.

خاصك تعرف:

- تبديل characters
- حذف characters
- تحويل lowercase/uppercase

**تمارين:**

- حول lowercase لـ uppercase.
- حول uppercase لـ lowercase.
- بدل character بآخر.
- حيد character معين من text.

---

### 8. `tee`

**Concept:** output يمشي لجوج directions:

```
command
   ↓
  tee
 ↙   ↘
terminal  file
```

**تمارين:**

- خذ output ديال command وخليه يظهر فالterminal ويتسجل فـ file.
- جرّب append بدل overwrite.
- دير pipeline واستعمل `tee` وسطها.

---

### 9. `xargs`

**Concept:** ياخذ output ويحولو لـ arguments ديال command آخر.

الفكرة:

```
output → xargs → command
```

**تمارين:**

- صايب list ديال filenames.
- خليهوم يتحولو arguments لـ command آخر.
- جرّب مع أكثر من input.
- استعمل `find` + `xargs`.

---

### 10. `basename`

**Concept:** استخراج اسم الملف من path.

مثلاً conceptually:

```
/home/ahmed/projects/app/main.c
                         ↓
                       main.c
```

**تمارين:**

- جرّب paths مختلفة.
- استخرج أسماء ملفات من paths.
- استعمله مع output ديال command آخر.

---

## المستوى 3 — Files & Permissions

### 11. `chmod`

**Concept:** تغيير permissions.

خاصك تفهم:

```
r = read
w = write
x = execute
```

و:

```
user
group
others
```

**تمارين:**

- صايب file.
- خليه readable فقط.
- زيد write permission.
- حيد write permission.
- صايب script وخليه executable.
- جرّب notation الرقمية.

---

### 12. `chown`

**Concept:** تغيير owner ديال file.

خاصك تفهم:

```
owner
group
```

**تمارين:**

- شوف owner ديال files.
- شوف group.
- جرّب تغيير ownership فـ environment اللي عندك permission فيه.
- فهم الفرق بين `chown` و`chmod`.

---

### 13. `ln`

**Concept:** links.

جوج أنواع مهمين:

```
hard link
symbolic link
```

**تمارين:**

- صايب file.
- صايب symbolic link ليه.
- بدّل محتوى الأصل وشوف link.
- حيد الأصل وشوف شنو كيوقع.
- تعلم كيفاش تميز symlink.

---

### 14. `stat`

**Concept:** تشوف metadata ديال file.

غادي تشوف معلومات بحال:

- size
- permissions
- owner
- timestamps
- inode

**تمارين:**

- استعمل `stat` على file.
- قارن metadata ديال جوج files.
- شوف inode.
- بدّل file وشوف timestamps.

---

## المستوى 4 — Search & Processes

### 15. `which`

**Concept:** فين كاين executable ديال command.

مثلاً conceptually:

```
command → PATH → executable
```

**تمارين:**

- قلب على location ديال commands مختلفة.
- قارن بين commands موجودين وما موجودينش.
- فهم علاش shell كيقدر يلقا command.

---

### 16. `type`

**Concept:** تعرف شنو هو command بالنسبة للShell.

ممكن يكون:

- executable
- alias
- builtin
- function

**تمارين:**

- استعمل `type` على commands مختلفة.
- قلب على الفرق بين builtin و executable.
- جرّب command عندو alias.

---

### 17. `ps`

**Concept:** تشوف processes.

خاصك تفهم:

```
PID
PPID
USER
CPU
MEM
COMMAND
```

**تمارين:**

- عرض processes ديالك.
- قلب على process معين.
- شوف PID ديالو.
- استعمل `ps` بأكثر من format.

---

### 18. `kill`

**Concept:** إرسال signal لـ process.

⚠️ `kill` ما كتعنيش دائماً "قتل process".

مفهوم مهم:

```
process
   ↑
 signal
```

**تمارين:**

- صايب process بسيط.
- عرف PID ديالو.
- أرسل signal عادي.
- جرّب signals مختلفة وفهم الفرق بينهم.

---

## المستوى 5 — Advanced Shell

### 19. `tee` + `grep` + `sort` + `uniq` + `wc`

هنا ما بقيناش نتعلمو command بوحدها.

غادي تتعلم **pipeline thinking**:

```
command
   ↓
grep
   ↓
sort
   ↓
uniq
   ↓
wc
```

**تمارين:**

عطيك data فيها:

- usernames
- commands
- duplicate entries
- errors

والمطلوب:

- filter
- sort
- count duplicates
- count final results

**بلا ما تستعمل script. غير terminal + pipelines.**

---

### 20. `find` + `xargs` + `grep` + `wc`

هاد التمرين غادي يجمع بزاف ديال اللي تعلمتي.

Concept:

```
find
 ↓
files
 ↓
xargs
 ↓
grep
 ↓
wc
```

**Project صغير:**

صايب directory فيه structure بحال:

```
project/
├── src/
├── docs/
├── tests/
└── logs/
```

حط files مختلفة داخلو.

المطلوب:

- قلب على files حسب extension.
- قلب داخل files على كلمة معينة.
- حسب شحال من file فيهاتها.
- حسب شحال من occurrence/line مرتبطة بها.
- دير pipeline كاملة.
- خدم بلا GUI.

---

# 🎯 الترتيب اللي غادي نخدمو به

```
01 wc
02 head
03 tail
04 sort
05 uniq
06 cut
07 tr
08 tee
09 xargs
10 basename
11 chmod
12 chown
13 ln
14 stat
15 which
16 type
17 ps
18 kill
19 pipelines
20 find + xargs + grep + wc
```

ومن بعد هاد 20، نقدروا ندوزو لـ **pro Linux**:  
`sed` → `awk` → `env` → `export` → `source` → `jobs` → `bg/fg` → `nohup` → `cron` → `systemctl` → networking commands → logs → bash scripting.

**ودابا ما غاديش نقفزو للـ 20 كاملين دفعة وحدة:** غادي نبدأو بـ **01 `wc`**، نشرحو مزيان، ومن بعد نعطيك التمارين، ونتا تحلهم.
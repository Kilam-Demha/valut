chof nkdar n3tik url fi githup otchra7 lia

Ah, bien sûr 👍 عطيني **URL ديال GitHub repo** وأنا نشرحو ليك.

نقدر نشرح ليك مثلاً:

- 📁 Structure ديال المشروع والـfolders
- ⚙️ كيفاش الكود خدام
- 🔄 Flow ديال التطبيق من البداية للنهاية
- 🧩 أهم functions/classes والـdependencies
- 🐛 المشاكل أو bugs اللي باينين
- 🚀 كيفاش تشغلو وتطورو
- وإذا بغيتي، نشرح **file par file** وبالدارجة.

صيفط ليا غير الـURL.

[Its-Kaizen/1337-Pool-Piscine-42-Network](https://github.com/Its-Kaizen/1337-Pool-Piscine-42-Network)

إيه، شفت الـrepo ديالك. [GitHub repository](https://github.com/Its-Kaizen/1337-Pool-Piscine-42-Network?utm_source=chatgpt.com)

هو repo ديال **1337/42 Piscine ديال يوليوز 2023 فـ Benguerir**، وفيه `DAYS`, `EXAMS`, و`RUSH`، ومعاه README كيشرح الـPool والمواضيع اللي كتدوز فيها.

نقدر نخدمو معاك **ماشي غير نعطيك الحلول**، ولكن نشرح ليك المنطق باش تولّي قادر تحل بوحدك.

مثلاً نقدر نبداو هكا:

1. **DAYS** → نشرح `Shell` و`C` exercise بـ exercise.
2. **Week 1 → Week 4** → شنو خاصك تتعلم فكل مرحلة.
3. **C exercises** → نشرح كل function، variables، loops، pointers، strings...
4. **EXAMS** → نشرح شنو كيتكرر وكيفاش تفكر فـexam.
5. أي exercise ما فهمتيهش → صيفط ليا اسمو/الرابط ديالو ونفككو **step by step بالدارجة**.

إلا الهدف ديالك هو **توجد للـPiscine ديال 1337**، نقدر حتى ندير ليك roadmap من `Day 00` حتى `Exam 04` باستعمال هاد الـrepo.

bghit dial Shell01

أكيد. بالنسبة لـ **Shell 01** فهاد الـrepo، نقدر نشرح ليك كل exercise **واحد بواحد** وبالدارجة، مع شرح علاش كنستعملو كل command.

غير باش ما نعطيكش شرح على ملفات غلط، غادي نفتح محتوى `Shell01` من الـrepo ونمشيو من `ex00` حتى الآخر.

صيفط ليا غير واش بغيتي **نشرح جميع exercises ديال Shell01 بالترتيب** ولا نبداو بـ **ex00**؟

ok kamlin

أكيد. غادي نعلمهملك **من الصفر وبالمنطق**، حيث الهدف ديالك هو ملي تشوف exercise تعرف بوحدك شنو command خاصك تستعمل.

غادي نقسمهم لمجموعات، ونبدأو بالأساسيات.

## 1. `cat` — قرا file

إلا عندك file سميتو `file.txt`:

```
cat file.txt
```

مثلاً فيه:

```
hello
world
42
```

غادي يطبع:

```
hello
world
42
```

يعني:

> `cat` = ورّيني محتوى الملف.

### جرب:

```
echo "hello 42" > file.txt
cat file.txt
```

هنا استعملنا `>` باش صنعنا file وكتبنا فيه.

---

# 2. `head` — خذ البداية

عندك:

```
1
2
3
4
5
6
7
8
9
10
```

إلا درتي:

```
head file.txt
```

غادي يعطيك غالباً أول **10 lines**.

تقدر تحدد العدد:

```
head -n 3 file.txt
```

النتيجة:

```
1
2
3
```

يعني:

```
head -n NUMBER FILE
```

> عطيني أول NUMBER lines.

---

# 3. `tail` — خذ النهاية

العكس ديال `head`.

```
tail -n 3 file.txt
```

يعطي:

```
8
9
10
```

ولكن عندو استعمال مهم فـPiscine:

```
tail -n +5 file.txt
```

معناها:

> بدا من line 5 حتى للآخر.

مثلاً:

```
1
2
3
4
5
6
7
```

يعطي:

```
5
6
7
```

---

# 4. `wc` — عد

`wc` = **word count**، ولكن يقدر يعد lines/words/characters.

### عد lines

```
wc -l file.txt
```

مثلاً:

```
10 file.txt
```

يعني عندك 10 lines.

### عد words

```
wc -w file.txt
```

### عد characters

```
wc -c file.txt
```

ركز خصوصاً على:

```
wc -l
```

حيت غادي تحتاجها بزاف.

---

# 5. `find` — قلب

بغينا نعرفو جميع files اللي عندنا:

```
find .
```

`.` معناها:

> current directory.

مثلاً:

```
.
./file.txt
./test.sh
./folder
./folder/a.sh
```

### غير files

```
find . -type f
```

### غير directories

```
find . -type d
```

### files ديال `.sh`

```
find . -type f -name "*.sh"
```

هنا:

```
-type f
```

= file

و:

```
-name "*.sh"
```

= الاسم كيسالي بـ `.sh`.

---

# 6. `grep` — قلب/filter على text

عندك:

```
hello
world
hello 42
1337
```

دير:

```
grep "hello" file.txt
```

يعطي:

```
hello
hello 42
```

يعني:

> وريني غير lines اللي فيها `hello`.

### مهم جداً

```
grep "^hello"
```

`^` معناها:

> البداية ديال line.

يعني غادي يجيب:

```
hello
hello 42
```

ولكن مثلاً:

```
say hello
```

ما غاديش يجيبها.

و:

```
grep "hello$"
```

`$` معناها:

> النهاية ديال line.

---

# 7. `cut` — قطع field

هاد command مهم بزاف.

شوف هاد line:

```
amine:x:1000:1000:Amine:/home/amine:/bin/bash
```

fields مفصولين بـ `:`.

بغينا غير username:

```
echo "amine:x:1000:1000:Amine:/home/amine:/bin/bash" | cut -d: -f1
```

النتيجة:

```
amine
```

### نفهموها:

```
-d:
```

يعني delimiter هو `:`.

و:

```
-f1
```

يعني:

> عطيني field رقم 1.

مثلاً:

```
cut -d: -f1
```

→ الأول

```
cut -d: -f2
```

→ الثاني

```
cut -d: -f7
```

→ السابع.

هادشي مهم بزاف مع `/etc/passwd`.

---

# 8. `sort` — رتب

عندك:

```
banana
apple
orange
car
```

دير:

```
sort file.txt
```

يعطي:

```
apple
banana
car
orange
```

### reverse

```
sort -r file.txt
```

يعطي:

```
orange
car
banana
apple
```

يعني:

```
sort
```

= ترتيب

```
sort -r
```

= reverse order

---

# 9. `tr` — بدل characters

عندك:

```
hello world
```

بغيتي تبدل space بـ `,`:

```
echo "hello world" | tr ' ' ','
```

النتيجة:

```
hello,world
```

مثال آخر:

```
echo "hello" | tr 'a-z' 'A-Z'
```

يعطي:

```
HELLO
```

يعني `tr` كيدير **character translation**.

### وحاجة مهمة

باش تحيد characters:

```
tr -d 'a'
```

مثلاً:

```
echo "banana" | tr -d 'a'
```

يعطي:

```
bnn
```

---

# 10. `groups` — groups ديال user

```
groups
```

كيعطي groups ديال **user الحالي**.

مثلاً:

```
user sudo docker
```

وتقدر تحدد user:

```
groups root
```

يعني:

> عطيني groups ديال root.

هادشي هو اللي كتحتاج فـShell01 ex01.

---

# 11. `ifconfig` — network

```
ifconfig
```

كيعطي information على network interfaces.

ممكن تلقى:

```
eth0
inet 192.168.1.20
ether aa:bb:cc:dd:ee:ff
```

الـ:

```
aa:bb:cc:dd:ee:ff
```

هي **MAC address**.

وهنا تقدر تفهم علاش ex04 كيستعمل:

```
ifconfig | grep ether
```

يعني:

```
ifconfig
   ↓
grep ether
   ↓
جيب غير lines اللي فيهم ether
```

---

# 12. `|` — PIPE ⭐

هاد واحد من **أهم الحوايج فالـShell**.

مثلاً:

```
cat file.txt | grep hello
```

المعنى:

```
cat file.txt
     ↓
   output
     ↓
    grep
     ↓
غير lines اللي فيهم hello
```

يعني:

> خذ output ديال command الأول وعطيه للثاني.

وتقدر تجمع بزاف:

```
cat file.txt | grep hello | sort
```

يعني:

```
cat
 ↓
grep
 ↓
sort
```

وهنا كتبدأ قوة الـShell.

---

# 13. `>` — redirect ⭐

بدل ما output يمشي للterminal، نقدروا نحطوه فـfile.

مثلاً:

```
echo "hello" > file.txt
```

دابا:

```
cat file.txt
```

يعطي:

```
hello
```

### مهم

`>` كيمسح المحتوى القديم.

مثلاً:

```
echo "A" > file.txt
echo "B" > file.txt
```

الـfile غادي يكون فيه غير:

```
B
```

أما:

```
echo "A" >> file.txt
echo "B" >> file.txt
```

غادي يكون:

```
A
B
```

يعني:

```
>   overwrite
>>  append
```

---

# 14. `-n` مع `echo`

عادي:

```
echo "hello"
```

كيطبع:

```
hello
```

ولكن كيزيد **newline** من بعد.

مع:

```
echo -n "hello"
```

ما كيزيدش newline.

هادشي مهم فـPiscine حيث مرات الـsubject كيقول:

> no newline at the end

فتستعمل:

```
echo -n "42"
```

---

# 🔥 دابا نجمعوهم

هاد command:

```
cat /etc/passwd | grep -v "^#" | cut -d: -f1 | sort
```

إلا فهمتي كل جزء، راك بديتي تفهم Shell مزيان.

### Step 1

```
cat /etc/passwd
```

قرا `/etc/passwd`.

### Step 2

```
grep -v "^#"
```

حيد lines اللي كيبداو بـ `#`.

### Step 3

```
cut -d: -f1
```

خذ أول field.

### Step 4

```
sort
```

رتبهم.

يعني command واحد طويل، ولكن هو غير:

```
READ
 ↓
FILTER
 ↓
EXTRACT
 ↓
SORT
```

وهذا بالضبط هو التفكير اللي خاصك فـPiscine.

---

## 🧪 أول Test ليك

صايب file:

```
echo "banana" > test.txt
echo "apple" >> test.txt
echo "orange" >> test.txt
echo "apple pie" >> test.txt
echo "42" >> test.txt
```

ومن بعد حاول بوحدك تجاوب:

**1.** كيفاش نخرج غير lines اللي فيهم `apple`؟

**2.** كيفاش نرتب جميع lines؟

**3.** كيفاش نخرج أول جوج lines؟

**4.** كيفاش نخرج آخر جوج lines؟

**5.** كيفاش نبدل كل `a` بـ `X`؟

**6.** كيفاش نحسب عدد الـlines؟

**7.** كيفاش نحط النتيجة ديال `sort` فـ `sorted.txt`؟

جاوبني غير بـ **7 commands**، وأنا نصححهم ليك ونشرح ليك أي حاجة غلط.

db hada char7 pro li 3taitini

إييه بالضبط 😄 هاد الشرح اللي عطيتك دابا هو **الشرح ديال الـcommands اللي غادي تحتاجهم فـ Shell01**، ولكن مازال ما دخلناش بعمق كبير فـكل command.

إلى بغيتي تتعلمهم **باحتراف**، نقدر ندير معاك واحد الطريقة أحسن:

**Command → syntax → كيفاش كيخدم → options → أمثلة → exercises → challenge ديال Piscine.**

مثلاً `grep` ماشي غير:

```
grep "hello" file
```

ولكن نفهمو:

```
grep [options] pattern [file]
```

ومن بعد:

```
grep -i
grep -v
grep -n
grep -r
grep "^"
grep "$"
grep "pattern1\|pattern2"
```

ونعرفو **إمتى تستعمل كل وحدة وعلاش**.

ونفس الشيء مع:

`find → wc → grep → sed → awk → cut → sort → tr → head → tail → pipe → redirect`

### والأهم

غادي نربط كل command مباشرة بـ **Shell01 exercises**، مثلاً:

```
ex01 → groups + tr
ex02 → find + sed
ex03 → find + wc
ex04 → ifconfig + grep + awk
ex05 → quoting + echo + redirect
ex06 → ls + awk
ex07 → cat + grep + cut + sort + ...
ex08 → نفس concepts ولكن بتركيب أكثر
```

يعني فالأخير ملي تشوف:

> "Find all `.sh` files and display only their names"

مخك مباشرة يقول:

```
find → نبحث
-type f → files
-name "*.sh" → extension
|
sed → نبدل/نحيد path و extension
```

**هاد المستوى هو اللي كنقصد بـ "تعلمهم".**

atini tamarin dial 2h nkhdamhom fi dar afak

أكيد 💪 نعطيك **programme ديال 2h** بحال mini-Piscine باش تتدرب فالدار. غادي نخلي التمارين **من الساهل للصعيب**، وما نعطيكش الحلول دابا باش تحاول بوحدك.

# 🐚 Shell Training — 2 Hours

## ⏱️ 0:00 → 0:15 — Warm-up

صايب dossier جديد:

```
mkdir shell_training
cd shell_training
```

وصايب هاد الملفات:

```
echo "banana" > fruits.txt
echo "apple" >> fruits.txt
echo "orange" >> fruits.txt
echo "apple pie" >> fruits.txt
echo "banana split" >> fruits.txt
echo "42" >> fruits.txt
```

### Exercise 1

طبع محتوى `fruits.txt`.

### Exercise 2

حسب شحال من line كاينة.

### Exercise 3

طبع غير أول 3 lines.

### Exercise 4

طبع غير آخر 2 lines.

### Exercise 5

حط محتوى `fruits.txt` فـ:

```
backup.txt
```

---

# ⏱️ 0:15 → 0:35 — `grep`

عندك:

```
banana
apple
orange
apple pie
banana split
42
```

### Exercise 6

خرج غير lines اللي فيهم:

```
apple
```

### Exercise 7

خرج غير lines اللي **مافيهمش** `apple`.

### Exercise 8

خرج غير lines اللي كيبداو بـ:

```
banana
```

### Exercise 9

خرج غير lines اللي كيساليو بـ:

```
split
```

### Exercise 10

حسب شحال من lines فيهم:

```
banana
```

💡 **Hint:** حاول تجمع `grep` مع `wc`.

---

# ⏱️ 0:35 → 0:55 — `sort` + `tr`

### Exercise 11

رتب `fruits.txt` alphabetically.

### Exercise 12

رتبو بالعكس.

### Exercise 13

بدل جميع الحروف الصغيرة إلى uppercase.

مثلاً:

```
apple
```

تصبح:

```
APPLE
```

### Exercise 14

بدل كل `a` بـ `@`.

مثلاً:

```
banana
```

تصبح:

```
b@n@n@
```

### Exercise 15

حيد جميع `a` من الملف.

---

# ⏱️ 0:55 → 1:15 — `find`

صايب structure:

```
project/
├── a.sh
├── b.txt
├── c.sh
├── test/
│   ├── hello.sh
│   ├── test.txt
│   └── deep/
│       └── wow.sh
└── docs/
    └── readme.md
```

تقدر تصايبها بالـcommands اللي عرفتي.

### Exercise 16

لقا جميع `.sh` files.

### Exercise 17

لقا جميع `.txt` files.

### Exercise 18

لقا جميع directories.

### Exercise 19

لقا غير regular files.

### Exercise 20 ⭐

لقا جميع `.sh` files ولكن خرج **غير الاسم**:

بدل:

```
./project/test/hello.sh
```

بغيتي:

```
hello.sh
```

---

# ⏱️ 1:15 → 1:35 — `cut` + `/etc/passwd`

دابا دخلنا للـPiscine الحقيقي 😈

جرب:

```
cat /etc/passwd
```

غادي تشوف lines بحال:

```
root:x:0:0:root:/root:/bin/bash
```

كلشي مفصول بـ:

```
:
```

### Exercise 21

خرج **غير usernames**.

يعني:

```
root
daemon
bin
sys
...
```

### Exercise 22

خرج **غير UID**.

مثلاً من:

```
root:x:0:0:root:/root:/bin/bash
```

بغيتي:

```
0
```

### Exercise 23

خرج **home directory**.

مثلاً:

```
/root
```

### Exercise 24 ⭐

خرج usernames ورتبهم alphabetically.

### Exercise 25 ⭐⭐

خرج usernames اللي فيهم الحرف:

```
a
```

ورتبهم.

---

# ⏱️ 1:35 → 1:50 — `awk`

دابا نزيدو difficulty.

عندك:

```
echo "amine 42 1337" > data.txt
echo "yassine 25 42" >> data.txt
echo "mehdi 30 1337" >> data.txt
```

### Exercise 26

خرج غير الاسم:

```
amine
yassine
mehdi
```

### Exercise 27

خرج غير الرقم الثاني:

```
42
25
30
```

### Exercise 28

خرج الاسم والرقم الثالث فقط:

```
amine 1337
yassine 42
mehdi 1337
```

### Exercise 29 ⭐

خرج غير الناس اللي عندهم:

```
1337
```

فالـcolumn الثالث.

---

# ⏱️ 1:50 → 2:00 — Final Challenge 🔥

دابا ممنوع تشوف solutions.

عندك هاد الملف:

```
cat > students.txt << EOF
yassine:42:1337
amine:25:42
mehdi:30:1337
sara:19:42
karim:35:1337
EOF
```

المطلوب:

### Challenge 1

خرج غير usernames.

Expected:

```
yassine
amine
mehdi
sara
karim
```

### Challenge 2

خرج usernames **مرتبين alphabetically**.

### Challenge 3

خرج غير الناس اللي عندهم `1337`.

### Challenge 4

خرج:

```
username age
```

مثلاً:

```
yassine 42
amine 25
...
```

### Challenge 5 🔥🔥

دير command واحد فيه **3 commands ولا أكثر مربوطين بـ `|`** باش تخرج usernames ديال الناس اللي عندهم `1337` **مرتبين alphabetically**.

---

## 🧠 القاعدة ديال هاد الساعتين

كلما شفتي exercise، سَوّل راسك:

```
واش خاصني نقلب؟       → find / grep
واش خاصني نعد؟        → wc
واش خاصني نخرج field؟ → cut / awk
واش خاصني نرتب؟       → sort
واش خاصني نبدل text؟  → tr / sed
واش خاصني ناخد lines؟ → head / tail
واش خاصني نربط commands؟ → |
واش خاصني نكتب output فـfile؟ → >
```

**ما تستعملش Google ولا تشوف solutions فهاد 2h.** حاول، حتى إلا غلطتي. الغلط هنا هو اللي غادي يخليك تفهم Shell مزيان.
chra7 chno lfar9 bin shell terminal tty cmd

أكيد. هادو 4 كلمات كيتخلطو بزاف: **Terminal, TTY, Shell, CMD**. نخليهم ليك من الصفر وبـ diagram.

# 🧠 الفكرة الكبيرة

ملي كتفتح Terminal وكتكتب:

```
ls
```

كاينين عدة طبقات خدامين مع بعضياتهم:

```
┌──────────────────────────────┐
│          Terminal            │
│  الواجهة اللي كتشوف وكتكتب   │
└──────────────┬───────────────┘
               ↓
┌──────────────────────────────┐
│             TTY              │
│   قناة/واجهة للتواصل         │
│   بين البرنامج والـ terminal  │
└──────────────┬───────────────┘
               ↓
┌──────────────────────────────┐
│            Shell             │
│  Bash / Zsh / Fish ...       │
│  كيفسر الأوامر ديالك         │
└──────────────┬───────────────┘
               ↓
┌──────────────────────────────┐
│            Linux             │
│        Kernel / OS           │
└──────────────────────────────┘
```

ودابا نفصلوهم.

---

# 1. Terminal 🖥️

**Terminal** هي الواجهة اللي كتستعمل باش تتفاعل مع النظام بالنصوص.

مثلاً عندك فـ Linux:

- XFCE Terminal
- GNOME Terminal
- Konsole

ملي كتفتح:

```
┌─────────────────────────┐
│ ahmed@MacBookPro:~$     │
│                         │
│                         │
└─────────────────────────┘
```

هاد النافذة هي **Terminal emulator**.

يعني هي بحال "الشاشة/الواجهة" اللي كتخليك تستعمل command line.

---

# 2. Shell 🐚

الـ **Shell** هو البرنامج اللي كيفهم الأوامر اللي كتكتب.

مثلاً:

```
ls
```

أنت كتكتبها فالـ Terminal.

ولكن اللي كيتعامل مع `ls` ويفسر syntax ديالك هو **Shell**.

أشهر Shells:

```
Bash
Zsh
Fish
Dash
Ksh
```

مثلاً عندك:

```
echo $SHELL
```

ممكن يعطيك:

```
/bin/bash
```

يعني الـ Shell الافتراضي ديالك هو Bash.

---

# 3. TTY 🖥️

هنا خاص شوية تركيز.

**TTY** جاية تاريخياً من:

> Teletypewriter

ولكن فـ Linux اليوم، TTY كتقدر تفهمها كـ **terminal interface/device/channel** كيتعامل مع input/output ديال النصوص.

مثلاً إلا ضغطتي:

```
Ctrl + Alt + F3
```

فـ Linux غالباً غادي تمشي لـ:

```
tty3
```

وغادي تلقى login بحال:

```
Linux Mint
login:
```

هاد الشي هو **Virtual Console / TTY**.

وتقدر تعرف الـ TTY اللي نتا فيه بـ:

```
tty
```

مثلاً:

```
/dev/pts/0
```

هنا `/dev/pts/0` هو pseudo-terminal.

---

# 4. علاش كنشوفو `/dev/pts/0`؟

إلى فتحت Terminal emulator، غالباً ماشي TTY حقيقي بحال `tty3`.

كيكون عندك:

```
Terminal Emulator
       ↓
Pseudo Terminal
       ↓
Shell
```

والـ pseudo-terminal كيتسمى غالباً:

```
PTY
```

والـ slave side ديالو كيكون مثلاً:

```
/dev/pts/0
```

لهذا ملي تدير:

```
tty
```

ممكن تشوف:

```
/dev/pts/0
```

---

# 5. CMD 🪟

هنا الفرق مهم.

**CMD** هو اختصار لـ:

> Command Prompt

وهو **command-line interpreter ديال Windows**.

يعني ماشي synonym ديال Terminal.

في Windows عندك مثلاً:

```
Windows Terminal
       ↓
      CMD
```

أو:

```
Windows Terminal
       ↓
    PowerShell
```

يعني:

**Windows Terminal** = الواجهة

**CMD** = shell/command interpreter

---

# 🔥 دابا الفرق كامل

|المصطلح|شنو هو؟|
|---|---|
|**Terminal**|الواجهة اللي كتكتب وتشوف فيها الأوامر|
|**Shell**|البرنامج اللي كيفسر الأوامر|
|**TTY**|terminal interface/device/session للتعامل مع النصوص|
|**CMD**|command interpreter ديال Windows|

---

## مثال من Linux ديالك

إلى فتحتي XFCE Terminal وكتبتي:

```
echo "Hello"
```

العملية تقريباً:

```
أنت
 │
 │ كتكتب echo "Hello"
 ↓
XFCE Terminal
 │
 │ input
 ↓
PTY / TTY
 │
 ↓
Bash
 │
 │ كيفسر الأمر
 ↓
Linux
 │
 ↓
output
 │
 ↓
Terminal
 │
 ↓
Hello
```

### أهم حاجة تحفظها:

```
Terminal ≠ Shell
Shell ≠ TTY
TTY ≠ CMD
```

وواحد التشبيه ساهل:

```
🚪 Terminal = الباب/الواجهة
🧠 Shell    = المترجم اللي كيفهم كلامك
📞 TTY      = وسيلة الاتصال
🪟 CMD      = واحد الـ command interpreter ديال Windows
```

**وبالنسبة ليك دابا:** بما أنك كتتعلم Linux، ركّز أكثر على **Terminal + Shell + TTY/PTY**، و`CMD` غير عرف الفرق ديالو مع Linux.

tty mafhamthach

آه، `TTY` هي اللي كتخلط 😄. نخليوها **بسيطة بزاف** وننسو التعريف التقني دابا.

### شوف هاد الصورة فدماغك:

ملي كتفتح Terminal وكتكتب:

```
ls
```

كاين واحد **المسار اللي كيدوز منو الكلام**:

```
أنت
 ↓
Terminal
 ↓
TTY / PTY
 ↓
Shell (Bash)
 ↓
Linux
```

يعني `TTY` ماشي هو `Shell` وماشي هو النافذة اللي كتشوف.

### TTY شنو هي إذن؟

فكّر فيها بحال **قناة اتصال** بينك وبين الـ Shell.

مثلاً:

```
أنت كتبتي: ls
       ↓
    Terminal
       ↓
   ┌─────────┐
   │   TTY   │  ← قناة الاتصال
   └─────────┘
       ↓
      Bash
       ↓
      ls
```

الـ TTY كتتعامل مع:

- شنو كتكتب ⌨️
- شنو كيخرج من البرنامج 🖥️

---

### جرب عندك هاد الأمر:

```
tty
```

غالباً غادي يعطيك:

```
/dev/pts/0
```

ما تخافش من `/dev/pts/0` 😄.

معناها ببساطة:

> **هاد الـ Terminal session اللي نتا خدام فيها عندها واحد الـ pseudo-terminal خاص بها.**

إلى فتحتي Terminal أخرى، ممكن تلقى:

```
Terminal 1 → /dev/pts/0
Terminal 2 → /dev/pts/1
Terminal 3 → /dev/pts/2
```

يعني كل Terminal session عندها **PTY** ديالها.

---

### وشنو الفرق بين TTY و PTY؟

هنا فقط خزن هاد الفكرة:

```
TTY
 ↓
الاسم العام/التاريخي للفكرة

PTY
 ↓
Pseudo-TTY
 ↓
TTY افتراضية
```

فـ Terminal emulator بحال XFCE Terminal، اللي كتستعمل غالباً هو **PTY**.

أما إلا دخلتي لـ Linux console بـ:

```
Ctrl + Alt + F3
```

غالباً غادي تكون فـ:

```
/dev/tty3
```

وهنا كتكون **TTY virtual console** حقيقية من ناحية Linux.

### 🧠 الخلاصة

ما تقولش:

> TTY = Terminal

قول:

> **TTY هي واجهة/قناة ديال input و output كتخلي الـ Shell والـ terminal يتواصلو.**

ودابا أهم حاجة: **ما تحتاجش تحفظ التفاصيل ديال TTY دابا**. فتعلم Linux، اللي خاصك تفهم هو أن `tty` command كيعطيك **شنو هو terminal/terminal session اللي نتا خدام فيها**.
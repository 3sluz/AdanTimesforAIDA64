<div align="center">

# 🕌 Adan External Data Bridge

### عرض أوقات الصلاة على سطح المكتب عبر AIDA64 و Rainmeter وأي أداة مراقبة

**Display prayer times on your desktop through AIDA64, Rainmeter, and any monitoring tool**

<div dir="rtl">

هذه الميزة مقدمة من تطبيق **[أذان — Adan](https://apps.microsoft.com/detail/9MXGH02LVJXX)** لأوقات الصلاة على ويندوز، من تطوير **[3sluz](https://github.com/3sluz)**.

</div>

*This feature is provided by the **[Adan](https://apps.microsoft.com/detail/9MXGH02LVJXX)** prayer times app for Windows, developed by **[3sluz](https://github.com/3sluz)**.*

[![Download Adan](https://img.shields.io/badge/⬇️_حمّل_أذان_|_Download_Adan-0078D6?style=for-the-badge&logo=microsoft)](https://apps.microsoft.com/detail/9MXGH02LVJXX)

[![Windows](https://img.shields.io/badge/Windows-10%2F11-0078D6?logo=windows)](https://apps.microsoft.com/detail/9MXGH02LVJXX)
[![AIDA64](https://img.shields.io/badge/AIDA64-Supported-orange)](https://www.aida64.com/)
[![Rainmeter](https://img.shields.io/badge/Rainmeter-Supported-green)](https://www.rainmeter.net/)
[![License](https://img.shields.io/badge/License-Proprietary-red)]()

</div>

---

## 📖 ما هي هذه الميزة؟ | What is this?

<div dir="rtl">

**جسر البيانات الخارجي** هو ميزة مدمجة في تطبيق **[أذان](https://apps.microsoft.com/detail/9MXGH02LVJXX)** (متوفر مجانًا على متجر مايكروسوفت). التطبيق يقوم بكتابة أوقات الصلاة والعد التنازلي والتاريخ الهجري تلقائيًا كل 60 ثانية، مما يتيح لبرامج مثل **AIDA64** أو **Rainmeter** قراءة هذه البيانات وعرضها على سطح المكتب أو على شاشات المراقبة.

**الفكرة ببساطة:** حمّل تطبيق أذان ← فعّل جسر البيانات من الإعدادات ← AIDA64 أو Rainmeter يعرض أوقات الصلاة على شاشتك.

⬇️ **[حمّل تطبيق أذان من متجر مايكروسوفت](https://apps.microsoft.com/detail/9MXGH02LVJXX)**

</div>

**External Data Bridge** is a feature built into the **[Adan](https://apps.microsoft.com/detail/9MXGH02LVJXX)** app (available for free on the Microsoft Store). The app automatically writes prayer times, countdown timers, and the Hijri date every 60 seconds, allowing tools like **AIDA64** or **Rainmeter** to read and display this data on your desktop or monitoring screens.

**The idea is simple:** Download the Adan app → Enable the Data Bridge in Settings → AIDA64 or Rainmeter displays prayer times on your screen.

⬇️ **[Download Adan from the Microsoft Store](https://apps.microsoft.com/detail/9MXGH02LVJXX)**

---

## 🏗️ كيف يعمل النظام؟ | How it works

<div dir="rtl">

تطبيق **أذان** يعمل في الخلفية ويقوم بتحديث أوقات الصلاة كل **60 ثانية** تلقائيًا. برنامج **AIDA64** أو **Rainmeter** يقرأ هذه البيانات ويعرضها على شاشتك أو على SensorPanel.

**كل شيء يحدث تلقائيًا** — فقط فعّل الميزة من الإعدادات وسيتولى التطبيق الباقي.

</div>

The **Adan** app runs in the background and automatically updates prayer times every **60 seconds**. **AIDA64** or **Rainmeter** reads this data and displays it on your screen or SensorPanel.

**Everything happens automatically** — just enable the feature in Settings and the app handles the rest.

---

## 📊 خريطة البيانات | Data Mapping

### مسار AIDA64 — `HKCU\Software\FinalWire\AIDA64\ImportValues`

<div dir="rtl">

#### ⚠️ حد AIDA64: 10 خانات فقط!

نظام **Import Values** في AIDA64 يدعم **10 خانات فقط** (`Str1` إلى `Str10`) — هذا حد ثابت من AIDA64 نفسها ولا يمكن زيادته. لذلك تطبيق أذان يستخدم **9 خانات** للبيانات المتغيرة ويترك خانة واحدة فارغة للمستقبل.

**لماذا لا تُرسل أسماء الصلوات في الخانات؟** لأن أسماء الصلوات (الفجر، الشروق، الظهر...) **ثابتة لا تتغير أبدًا** — إرسالها يعني إهدار خانات ثمينة من الـ 10 المتاحة فقط. بدلاً من ذلك، تقوم **أنت** بإضافة أسماء الصلوات كـ **Static Label** في SensorPanel وتتحكم بخطها ولونها وموقعها بحرية كاملة.

</div>

#### ⚠️ AIDA64 Limit: Only 10 slots!

AIDA64's **Import Values** system supports a **maximum of 10 string slots** (`Str1` to `Str10`) — this is a hard limit set by AIDA64 itself and cannot be increased. Adan uses **9 of these 10 slots** for dynamic data and reserves one for future use.

**Why aren't prayer names sent as slots?** Because prayer names (Fajr, Sunrise, Dhuhr...) **never change** — sending them would waste precious slots out of the only 10 available. Instead, **you** add prayer names as **Static Labels** in SensorPanel, giving you full control over their font, color, and position.

| Slot | البيانات / Data | مثال / Example |
|:----:|:---|:---|
| **Str1** | 🌅 وقت الفجر — Fajr Time | `06:22` |
| **Str2** | 🌄 وقت الشروق — Sunrise Time | `07:46` |
| **Str3** | ☀️ وقت الظهر — Dhuhr Time | `01:25` |
| **Str4** | 🌤️ وقت العصر — Asr Time | `04:30` |
| **Str5** | 🌅 وقت المغرب — Maghrib Time | `06:59` |
| **Str6** | 🌙 وقت العشاء — Isha Time | `08:19` |
| **Str7** | ⏳ متبقي/مضى على الصلاة — Until/Since Label | `متبقي على المغرب` |
| **Str8** | ⏱️ العد التنازلي/المنقضي — Countdown/Elapsed | `02:40:19` |
| **Str9** | 📅 التاريخ الهجري — Hijri Date | `1 رمضان 1447` |
| **Str10** | *(فارغة — محجوزة للمستقبل)* | — |

> 🎨 **نصيحة:** أضف **Static Label** بجانب كل قيمة واكتب فيها اسم الصلاة يدويًا (مثلاً "الفجر" بجانب Str1). هكذا تتحكم بالتصميم بالكامل ولا تهدر أي خانة.
>
> 🎨 **Tip:** Add a **Static Label** next to each value and type the prayer name manually (e.g., "Fajr" next to Str1). This gives you full design control without wasting any slots.

### سلوك Str7 و Str8 الذكي | Smart Str7 & Str8 Behavior

<div dir="rtl">

هاتان القيمتان تتبدلان ذكيًا بين وضعين:

</div>

```
⏰ عند دخول وقت الصلاة (لمدة 45 دقيقة):
   Str7 = "مضى على المغرب"     ← الوقت المنقضي
   Str8 = "00:12:30"           ← يعد تصاعديًا ⬆️

⏳ بعد 45 دقيقة (حتى الصلاة التالية):
   Str7 = "متبقي على العشاء"    ← العد التنازلي
   Str8 = "01:30:45"           ← يعد تنازليًا ⬇️
```

---

### مسار Rainmeter

<div dir="rtl">

إذا كنت تستخدم **Rainmeter** بدلاً من AIDA64، فالتطبيق يوفر أيضًا بيانات مفصلة تشمل:

- ✅ أوقات الصلوات الستة (الفجر، الشروق، الظهر، العصر، المغرب، العشاء)
- ✅ اسم الصلاة التالية ووقتها والوقت المتبقي لها
- ✅ اسم الصلاة الحالية والوقت المنقضي عليها
- ✅ التاريخ الهجري والميلادي
- ✅ وقت آخر تحديث

يمكنك قراءة هذه البيانات من داخل Rainmeter باستخدام وحدة **Registry** المدمجة فيه.

</div>

If you use **Rainmeter** instead of AIDA64, the app also provides detailed data including:

- ✅ All six prayer times (Fajr, Sunrise, Dhuhr, Asr, Maghrib, Isha)
- ✅ Next prayer name, time, and countdown
- ✅ Current prayer name and elapsed time
- ✅ Hijri and Gregorian dates
- ✅ Last update timestamp

You can read this data from within Rainmeter using its built-in **Registry** measure.

---

## 🚀 دليل الإعداد خطوة بخطوة | Step-by-Step Setup Guide

### الخطوة 1: تفعيل الميزة في تطبيق أذان

<div dir="rtl">

1. افتح تطبيق **أذان**
2. اذهب إلى **الإعدادات** ⚙️
3. مرر لأسفل حتى تجد قسم **جسر البيانات الخارجي**
4. فعّل زر **التفعيل** ✅
5. البيانات ستبدأ بالكتابة في السجل فورًا

</div>

1. Open the **Adan** app
2. Go to **Settings** ⚙️
3. Scroll down to the **External Data Bridge** section
4. Toggle the **Enable** switch ✅
5. Data will start writing to the registry immediately

---

### الخطوة 2: الإعداد مع AIDA64

#### الطريقة السريعة (موصى بها) — Quick Method (Recommended)

<div dir="rtl">

1. في إعدادات أذان، اضغط زر **حفظ قالب SensorPanel**
2. اختر مكان حفظ الملف (مثلاً سطح المكتب)
3. افتح **AIDA64**
4. اذهب إلى: `File → Preferences → Hardware Monitoring → SensorPanel`
5. اضغط **Import** واختر الملف المحفوظ
6. ستظهر جميع أوقات الصلاة جاهزة! 🎉

</div>

1. In Adan settings, press the **Export SensorPanel Template** button
2. Choose where to save the file (e.g., Desktop)
3. Open **AIDA64**
4. Go to: `File → Preferences → Hardware Monitoring → SensorPanel`
5. Click **Import** and select the saved file
6. All prayer times will appear ready to use! 🎉

#### الطريقة اليدوية — Manual Method

<div dir="rtl">

إذا كنت تفضل التحكم الكامل:

</div>

**Step A: Add the data values (from Import Values)**

1. Open **AIDA64** → `File → Preferences → Hardware Monitoring → SensorPanel`
2. Click **New** to add a sensor item
3. Find **Import Values** in the sensor list (under "Software Information")
4. Select the slot you want:
   - `SREGVALS1` = Fajr time
   - `SREGVALS2` = Sunrise time
   - `SREGVALS3` = Dhuhr time
   - `SREGVALS4` = Asr time
   - `SREGVALS5` = Maghrib time
   - `SREGVALS6` = Isha time
   - `SREGVALS7` = Dynamic label (until/since)
   - `SREGVALS8` = Countdown/elapsed time
   - `SREGVALS9` = Hijri date

**Step B: Add prayer name labels (Static Labels)**

<div dir="rtl">

⚠️ **مهم:** بما أن AIDA64 لا يدعم أكثر من 10 خانات Import Values، يجب عليك كتابة أسماء الصلوات يدويًا كـ **Label**:

</div>

> ⚠️ **Important:** Since AIDA64 only supports 10 Import Values slots, you must add prayer names manually as **Labels**:

5. Click **New** again → select **Label** (not Import Values)
6. In the **Text** field, type the prayer name (e.g., `الفجر` or `Fajr`)
7. Position it next to the corresponding time value (Str1)
8. Repeat for each prayer: الشروق، الظهر، العصر، المغرب، العشاء
9. Customize fonts, colors, and positions as you like

```
Example SensorPanel Layout:

  ┌──────────────────────────────────────┐
  │  الفجر        06:22    ← Label + Str1│
  │  الشروق       07:46    ← Label + Str2│
  │  الظهر        01:25    ← Label + Str3│
  │  العصر        04:30    ← Label + Str4│
  │  المغرب       06:59    ← Label + Str5│
  │  العشاء       08:19    ← Label + Str6│
  │                                      │
  │  متبقي على المغرب    02:40:19        │
  │       Str7              Str8         │
  │                                      │
  │  1 رمضان 1447                        │
  │       Str9                           │
  └──────────────────────────────────────┘
```

> 📍 In AIDA64, the sensor items are located at:
> `SensorPanel → New → Software Information → Import Values → SREGVALS1..9`

---

### الخطوة 3: الإعداد مع Rainmeter (اختياري)

<div dir="rtl">

1. افتح **Rainmeter** وأنشئ **Skin** جديد
2. استخدم وحدة **Registry** المدمجة في Rainmeter لقراءة بيانات أوقات الصلاة
3. صمم واجهتك كما تشاء — جميع البيانات متاحة ومحدثة تلقائيًا

</div>

1. Open **Rainmeter** and create a new **Skin**
2. Use Rainmeter's built-in **Registry** measure to read prayer time data
3. Design your skin as you like — all data is available and auto-updated

---

## 🔄 التحديث التلقائي | Auto-Update

<div dir="rtl">

- ⏱️ **التحديث كل 60 ثانية** — يكفي لعد تنازلي دقيق
- 🚀 **كتابة فورية عند التفعيل** — لا انتظار
- 🧹 **تنظيف عند الإيقاف** — القيم تتحول إلى `--:--` بدلاً من الحذف (لحماية تصميم SensorPanel)
- 🔋 **لا يؤثر على الأداء** — العملية خفيفة جدًا ولا تستهلك موارد الجهاز

</div>

- ⏱️ **Updates every 60 seconds** — accurate enough for a live countdown
- 🚀 **Writes immediately on enable** — no waiting
- 🧹 **Cleans up on disable** — values become `--:--` instead of being deleted (protects your SensorPanel layout)
- 🔋 **No performance impact** — the process is extremely lightweight

---

## ❓ الأسئلة الشائعة | FAQ

<details>
<summary><strong>🔸 هل يؤثر على أداء الجهاز؟</strong></summary>

لا. العملية خفيفة جدًا ولا تستهلك أي موارد ملحوظة من الجهاز.

**No.** The process is extremely lightweight and does not consume any noticeable system resources.

</details>

<details>
<summary><strong>🔸 هل يعمل مع تطبيقات أخرى غير AIDA64 و Rainmeter؟</strong></summary>

نعم! أي تطبيق مراقبة يستطيع قراءة بيانات من سجل ويندوز يمكنه استخدام هذه الميزة.

**Yes!** Any monitoring application that can read data from the Windows Registry can use this feature.

</details>

<details>
<summary><strong>🔸 ماذا يحدث عند إغلاق تطبيق أذان؟</strong></summary>

آخر البيانات المكتوبة تبقى محفوظة حتى يفتح التطبيق مرة أخرى ويحدّثها. إذا أوقفت الميزة، القيم تتحول إلى `--:--` لكن لا تُحذف — حتى لا يتأثر تصميم SensorPanel الخاص بك.

**The last written data stays** saved until the app opens again and updates it. If you disable the feature, values become `--:--` but aren't deleted — so your SensorPanel layout stays intact.

</details>

<details>
<summary><strong>🔸 هل يعمل مع نسخة المتجر (Microsoft Store)؟</strong></summary>

نعم! الميزة تعمل تلقائيًا سواء ثبّت التطبيق من المتجر أو بأي طريقة أخرى. لا يحتاج المستخدم لفعل أي شيء إضافي.

**Yes!** The feature works automatically whether you installed the app from the Store or any other way. No extra steps needed.

</details>

<details>
<summary><strong>🔸 Str10 فارغة — هل ستُستخدم لاحقًا؟</strong></summary>

نعم، **Str10 محجوزة للمستقبل**. يمكن استخدامها لإضافة بيانات إضافية مثل اسم المدينة أو وقت الإمساك في رمضان.

**Yes, Str10 is reserved for future use.** It could be used for additional data like city name or Imsak time during Ramadan.

</details>

---

## 🛡️ الأمان والخصوصية | Security & Privacy

<div dir="rtl">

- ✅ **لا يُرسل أي بيانات عبر الإنترنت** — كل شيء يعمل محليًا على جهازك
- ✅ **لا يقرأ بيانات المستخدم** — يكتب فقط أوقات الصلاة والتاريخ الهجري
- ✅ **لا يحتاج صلاحيات المسؤول** — يعمل بدون أي صلاحيات إضافية
- ✅ **يمكن إيقافه في أي وقت** — زر تشغيل/إيقاف بسيط في الإعدادات

</div>

- ✅ **No data sent over the internet** — everything works locally on your device
- ✅ **No user data read** — only writes prayer times and Hijri date
- ✅ **No administrator privileges needed** — works without any extra permissions
- ✅ **Can be disabled anytime** — simple toggle in Settings

---

## 🎨 شارك تصميمك! | Share Your Design!

<div dir="rtl">

### 💫 أنشأت واجهة جميلة؟ شاركها مع المجتمع بضغطة واحدة!

نريد أن نرى إبداعاتكم! إذا صممت **SensorPanel** أو **Rainmeter Skin** تعرض أوقات الصلاة بشكل جميل، شاركها معنا ليستفيد الجميع.

</div>

### 💫 Created a beautiful panel? Share it with one click!

We want to see your creativity! If you've designed a beautiful prayer times panel, share it with the community.

<div align="center">

### 👇 اضغط الزر لمشاركة تصميمك | Click the button to share your design 👇

[![Share Your Design](https://img.shields.io/badge/🎨_شارك_تصميمك_|_Share_Your_Design-brightgreen?style=for-the-badge&logo=github)](https://github.com/3sluz/AdanTimesforAIDA64/issues/new?template=share-design.yml)

</div>

<div dir="rtl">

**ماذا سيحدث عند الضغط؟**
1. سيُفتح نموذج جاهز على GitHub
2. اكتب اسم تصميمك
3. اختر الأداة (AIDA64 أو Rainmeter)
4. **اسحب وأفلت** صورة التصميم في المكان المخصص
5. **اضغط الملف كـ ZIP** (بزر الفأرة الأيمن → إرسال إلى → مجلد مضغوط) ثم **اسحب وأفلت** ملف الـ ZIP
6. اضغط **Submit** — وانتهى! ✅

**كيف تصدّر ملف التصميم؟**
- **AIDA64:** اذهب إلى `SensorPanel → Export` واحفظ الملف → اضغطه كـ ZIP
- **Rainmeter:** اضغط بزر الفأرة الأيمن على الـ Skin → `Export` واحفظ الملف → اضغطه كـ ZIP

> ⚠️ **ملاحظة:** GitHub لا يدعم رفع ملفات `.sensorpanel` أو `.rmskin` مباشرة، لذلك يجب ضغطها كـ **ZIP** أولاً.

</div>

**What happens when you click?**
1. A ready-made form opens on GitHub
2. Type your design name
3. Choose the tool (AIDA64 or Rainmeter)
4. **Drag & drop** your design screenshot into the designated area
5. **ZIP the file first** (Right-click → Send to → Compressed folder) then **drag & drop** the ZIP file
6. Click **Submit** — and you're done! ✅

**How to export your design file?**
- **AIDA64:** Go to `SensorPanel → Export` and save the file → ZIP it
- **Rainmeter:** Right-click your Skin → `Export` and save the file → ZIP it

> ⚠️ **Note:** GitHub doesn't support uploading `.sensorpanel` or `.rmskin` files directly, so you must compress them as **ZIP** first.

> ✅ **سيتم مراجعة تصميمك من قبل الفريق قبل إضافته للصفحة الرئيسية. شكرًا لصبرك!**
>
> ✅ **Your design will be reviewed by the team before being featured on the main page. Thanks for your patience!**

> 🌟 **الفكرة:** نبني مكتبة من التصاميم الجاهزة — أي مستخدم جديد يمكنه تحميل تصميمك واستخدامه مباشرة!
>
> 🌟 **The idea:** We're building a library of ready-made designs — any new user can download your design and use it instantly!

### 🏆 تصاميم مميزة | Featured Designs

<div dir="rtl">

*كن أول من يشارك تصميمه! 🎉*

</div>

| التصميم / Design | المصمم / Author | الأداة / Tool | رابط / Link |
|:---|:---|:---|:---|
| *Be the first to share!* | — | — | — |

---

<div align="center">

**Made with ❤️ by [3sluz](https://github.com/3sluz)**

*Part of the [Adan](https://github.com/3sluz) prayer times application for Windows*

</div>

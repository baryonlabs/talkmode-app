<div align="center">

# TalkMode

**جهاز Mac mini يتحوّل إلى مساعد حقيقي — صوت كوري فوري، على الجهاز، وفق شروطك.**
**حوّل جهاز Mac mini إلى مساعد حقيقي. ردود صوتية فورية، كل شيء على الجهاز، وبالقواعد التي تحدّدها أنت.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | العربية | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> المستودع العام لـ TalkMode — الكود المصدري و**الإصدارات** و**المشكلات** و**النقاشات**.
> راجع **[SECURITY.md](../SECURITY.md)** لمعرفة الطريقة الدقيقة التي يتعامل بها التطبيق مع بياناتك.

---

## ما هو TalkMode

يحوّل TalkMode جهاز Mac mini (أو أي جهاز Mac يعمل بمعالج Apple silicon) إلى **مساعد صوتي كوري يعمل في الزمن الحقيقي** يتصرّف مثل زميل عمل، لا مثل روبوت دردشة.

- **تبادل الأدوار في أقل من ثانية** بفضل محدّد نقاط النهاية التكيّفي المضبوط للغة الكورية (النظرة + الصوت + النص)
- **تكلّم لتقاطع، أو أشِح بنظرك لتُنهي** — إشارات متعددة الوسائط، وليس مجرد مؤقّتات صمت
- **4 أوضاع**: المحادثة · محضر الاجتماع · العصف الذهني (مع التركيز على التجاوب) · الاستشارة النفسية (مع التركيز على الإصغاء)
- **تمييز المتحدثين على الجهاز** لمحاضر الاجتماعات (Apple Accelerate vDSP)
- **مهارات**: قراءة التقويم، صياغة البريد، قراءة الرسائل النصية، الاستعلام عن استخدام CPU/RAM، حفظ الذاكرة، تعلّم الأسماء البديلة
- **8 مزوّدي LLM**: أدوات سطر الأوامر Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 لغة للواجهة**، وأكثر من 50 لغة محلية لتحويل الكلام إلى نص
- **شخصيات**: ملفات Soul + Contract، لكل لغة، بالإضافة إلى مجموعة منتقاة من NVIDIA Nemotron-Personas-Korea
- **صور رمزية مخصّصة** عبر DiceBear (10 أنماط)، أو ImagePlayground (macOS 15.1+)، أو صورتك الخاصة
- **الخصوصية افتراضيًا**: لا شيء يغادر جهاز Mac الخاص بك سوى (أ) مزوّد LLM الذي اخترته و(ب) تشخيصات مجهّلة الهوية تُختزل فيها كل النصوص الحرة إلى قيم طول

---

## لقطات الشاشة

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="تبويب المحادثة — الرئيسي" /></a><br/>
      <sub><b>تبويب المحادثة</b> — صورة المساعد الرمزية، ومعاينة كاميرا اختيارية لتتبّع النظرة، وطبقة مستوى الميكروفون، ودردشة حيّة. تُظهر رقاقة «الأحدث» البرتقالية المزاج النشط.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="تبويب المحادثة — محادثة جارية" /></a><br/>
      <sub><b>محادثة حيّة</b> — يُعرَض markdown داخل الفقاعات، ويضيف STT علامات الترقيم تلقائيًا، وتظهر شارة «تنبيه المغادرة» عند تجهيز مهارة.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="الإعدادات — شخصية المساعد" /></a><br/>
      <sub><b>الإعدادات — الشخصية</b> — لغة الواجهة / STT، ونمط الصورة الرمزية وجنسها، والتوليد عبر ImagePlayground، وعقد <code>soul.md</code> الحيّ الذي يؤطّر كل رد.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="التشخيص — الخط الزمني" /></a><br/>
      <sub><b>التشخيص</b> — المرحلة، وانحراف/ميل الرأس، والنظرة، وقراءات STT/الوجه/CPU، وخط زمني متجدّد لكل قرار تحديد نقطة نهاية. أوقِف الخط الزمني لتوفير نسبة قليلة من المعالج.</sub>
    </td>
  </tr>
</table>

---

## اللغات المدعومة

يفصل TalkMode بين **لغة الواجهة** (لغة القوائم والأزرار ورسائل الخطأ) و**لغة الكلام** (اللغة التي يفرّغ بها المساعد الكلام ويردّ بها). يمكن ضبطهما بشكل مستقل — اقرأ الواجهة بالألمانية وتحدّث مع المساعد بالكورية.

### لغات الواجهة (20)

تُضبط في **الإعدادات → اللغة → لغة الواجهة**. كل لغة مترجمة بالكامل — جميع القوائم والأزرار والإعدادات وأوصاف المهارات وتسميات التشخيص.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### لغات الكلام / المحادثة

كل ما يدعمه إطار عمل Speech في جهاز Mac الخاص بك — عادةً **50–60 لغة محلية** على macOS Sonoma+. تُضبط في **الإعدادات → اللغة → لغة التعرّف على الكلام**؛ يسرد المنتقي كل لغة محلية يُرجعها `SFSpeechRecognizer.supportedLocales()` مع تثبيت اللغات المحلية الأربع لشرق آسيا والإنجليزية في الأعلى.

متوفّرة دائمًا على تثبيت macOS Sonoma+ القياسي (قائمة جزئية — قد يحتوي جهاز Mac الخاص بك على المزيد):

| المنطقة | اللغات المحلية |
|---|---|
| **شرق آسيا** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **الإنجليزية** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **أوروبا الغربية** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **وسط / شرق أوروبا** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **اليونانية / العبرية** | Ελληνικά · עברית |
| **الشرق الأوسط وجنوب آسيا** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **جنوب شرق آسيا** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **أخرى** | Türkçe · Русский · Català · Қазақ |

> تعتمد المجموعة الدقيقة على إصدار نظام التشغيل ولغات الإملاء التي نزّلتها ضمن **إعدادات النظام → لوحة المفاتيح → الإملاء**. يقرأ TalkMode القائمة الحيّة عند الإطلاق — افتح المنتقي على جهاز Mac الخاص بك للحصول على الجرد الموثوق.

### أصوات تحويل النص إلى كلام

يستخدم *إخراج* الكلام `AVSpeechSynthesizer` — المحرّك نفسه المستخدَم في Siri / الإملاء على macOS. تُنزَّل الأصوات ضمن **إعدادات النظام → إمكانية الوصول → المحتوى المنطوق → صوت النظام → إدارة الأصوات**. الكورية: Yuna / Sora؛ الإنجليزية: Samantha / Alex / Daniel / Karen / Moira؛ اليابانية: Kyoko / O-Ren؛ الصينية: Mei-Jia / Tian-Tian؛ وغيرها. الأصوات المميّزة (Yuna Premium وغيرها) أعلى جودة لكنها تحتاج إلى شبكة للجزء الأول.

---

> 🆕 **Latest features and install guide are in هذه الترجمة.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## التثبيت

### Homebrew (مُوصى به)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### التنزيل المباشر

[أحدث إصدار](https://talkmode.baryon.ai/download/TalkMode-0.4.28.zip) ← فُكّ الضغط ← اسحبه إلى `Applications` ← عند الإطلاق الأول قد يقول macOS «من مطوّر غير معروف»، انقر بالزر الأيمن ← فتح مرّة واحدة.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.28.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### التحديث التلقائي

Sparkle 2 مدمج. بعد التثبيت (بأي طريقة)، يتحقّق TalkMode من التحديثات في الخلفية — افتح `TalkMode → التحقق من التحديثات…` أو `الإعدادات → التحديث` للتحكّم به.

### المتطلّبات

- macOS **Sonoma (14.0)** أو أحدث
- Apple silicon (M1 / M2 / M3 / M4)
- مزوّد LLM — على الأقل Claude CLI أو Codex CLI أو مفتاح OpenAI

---

## الأذونات

تُطلب الأذونات **فقط في المرة الأولى التي تستخدم فيها الميزة**:

| الميزة | الإذن |
|---|---|
| الإصغاء الدائم | الميكروفون، التعرّف على الكلام |
| تتبّع النظرة (اختياري) | الكاميرا |
| مفتاح Option الأيمن لكتم TTS | مراقبة الإدخال |
| مهارات التقويم | التقويمات (وصول كامل) |
| مُنشئ البريد الإلكتروني | Apple Events |
| مهارة `messages.list_recent` | الوصول الكامل للقرص (امنحه يدويًا في إعدادات النظام) |

لا يُرفع أي شيء — يعمل STT على الجهاز (أو على خادم STT من Apple حسب لغتك المحلية)، والصور الرمزية ملفات PNG محلية، ويبقى صوت محاضر الاجتماعات في `~/.talk_mode_mac/recordings/`.

---

## الأمان والخصوصية

ما يحتفظ به TalkMode على جهاز Mac الخاص بك، وما يغادره وإلى أين، وما يُخزَّن على القرص، وكيف تُعالَج مفاتيح API والأذونات — إلى جانب مراجعة أمنية على مستوى الكود ونتائجها (لا توجد ثغرة قابلة للاستغلال عن بُعد؛ القيود الحالية مكشوفة بشفافية) — موثّق في **[SECURITY.md](../SECURITY.md)**.

---

## بُني باستخدام

TalkMode تطبيق macOS يعتمد على SwiftPM. حزمتان من Swift من جهة خارجية، والباقي أُطر عمل من Apple.

### حزم Swift

| الحزمة | الإصدار | ما تقوم به هنا | لماذا |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | تحديث تلقائي داخل التطبيق عبر appcast موقّع | معيار منصّة Apple؛ تستخدمه 1Password وTower وOBS. تحديثات موقّعة بـ EdDSA، وتنزيل في الخلفية، وعنصر قائمة «التحقق من التحديثات…». |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | تشخيصات مجهّلة الهوية بموافقة المستخدم (سجلّات بأسلوب OpenTelemetry) | تتيح لنا رؤية *أي* انتقالات مراحل تتعثّر في الواقع دون رؤية نص المستخدم أبدًا — تُختزل كل الحقول الحرة إلى قيم طول قبل الإرسال. |

### أُطر عمل Apple

| الإطار | يُستخدم لـ |
|---|---|
| **AVFoundation** | إدخال `AVAudioEngine` بنقطة استماع واحدة، وتحويل النص إلى كلام عبر `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice)، وكاميرا `AVCaptureSession` |
| **Speech** | STF متدفّق عبر `SpeechAnalyzer` (macOS 26) أو `SFSpeechRecognizer` مع `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` لوضعية الرأس ← تقدير النظرة (مقيّد إلى نحو 10 إطارات/ثانية) |
| **Accelerate (vDSP)** | تحويل فورييه بـ 1024 نقطة + نافذة Hann + تضمين طيفي لوغاريتمي مُسوّى بـ L2 لتمييز المتحدثين على الجهاز |
| **EventKit** | مهارات قراءة / إنشاء / تحديث / حذف التقويم (نطاق وصول كامل) |
| **ImagePlayground** | توليد الصور الرمزية على macOS 15.1+ (يرجع إلى DiceBear PNG عبر URLSession في غير ذلك) |
| **CoreImage / CoreVideo** | تحويل إطارات الكاميرا لإدخالها في Vision |
| **AppKit + SwiftUI** | نافذة الإعدادات، والتخطيط متعدّد التبويبات، وعرض السجلّ داخل التطبيق |
| **Combine** | نشر حالة `@Published` من `ConversationEngine` إلى كل الواجهة |
| **OSLog** | تشخيصات السجلّ الموحّد (`subsystem=app.talkmode`) |
| **SQLite3** | مخزن الأسماء البديلة المحلي + ذاكرة المهارات |
| **UniformTypeIdentifiers** | منتقي ملفات الصورة الرمزية |

### أصول من جهة خارجية (غير برمجية)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 شخصيات منتقاة لكل وضع (이수민·정아람·박도윤·강예린). يمكن للمستخدمين تجاوزها بـ `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 أنماط للصور الرمزية تُجلب كملفات PNG وتُخزَّن محليًا.

---

## الخلفية التقنية

بعض الخيارات التصميمية التي لا تتّضح من لقطات الشاشة:

### تحديد نقطة النهاية متعدّد الوسائط — لماذا ينتهي دورك بسرعة لكن ليس بسرعة مفرطة

تقطع المساعدات الصوتية القياسية للغات شرق آسيا حديثك إمّا عند أول «ممم…» أو تنتظر 3 ثوانٍ بعد أن تنتهي فعليًا. يقرأ `AdaptiveTurnDetector` في TalkMode أربع إشارات في آنٍ واحد:

1. **النشاط الصوتي** (EnergyVAD على الميكروفون) — تراكم عيّنات الصمت يُكوّن رصيدًا
2. **النص المتدفّق** (SpeechAnalyzer / SFSpeechRecognizer) — لواحق الربط الكورية (`-고`، `-는데`) تضيف 1.2 ثانية؛ لواحق الإنهاء (`-습니다`، `-요`) تطرح 400 مللي ثانية؛ علامات التردّد (`음…`، `어…`) تضيف 1.5 ثانية
3. **معدّل الكلام** (أحرف / ثانية) — يحصل المتحدّثون السريعون على رصيد توقّف أصغر
4. **حالة النظرة** (انحراف / ميل الرأس عبر Vision) — النظر إلى الشاشة يضرب التوقّف في 0.3–0.65 (انتظار)، وإشاحة النظر بعد جملة مكتملة تضرب في 1.4 *وتُسلّح* إطلاقًا سريعًا فوريًا (لقد انتهيت)

تتغذّى الإشارات الأربع كلها في دالة واحدة `predictedSilenceMs()`، مقيّدة بحدّ أدنى لكل لغة (شرق آسيا 900–7000 مللي ثانية، الإنجليزية 300–3000 مللي ثانية). لا مؤقّتات متوازية، ولا حالات تسابق.

### الصوت الدائم التشغيل هو ركيزة أساسية

يبدأ `AudioInputStream` تشغيل `AVAudioEngine` **مرة واحدة لكل جلسة ولا يوقفه أبدًا** حتى انتهاء الجلسة. كان الكود السابق يوقفه/يعيد تشغيله عند كل حدّ مرحلة؛ وراكم ذلك النمط أخطاءً على macOS 26 (`couldn't get default input device, ID = 0`، وحالات إجهاض `format.sampleRate == inputHWFormat.sampleRate`). الآن تبثّ نقطة استماع واحدة المخازن المؤقتة إلى N من المستهلكين (VAD، STT، كاشف المقاطعة، مسجّل الاجتماعات، مقياس المستوى) عبر `AsyncStream`.

### تمييز المتحدثين على الجهاز

يستخدم وضع محضر الاجتماع Apple Accelerate vDSP لحساب **تضمين طيفي لوغاريتمي مُسوّى بـ L2 بـ 24 بُعدًا** (FFT 1024، نافذة Hann، قفزة 256) لكل نطق. تشابه جيب التمام > 0.82 = المتحدّث نفسه السابق، وإلا يُسنَد معرّف جديد. لا تنزيل لنموذج، ولا استدعاء API. يستمرّ المتحدثون عبر الاجتماعات — أعِد تسمية «المتحدّث 1» ← «지원» مرة واحدة، فيثبت ذلك.

### LLM يعمل بمبدأ BYOK

`AssistantClient` بروتوكول واحد بثماني تطبيقات. يُطلق مزوّدو CLI (`CLIAssistantClient` لـ `claude` و`codex` و`gemini` و`cursor-agent` و`kimi` و`opencode`) عملية فرعية في `~/.talk_mode_mac/work/` بـ `currentDirectoryURL` معزول، ويبثّون stdout جملةً جملةً إلى `TTSQueue`، ولا يرون أبدًا مفتاح API من TalkMode نفسه. أنت تأتي بأي اشتراك تدفع ثمنه بالفعل.

### تشخيصات الخصوصية افتراضيًا

تُمرّر قياسات PostHog عن بُعد (بموافقة المستخدم) **أحداثًا مصنّفة فقط**، لا النص الأساسي:

- `turn / llm / tts / minutes / alias` ← تُختزل إلى `[category] len=N` قبل الإرسال
- `skill` ← يحتفظ بـ `skill_id`، ويُسقط `args`
- `fsm / endpointing / session / error / update` ← بيانات وصفية فقط، بلا نص مفرّغ

تحقّق في `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (مرئي في سلاسل الملف الثنائي إذا لم تثق بي).

### تجريد Markdown لتحويل النص إلى كلام، وعرضه للدردشة

تحبّ نماذج LLM `**العريض**` و`### العناوين`. يقرأها AVSpeechSynthesizer كـ «نجمة نجمة عريض نجمة نجمة». تُنظّف `MarkdownStripper.strip(_:)` النص مباشرةً قبل دخوله `TTSQueue` (تحتفظ فقاعة الدردشة بالأصل عبر `AttributedString(markdown:)`).

### تقسيم SwiftPM المعياري

يعيش هدفان قابلان لإعادة الاستخدام إلى جانب التطبيق الرئيسي:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — دالة `timeout(for:localeID:)` المعتمدة على Foundation فقط مع 14 اختبار وحدة. مُضاعِف `ثانية/حرف × 4` لكل لغة مع حدّ أدنى؛ لا يمكن أن يتراجع بصمت بسبب التزام غير ذي صلة.
- **`Endpointing`** (`Sources/Endpointing/`) — يملك `AdaptiveTurnDetector` و`VoiceActivity` و`GazeState`. لا اعتماد على AVFoundation / Vision. 7 اختبارات وحدة تغطّي تسليم الدور بإشاحة النظر، ورفض الميكروفون النشط، ومسح المزلاج.

يعمل كلٌّ من `swift test --filter EndpointingTests` و`swift test --filter SpeechWatchdogTests` على وحدة صغيرة جدًا — تكرار سريع.

### آلة الحالة

يمرّ كل انتقال مرحلة (`idle → listening → thinking → speaking → listening …`) عبر `PhaseStateMachine.transition(to:reason:)` واحد. تُرفَض الانتقالات غير المشروعة مع سبب مُسجَّل. يظهر ذلك في الخط الزمني لتبويب التشخيص، فعندما يتعثّر شيء ما يمكنك رؤية *أي* حافة رفضت الانطلاق.

---

## المجتمع

- **Discussions** — أسئلة وأفكار وطلبات ميزات → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — تقارير الأخطاء → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## الترخيص

التطبيق المُجمَّع مجاني للاستخدام، شخصيًا أو تجاريًا — تحتوي ملفات ZIP للإصدارات على حزمة `.app` موقّعة واحدة.

الكود المصدري في هذا المستودع مرخّص بموجب **رخصة GNU Affero العمومية العامة الإصدار 3.0** — راجع [LICENSE](../LICENSE). يمكنك استخدامه ودراسته وتعديله وإعادة توزيعه، لكن أي نسخة معدّلة — بما في ذلك تلك المقدَّمة كخدمة شبكية — يجب أن تبقى مفتوحة بموجب الرخصة نفسها AGPL-3.0. تملك Baryon Labs حقوق النشر؛ إذا كنت بحاجة إلى شروط خارج AGPL-3.0 (مثل ترخيص تجاري)، فاسأل عبر **Discussions**.

صُنع في سيول بواسطة [Baryon Labs](https://baryon.ai).

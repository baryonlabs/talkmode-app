<div align="center">

# TalkMode

**Mac mini एक असली सहायक में बदल जाता है — तत्काल कोरियाई आवाज़, डिवाइस पर ही, आपकी शर्तों पर।**
**Mac mini को एक असली सहायक बनाइए। तत्काल आवाज़ी जवाब, सब कुछ on-device, और आपके तय किए नियमों के अनुसार।**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | हिन्दी | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> TalkMode के लिए सार्वजनिक रिपॉज़िटरी — सोर्स, **Releases**, **Issues** और **Discussions**।
> ऐप आपके डेटा को ठीक किस तरह संभालता है, यह जानने के लिए **[SECURITY.md](../SECURITY.md)** देखें।

---

## TalkMode क्या है

TalkMode एक Mac mini (या किसी भी Apple-silicon Mac) को एक **रियल-टाइम कोरियाई आवाज़ सहायक** में बदल देता है, जो किसी चैटबॉट की तरह नहीं बल्कि एक सहकर्मी की तरह बर्ताव करता है।

- कोरियाई के लिए ट्यून किए गए अनुकूली एंडपॉइंटर (नज़र + आवाज़ + ट्रांसक्रिप्ट) के साथ **एक सेकंड से कम में बारी का आदान-प्रदान**
- **बीच में बोलकर रोकें, या नज़र हटाकर बात समेटें** — सिर्फ़ खामोशी के टाइमर नहीं, बल्कि बहु-माध्यमिक संकेत
- **4 मोड**: बातचीत · मीटिंग के मिनट · विचार-मंथन (हुंकार पर केंद्रित) · मनोवैज्ञानिक परामर्श (ध्यान से सुनने पर केंद्रित)
- मीटिंग मिनट के लिए **डिवाइस पर स्पीकर डायराइज़ेशन** (Apple Accelerate vDSP)
- **स्किल्स**: कैलेंडर पढ़ना, मेल का मसौदा बनाना, SMS पढ़ना, CPU/RAM उपयोग की जानकारी लेना, मेमोरी सहेजना, उपनाम सीखना
- **8 LLM प्रदाता**: Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLI + OpenAI + Mock
- **20 UI भाषाएँ**, 50+ STT लोकेल
- **पर्सोना**: हर भाषा के लिए Soul + Contract फ़ाइलें, साथ ही NVIDIA Nemotron-Personas-Korea से चुना गया एक सेट
- DiceBear (10 शैलियाँ), ImagePlayground (macOS 15.1+), या आपकी अपनी छवि के ज़रिए **कस्टम अवतार**
- **डिफ़ॉल्ट रूप से गोपनीयता**: आपके Mac से कुछ भी बाहर नहीं जाता, सिवाय (a) आपके चुने हुए LLM प्रदाता और (b) गुमनाम किए गए डायग्नोस्टिक्स के, जिनमें सारा मुक्त-पाठ लंबाई के मानों में बदल दिया जाता है

---

## स्क्रीनशॉट

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="बातचीत टैब — मुख्य" /></a><br/>
      <sub><b>बातचीत टैब</b> — सहायक का अवतार, नज़र के लिए वैकल्पिक कैमरा प्रीव्यू, माइक स्तर का ओवरले, और लाइव चैट। नारंगी "हाल का" चिप सक्रिय मूड दिखाता है।</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="बातचीत टैब — बातचीत जारी" /></a><br/>
      <sub><b>लाइव बातचीत</b> — बबल में markdown रेंडर होता है, STT स्वतः विराम-चिह्न लगाता है, और कोई स्किल तैयार होने पर "प्रस्थान सूचना" बैज दिखता है।</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="सेटिंग्स — सहायक का व्यक्तित्व" /></a><br/>
      <sub><b>सेटिंग्स — पर्सोना</b> — UI / STT भाषा, अवतार शैली और लिंग, ImagePlayground से जनरेशन, और लाइव <code>soul.md</code> कॉन्ट्रैक्ट जो हर जवाब को ढाँचा देता है।</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="डायग्नोस्टिक्स — टाइमलाइन" /></a><br/>
      <sub><b>डायग्नोस्टिक्स</b> — फ़ेज़, yaw/pitch, नज़र, STT/चेहरा/CPU रीडआउट, और हर एंडपॉइंटिंग निर्णय की चलती टाइमलाइन। थोड़ा CPU बचाने के लिए टाइमलाइन बंद कर दें।</sub>
    </td>
  </tr>
</table>

---

## समर्थित भाषाएँ

TalkMode **UI भाषा** (मेन्यू, बटन और त्रुटि संदेश किस भाषा में हैं) को **वाक् भाषा** (सहायक किस भाषा में लिप्यंतरण और जवाब देता है) से अलग रखता है। इन्हें स्वतंत्र रूप से सेट किया जा सकता है — UI जर्मन में पढ़ें, सहायक से कोरियाई में बात करें।

### UI भाषाएँ (20)

**सेटिंग्स → भाषा → UI भाषा** में सेट करें। हर भाषा पूरी तरह अनूदित है — सभी मेन्यू, बटन, सेटिंग्स, स्किल विवरण और डायग्नोस्टिक्स लेबल।

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### वाक् / बातचीत की भाषाएँ

जो भी आपके Mac का Speech फ़्रेमवर्क समर्थन करता है — आमतौर पर macOS Sonoma+ पर **50-60 लोकेल**। **सेटिंग्स → भाषा → वाक् पहचान भाषा** में सेट करें; पिकर `SFSpeechRecognizer.supportedLocales()` से लौटाए गए हर लोकेल को सूचीबद्ध करता है, जिसमें चार CJK और अंग्रेज़ी लोकेल सबसे ऊपर पिन रहते हैं।

एक स्टॉक macOS Sonoma+ इंस्टॉल पर हमेशा उपलब्ध (आंशिक सूची — आपके Mac में और भी हो सकते हैं):

| क्षेत्र | लोकेल |
|---|---|
| **पूर्वी एशिया** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **अंग्रेज़ी** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **पश्चिमी यूरोप** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **मध्य / पूर्वी यूरोप** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **यूनानी / हिब्रू** | Ελληνικά · עברית |
| **मध्य पूर्व और दक्षिण एशिया** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **दक्षिण-पूर्व एशिया** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **अन्य** | Türkçe · Русский · Català · Қазақ |

> सटीक सेट OS संस्करण और उन डिक्टेशन भाषाओं पर निर्भर करता है जिन्हें आपने **सिस्टम सेटिंग्स → कीबोर्ड → डिक्टेशन** में डाउनलोड किया है। TalkMode लॉन्च के समय लाइव सूची पढ़ता है — आधिकारिक सूची के लिए अपने Mac पर पिकर खोलें।

### TTS आवाज़ें

वाक् *आउटपुट* `AVSpeechSynthesizer` का उपयोग करता है — वही इंजन जो macOS Siri / डिक्टेशन में है। आवाज़ें **सिस्टम सेटिंग्स → सुलभता → बोली गई सामग्री → सिस्टम वॉइस → आवाज़ें प्रबंधित करें** में डाउनलोड होती हैं। कोरियाई: Yuna / Sora; अंग्रेज़ी: Samantha / Alex / Daniel / Karen / Moira; जापानी: Kyoko / O-Ren; चीनी: Mei-Jia / Tian-Tian; आदि। प्रीमियम आवाज़ें (Yuna Premium आदि) उच्च गुणवत्ता की हैं लेकिन पहले हिस्से के लिए नेटवर्क की ज़रूरत होती है।

---

## इंस्टॉल

### Homebrew (अनुशंसित)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### सीधा डाउनलोड

[नवीनतम रिलीज़](https://talkmode.baryon.ai/download/TalkMode-0.4.13.zip) → अनज़िप करें → `Applications` में खींचें → पहले लॉन्च पर macOS कह सकता है "अज्ञात डेवलपर से", राइट-क्लिक करें → एक बार Open करें।

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.13.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### स्वतः-अपडेट

Sparkle 2 अंतर्निहित है। इंस्टॉल होने के बाद (किसी भी तरीके से), TalkMode पृष्ठभूमि में अपडेट जाँचता है — इसे नियंत्रित करने के लिए `TalkMode → Check for Updates…` या `सेटिंग्स → अपडेट` खोलें।

### आवश्यकताएँ

- macOS **Sonoma (14.0)** या उसके बाद का
- Apple silicon (M1 / M2 / M3 / M4)
- एक LLM प्रदाता — कम से कम Claude CLI, Codex CLI, या एक OpenAI कुंजी

---

## अनुमतियाँ

अनुमतियाँ **केवल पहली बार उस सुविधा का उपयोग करते समय** माँगी जाती हैं:

| सुविधा | अनुमति |
|---|---|
| हमेशा-चालू श्रवण | माइक्रोफ़ोन, वाक् पहचान |
| नज़र ट्रैकिंग (वैकल्पिक) | कैमरा |
| TTS शांत करने हेतु राइट-Option | इनपुट मॉनिटरिंग |
| कैलेंडर स्किल्स | कैलेंडर (पूर्ण पहुँच) |
| ईमेल कंपोज़र | Apple Events |
| `messages.list_recent` स्किल | पूर्ण डिस्क पहुँच (सिस्टम सेटिंग्स में मैन्युअल रूप से दें) |

कुछ भी अपलोड नहीं होता — STT डिवाइस पर चलता है (या आपके लोकेल के आधार पर Apple के STT सर्वर पर), अवतार स्थानीय PNG हैं, और मीटिंग मिनट का ऑडियो `~/.talk_mode_mac/recordings/` में रहता है।

---

## सुरक्षा और गोपनीयता

TalkMode आपके Mac पर क्या रखता है, क्या बाहर जाता है और कहाँ, डिस्क पर क्या संग्रहीत होता है, और API कुंजियाँ व अनुमतियाँ कैसे संभाली जाती हैं — साथ ही एक कोड-स्तरीय सुरक्षा समीक्षा और उसके निष्कर्ष (कोई दूरस्थ रूप से शोषण योग्य भेद्यता नहीं; मौजूदा सीमाएँ पारदर्शिता से प्रकट) — सब **[SECURITY.md](../SECURITY.md)** में प्रलेखित है।

---

## किससे बना है

TalkMode एक SwiftPM-आधारित macOS ऐप है। दो तृतीय-पक्ष Swift पैकेज, बाकी सब Apple फ़्रेमवर्क।

### Swift पैकेज

| पैकेज | संस्करण | यहाँ क्या करता है | क्यों |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | हस्ताक्षरित appcast के ज़रिए ऐप-में स्वतः-अपडेट | Apple-प्लेटफ़ॉर्म मानक; 1Password, Tower, OBS द्वारा उपयोग। EdDSA-हस्ताक्षरित अपडेट, पृष्ठभूमि डाउनलोड, "Check for Updates…" मेन्यू आइटम। |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | वैकल्पिक गुमनाम डायग्नोस्टिक्स (OpenTelemetry-शैली लॉग) | हमें वास्तविक उपयोग में देखने देता है कि *कौन-से* फ़ेज़ ट्रांज़िशन अटक रहे हैं, बिना कभी उपयोगकर्ता का पाठ देखे — सभी मुक्त-रूप फ़ील्ड भेजने से पहले लंबाई मानों में घटा दिए जाते हैं। |

### Apple फ़्रेमवर्क

| फ़्रेमवर्क | किसके लिए उपयोग |
|---|---|
| **AVFoundation** | `AVAudioEngine` एकल-टैप इनपुट, `AVSpeechSynthesizer` TTS (Yuna / Premium / Personal Voice), `AVCaptureSession` कैमरा |
| **Speech** | `addsPunctuation` के साथ `SpeechAnalyzer` (macOS 26) या `SFSpeechRecognizer` स्ट्रीमिंग STT |
| **Vision** | सिर की मुद्रा → नज़र अनुमान के लिए `VNDetectFaceLandmarksRequest` (~10 fps तक सीमित) |
| **Accelerate (vDSP)** | डिवाइस पर स्पीकर डायराइज़ेशन हेतु 1024-पॉइंट FFT + Hann विंडो + L2-सामान्यीकृत लॉग-मैग्निट्यूड स्पेक्ट्रल एम्बेडिंग |
| **EventKit** | कैलेंडर पढ़ना / बनाना / अपडेट / हटाना स्किल्स (पूर्ण-पहुँच दायरा) |
| **ImagePlayground** | macOS 15.1+ अवतार जनरेशन (अन्यथा URLSession के ज़रिए DiceBear PNG पर लौटता है) |
| **CoreImage / CoreVideo** | Vision इनपुट के लिए कैमरा फ़्रेम रूपांतरण |
| **AppKit + SwiftUI** | सेटिंग्स विंडो, बहु-टैब लेआउट, ऐप-में लॉग दृश्य |
| **Combine** | `ConversationEngine` से पूरे UI तक `@Published` स्थिति प्रसार |
| **OSLog** | यूनिफ़ाइड-लॉग डायग्नोस्टिक्स (`subsystem=app.talkmode`) |
| **SQLite3** | स्थानीय उपनाम स्टोर + स्किल मेमोरी |
| **UniformTypeIdentifiers** | अवतार फ़ाइल पिकर |

### तृतीय-पक्ष (गैर-कोड) एसेट

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — प्रति मोड 4 चुनी हुई पर्सोना (이수민·정아람·박도윤·강예린)। उपयोगकर्ता `nemotron-extras.json` से इन्हें ओवरराइड कर सकते हैं।
- **[DiceBear](https://www.dicebear.com)** — 10 अवतार शैलियाँ PNG के रूप में लाई गईं, स्थानीय रूप से कैश की गईं।

---

## तकनीकी पृष्ठभूमि

कुछ डिज़ाइन विकल्प जो स्क्रीनशॉट से स्पष्ट नहीं हैं:

### बहु-माध्यमिक एंडपॉइंटिंग — आपकी बारी तेज़ी से क्यों समाप्त होती है पर बहुत तेज़ी से नहीं

मानक CJK आवाज़ सहायक या तो आपको पहले "हम्म…" पर ही काट देते हैं या आपके वास्तव में समाप्त करने के बाद 3 सेकंड तक प्रतीक्षा करते हैं। TalkMode का `AdaptiveTurnDetector` एक साथ चार संकेत पढ़ता है:

1. **वाक् गतिविधि** (माइक पर EnergyVAD) — खामोशी के नमूने एक बजट जमा करते हैं
2. **स्ट्रीमिंग ट्रांसक्रिप्ट** (SpeechAnalyzer / SFSpeechRecognizer) — कोरियाई संयोजक अंत-प्रत्यय (`-고`, `-는데`) 1.2 से जोड़ते हैं; समापन अंत-प्रत्यय (`-습니다`, `-요`) 400 मि.से. घटाते हैं; हिचकिचाहट चिह्न (`음…`, `어…`) 1.5 से जोड़ते हैं
3. **वाक् दर** (अक्षर / से.) — तेज़ बोलने वालों को छोटा विराम बजट मिलता है
4. **नज़र स्थिति** (Vision के ज़रिए सिर का yaw / pitch) — स्क्रीन की ओर देखना विराम को 0.3-0.65 से गुणा करता है (प्रतीक्षा), पूरे वाक्य के बाद नज़र हटाना 1.4 से गुणा करता है *और* तत्काल तेज़-फायर सक्रिय करता है (आप समाप्त हो चुके हैं)

चारों एक ही `predictedSilenceMs()` फ़ंक्शन में जाते हैं, जो प्रति-भाषा फ़्लोर तक सीमित है (CJK 900-7000 मि.से., अंग्रेज़ी 300-3000 मि.से.)। कोई समानांतर टाइमर नहीं, कोई रेस कंडीशन नहीं।

### हमेशा-चालू ऑडियो भार वहन करने वाला है

`AudioInputStream` `AVAudioEngine` को **प्रति सत्र एक बार शुरू करता है और सत्र समाप्त होने तक कभी नहीं रोकता**। पहले का कोड हर फ़ेज़ सीमा पर इसे रोकता/पुनः शुरू करता था; उस पैटर्न ने macOS 26 पर बग जमा किए (`couldn't get default input device, ID = 0`, `format.sampleRate == inputHWFormat.sampleRate` एबॉर्ट)। अब एक टैप `AsyncStream` के ज़रिए N उपभोक्ताओं (VAD, STT, बार्ज-इन डिटेक्टर, मीटिंग रिकॉर्डर, लेवल मीटर) को बफ़र प्रसारित करता है।

### डिवाइस पर स्पीकर डायराइज़ेशन

मीटिंग मिनट मोड प्रति उच्चारण एक **24-आयामी L2-सामान्यीकृत लॉग-मैग्निट्यूड स्पेक्ट्रल एम्बेडिंग** (FFT 1024, Hann विंडो, hop 256) की गणना के लिए Apple Accelerate vDSP का उपयोग करता है। कोसाइन समानता > 0.82 = पहले जैसा ही स्पीकर, अन्यथा एक नया ID सौंपा जाता है। कोई मॉडल डाउनलोड नहीं, कोई API कॉल नहीं। स्पीकर मीटिंग के बीच बने रहते हैं — "Speaker 1" → "지원" एक बार पुनः-लेबल करें, यह टिक जाता है।

### LLM BYOK है

`AssistantClient` आठ कार्यान्वयनों वाला एक प्रोटोकॉल है। CLI प्रदाता (`claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode` के लिए `CLIAssistantClient`) एक सैंडबॉक्स्ड `currentDirectoryURL` के साथ `~/.talk_mode_mac/work/` में एक उपप्रक्रिया लॉन्च करते हैं, stdout को वाक्य-दर-वाक्य `TTSQueue` में स्ट्रीम करते हैं, और स्वयं TalkMode से कभी API कुंजी नहीं देखते। आप जो भी सब्सक्रिप्शन पहले से चुकाते हैं, वही लाते हैं।

### डिफ़ॉल्ट रूप से गोपनीयता वाली डायग्नोस्टिक्स

वैकल्पिक PostHog टेलीमेट्री केवल **वर्गीकृत इवेंट** अग्रेषित करती है, अंतर्निहित पाठ नहीं:

- `turn / llm / tts / minutes / alias` → भेजने से पहले `[category] len=N` में घटाए जाते हैं
- `skill` → `skill_id` रखता है, `args` हटाता है
- `fsm / endpointing / session / error / update` → केवल मेटाडेटा, कोई ट्रांसक्रिप्ट नहीं

`Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` में सत्यापित करें (यदि आप मुझ पर भरोसा नहीं करते तो बाइनरी की strings में दिखता है)।

### TTS के लिए Markdown हटाया जाता है, चैट के लिए रेंडर किया जाता है

LLM `**बोल्ड**` और `### हेडिंग` से प्यार करते हैं। AVSpeechSynthesizer उन्हें "तारांकन तारांकन बोल्ड तारांकन तारांकन" पढ़ता है। `MarkdownStripper.strip(_:)` पाठ को ठीक `TTSQueue` में प्रवेश से पहले साफ़ करता है (चैट बबल `AttributedString(markdown:)` के ज़रिए मूल रखता है)।

### मॉड्यूलर SwiftPM विभाजन

मुख्य ऐप के साथ दो पुन: उपयोग योग्य लक्ष्य रहते हैं:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — 14 यूनिट टेस्ट के साथ शुद्ध-Foundation `timeout(for:localeID:)` फ़ंक्शन। एक फ़्लोर के साथ प्रति-भाषा `सेकंड/अक्षर × 4` गुणक; किसी असंबंधित कमिट द्वारा चुपचाप पतित नहीं हो सकता।
- **`Endpointing`** (`Sources/Endpointing/`) — `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState` का स्वामी। कोई AVFoundation / Vision निर्भरता नहीं। नज़र-हटाना हैंडऑफ़, माइक-सक्रिय अस्वीकृति, लैच साफ़ करना को कवर करते 7 यूनिट टेस्ट।

`swift test --filter EndpointingTests` और `swift test --filter SpeechWatchdogTests` प्रत्येक एक छोटे मॉड्यूल के विरुद्ध चलते हैं — तेज़ पुनरावृत्ति।

### स्टेट मशीन

हर फ़ेज़ ट्रांज़िशन (`idle → listening → thinking → speaking → listening …`) एक ही `PhaseStateMachine.transition(to:reason:)` से गुज़रता है। अवैध ट्रांज़िशन एक लॉग किए गए कारण के साथ अस्वीकृत किए जाते हैं। यह डायग्नोस्टिक्स टैब की टाइमलाइन में दिखता है, इसलिए जब कुछ अटक जाए, तो आप देख सकते हैं कि *कौन-सा* किनारा फायर होने से इनकार कर रहा है।

---

## समुदाय

- **Discussions** — प्रश्न, विचार, सुविधा अनुरोध → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — बग रिपोर्ट → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## लाइसेंस

संकलित ऐप का उपयोग नि:शुल्क है, व्यक्तिगत या व्यावसायिक — रिलीज़ ZIP में एक हस्ताक्षरित `.app` बंडल होता है।

इस रिपॉज़िटरी का सोर्स **GNU Affero General Public License v3.0** के अंतर्गत लाइसेंस-प्राप्त है — देखें [LICENSE](../LICENSE)। आप इसका उपयोग, अध्ययन, संशोधन और पुनर्वितरण कर सकते हैं, पर कोई भी संशोधित संस्करण — जिसमें नेटवर्क सेवा के रूप में पेश किया गया भी शामिल है — उसी AGPL-3.0 लाइसेंस के तहत खुला रहना चाहिए। कॉपीराइट Baryon Labs के पास है; यदि आपको AGPL-3.0 से बाहर की शर्तें चाहिए (जैसे एक व्यावसायिक लाइसेंस), तो **Discussions** के ज़रिए पूछें।

सियोल में [Baryon Labs](https://baryon.ai) द्वारा बनाया गया।

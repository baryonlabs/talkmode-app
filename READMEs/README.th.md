<div align="center">

# TalkMode

**เปลี่ยน Mac mini ให้เป็นผู้ช่วยตัวจริง — ตอบกลับด้วยเสียงภาษาเกาหลีทันที ทำงานบนเครื่อง ตามกฎที่คุณกำหนด**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | ไทย | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> ที่เก็บโค้ดสาธารณะของ TalkMode — ซอร์สโค้ด, **Releases**, **Issues** และ **Discussions**
> ดูที่ **[SECURITY.md](../SECURITY.md)** เพื่อทราบว่าแอปจัดการข้อมูลของคุณอย่างไรอย่างละเอียด

---

## TalkMode คืออะไร

TalkMode เปลี่ยน Mac mini (หรือ Mac ที่ใช้ Apple silicon เครื่องใดก็ได้) ให้กลายเป็น **ผู้ช่วยด้วยเสียงภาษาเกาหลีแบบเรียลไทม์** ที่ทำตัวเหมือนเพื่อนร่วมงาน ไม่ใช่แชตบอต

- **การสลับเทิร์นในเวลาไม่ถึงวินาที** ด้วยตัวตรวจจับจุดจบประโยคแบบปรับตัวที่ปรับจูนสำหรับภาษาเกาหลี (สายตา + เสียง + ข้อความถอดเสียง)
- **พูดเพื่อขัดจังหวะ หรือมองออกไปทางอื่นเพื่อจบบทสนทนา** — ใช้สัญญาณหลายรูปแบบ ไม่ใช่แค่ตัวจับเวลาความเงียบ
- **4 โหมด**: บทสนทนา · บันทึกการประชุม · ระดมความคิด (เน้นการตอบรับ) · ให้คำปรึกษาทางจิตใจ (เน้นการรับฟัง)
- **การแยกแยะผู้พูดบนเครื่อง** สำหรับบันทึกการประชุม (Apple Accelerate vDSP)
- **Skills**: อ่านปฏิทิน ร่างอีเมล อ่าน SMS สอบถาม CPU/RAM บันทึกความจำ เรียนรู้คำเรียกแทน
- **ผู้ให้บริการ LLM 8 ราย**: CLI ของ Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 ภาษาสำหรับ UI**, มากกว่า 50 ภาษาสำหรับ STT
- **บุคลิก (Personas)**: ไฟล์ Soul + Contract แยกตามภาษา พร้อมชุดที่คัดสรรจาก Nemotron-Personas-Korea ของ NVIDIA
- **อวาตาร์แบบกำหนดเอง** ผ่าน DiceBear (10 สไตล์), ImagePlayground (macOS 15.1+) หรือใช้รูปภาพของคุณเอง
- **ความเป็นส่วนตัวเป็นค่าเริ่มต้น**: ไม่มีข้อมูลใดออกจาก Mac ของคุณ ยกเว้น (ก) ผู้ให้บริการ LLM ที่คุณเลือก และ (ข) ข้อมูลวินิจฉัยที่ไม่ระบุตัวตน ซึ่งข้อความอิสระทั้งหมดถูกตัดเหลือเพียงค่าความยาว

---

## ภาพหน้าจอ

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="แท็บบทสนทนา — หน้าหลัก" /></a><br/>
      <sub><b>แท็บบทสนทนา</b> — อวาตาร์ของผู้ช่วย ตัวอย่างกล้องสำหรับติดตามสายตา (ถ้าต้องการ) การแสดงระดับไมโครโฟน และแชตสด ชิป "최근" สีส้มแสดงอารมณ์ที่กำลังใช้งาน</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="แท็บบทสนทนา — บทสนทนากำลังดำเนิน" /></a><br/>
      <sub><b>บทสนทนาสด</b> — แสดงผล markdown ในกล่องข้อความ STT เติมเครื่องหมายวรรคตอนอัตโนมัติ ป้าย "출발 알림" จะปรากฏเมื่อมีการเตรียม skill</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="การตั้งค่า — บุคลิกผู้ช่วย" /></a><br/>
      <sub><b>การตั้งค่า — บุคลิก</b> — ภาษา UI / STT สไตล์อวาตาร์และเพศ การสร้างด้วย ImagePlayground และสัญญา <code>soul.md</code> แบบสดที่กำหนดกรอบทุกคำตอบ</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="การวินิจฉัย — ไทม์ไลน์" /></a><br/>
      <sub><b>การวินิจฉัย</b> — เฟส, ค่า yaw/pitch, สายตา, ค่าอ่าน STT/ใบหน้า/CPU และไทม์ไลน์ต่อเนื่องของทุกการตัดสินใจเกี่ยวกับจุดจบประโยค ปิดไทม์ไลน์เพื่อประหยัด CPU ได้สองสามเปอร์เซ็นต์</sub>
    </td>
  </tr>
</table>

---

## ภาษาที่รองรับ

TalkMode แยก **ภาษาของ UI** (ภาษาของเมนู ปุ่ม และข้อความแสดงข้อผิดพลาด) ออกจาก **ภาษาของเสียงพูด** (ภาษาที่ผู้ช่วยถอดเสียงและตอบกลับ) ทั้งสองอย่างตั้งค่าแยกกันได้ — อ่าน UI ภาษาเยอรมัน แต่คุยกับผู้ช่วยเป็นภาษาเกาหลีก็ได้

### ภาษาของ UI (20 ภาษา)

ตั้งค่าได้ที่ **Settings → 언어 → UI 언어** ทุกภาษาแปลครบถ้วน — ทั้งเมนู ปุ่ม การตั้งค่า คำอธิบาย skill และป้ายกำกับการวินิจฉัย

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### ภาษาของเสียงพูด / บทสนทนา

ขึ้นอยู่กับสิ่งที่เฟรมเวิร์ก Speech ของ Mac ของคุณรองรับ — โดยทั่วไป **50-60 ภาษา** บน macOS Sonoma+ ตั้งค่าได้ที่ **Settings → 언어 → 음성 인식 언어** ตัวเลือกจะแสดงทุกภาษาที่ `SFSpeechRecognizer.supportedLocales()` ส่งกลับมา โดยปักหมุดภาษา CJK สี่ภาษาและภาษาอังกฤษไว้ด้านบน

ภาษาที่มีให้เสมอบน macOS Sonoma+ มาตรฐาน (เป็นรายการบางส่วน — Mac ของคุณอาจมีมากกว่านี้):

| ภูมิภาค | ภาษา |
|---|---|
| **เอเชียตะวันออก** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **อังกฤษ** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **ยุโรปตะวันตก** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **ยุโรปกลาง / ตะวันออก** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **กรีก / ฮีบรู** | Ελληνικά · עברית |
| **ตะวันออกกลางและเอเชียใต้** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **เอเชียตะวันออกเฉียงใต้** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **อื่น ๆ** | Türkçe · Русский · Català · Қазақ |

> ชุดภาษาที่แน่นอนขึ้นอยู่กับเวอร์ชันของ OS และภาษาสำหรับการเขียนตามคำบอกที่คุณดาวน์โหลดไว้ใน **System Settings → Keyboard → Dictation** TalkMode อ่านรายการแบบสดตอนเปิดแอป — เปิดตัวเลือกบน Mac ของคุณเพื่อดูรายการที่ถูกต้อง

### เสียง TTS

*เสียงเอาต์พุต* ใช้ `AVSpeechSynthesizer` — เอนจินเดียวกับ Siri / การเขียนตามคำบอกของ macOS เสียงดาวน์โหลดได้ที่ **System Settings → Accessibility → Spoken Content → System Voice → Manage Voices** ภาษาเกาหลี: Yuna / Sora; ภาษาอังกฤษ: Samantha / Alex / Daniel / Karen / Moira; ภาษาญี่ปุ่น: Kyoko / O-Ren; ภาษาจีน: Mei-Jia / Tian-Tian; เป็นต้น เสียงพรีเมียม (Yuna Premium ฯลฯ) มีคุณภาพสูงกว่าแต่ต้องใช้เครือข่ายสำหรับช่วงแรก

---

## การติดตั้ง

### Homebrew (แนะนำ)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### ดาวน์โหลดโดยตรง

[Latest release](https://talkmode.baryon.ai/download/TalkMode-0.4.3.zip) → แตกไฟล์ zip → ลากเข้าโฟลเดอร์ `Applications` → ตอนเปิดครั้งแรก macOS อาจแจ้งว่า "from unknown developer" ให้คลิกขวา → Open หนึ่งครั้ง

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.3.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### อัปเดตอัตโนมัติ

Sparkle 2 ติดตั้งมาในตัว เมื่อติดตั้งแล้ว (ไม่ว่าวิธีใด) TalkMode จะตรวจสอบการอัปเดตในเบื้องหลัง — เปิด `TalkMode → Check for Updates…` หรือ `Settings → Update` เพื่อควบคุม

### ความต้องการของระบบ

- macOS **Sonoma (14.0)** ขึ้นไป
- Apple silicon (M1 / M2 / M3 / M4)
- ผู้ให้บริการ LLM — อย่างน้อยคือ Claude CLI, Codex CLI หรือคีย์ OpenAI

---

## การอนุญาต

ระบบจะขอการอนุญาต **เฉพาะครั้งแรกที่คุณใช้คุณสมบัตินั้น ๆ** เท่านั้น:

| คุณสมบัติ | การอนุญาต |
|---|---|
| การฟังตลอดเวลา | Microphone, Speech Recognition |
| การติดตามสายตา (ถ้าต้องการ) | Camera |
| ปุ่ม Right-Option เพื่อปิดเสียง TTS | Input Monitoring |
| Skills ปฏิทิน | Calendars (Full Access) |
| ตัวเขียนอีเมล | Apple Events |
| Skill `messages.list_recent` | Full Disk Access (ต้องอนุญาตด้วยตนเองใน System Settings) |

ไม่มีข้อมูลใดถูกอัปโหลด — STT ทำงานบนเครื่อง (หรือบนเซิร์ฟเวอร์ STT ของ Apple ขึ้นอยู่กับภาษาของคุณ) อวาตาร์เป็นไฟล์ PNG บนเครื่อง และเสียงบันทึกการประชุมยังคงอยู่ใน `~/.talk_mode_mac/recordings/`

---

## ความปลอดภัยและความเป็นส่วนตัว

สิ่งที่ TalkMode เก็บไว้บน Mac ของคุณ สิ่งที่ออกจากเครื่องและไปที่ใด สิ่งที่จัดเก็บบนดิสก์ และวิธีจัดการคีย์ API และการอนุญาต — พร้อมการตรวจสอบความปลอดภัยระดับโค้ดและผลการตรวจสอบ (ไม่พบช่องโหว่ที่ใช้โจมตีจากระยะไกลได้ และเปิดเผยข้อจำกัดในปัจจุบันอย่างโปร่งใส) — มีบันทึกไว้ใน **[SECURITY.md](../SECURITY.md)**

---

## สร้างด้วย

TalkMode เป็นแอป macOS ที่อิงกับ SwiftPM ใช้แพ็กเกจ Swift ของบุคคลที่สามสองรายการ ส่วนที่เหลือเป็นเฟรมเวิร์กของ Apple

### แพ็กเกจ Swift

| แพ็กเกจ | เวอร์ชัน | ทำหน้าที่อะไรที่นี่ | เหตุผล |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | อัปเดตอัตโนมัติในแอปผ่าน appcast ที่ลงนาม | มาตรฐานของแพลตฟอร์ม Apple; ใช้โดย 1Password, Tower, OBS การอัปเดตลงนาม EdDSA ดาวน์โหลดในเบื้องหลัง เมนู "Check for Updates…" |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | ข้อมูลวินิจฉัยแบบไม่ระบุตัวตนที่เลือกเข้าร่วมเอง (บันทึกแบบ OpenTelemetry) | ช่วยให้เราเห็นว่าการเปลี่ยนเฟส *ใด* ที่ติดขัดในการใช้งานจริงโดยไม่ต้องเห็นข้อความของผู้ใช้ — ฟิลด์ข้อความอิสระทั้งหมดถูกลดเหลือค่าความยาวก่อนส่ง |

### เฟรมเวิร์กของ Apple

| เฟรมเวิร์ก | ใช้สำหรับ |
|---|---|
| **AVFoundation** | อินพุตแบบ single-tap ของ `AVAudioEngine`, TTS ของ `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), กล้องของ `AVCaptureSession` |
| **Speech** | STT แบบสตรีมมิงด้วย `SpeechAnalyzer` (macOS 26) หรือ `SFSpeechRecognizer` พร้อม `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` สำหรับท่าทางศีรษะ → การประเมินสายตา (จำกัดที่ ~10 fps) |
| **Accelerate (vDSP)** | FFT 1024 จุด + Hann window + การฝังสเปกตรัม log-magnitude แบบนอร์มัลไลซ์ L2 สำหรับการแยกแยะผู้พูดบนเครื่อง |
| **EventKit** | Skills อ่าน / สร้าง / อัปเดต / ลบปฏิทิน (ขอบเขต full-access) |
| **ImagePlayground** | การสร้างอวาตาร์บน macOS 15.1+ (ถ้าไม่มีจะใช้ PNG ของ DiceBear ผ่าน URLSession แทน) |
| **CoreImage / CoreVideo** | การแปลงเฟรมกล้องสำหรับอินพุตของ Vision |
| **AppKit + SwiftUI** | หน้าต่างการตั้งค่า เลย์เอาต์หลายแท็บ มุมมองบันทึกในแอป |
| **Combine** | การกระจายสถานะ `@Published` จาก `ConversationEngine` ไปยัง UI ทั้งหมด |
| **OSLog** | การวินิจฉัยผ่าน unified log (`subsystem=app.talkmode`) |
| **SQLite3** | ที่เก็บคำเรียกแทนในเครื่อง + ความจำของ skill |
| **UniformTypeIdentifiers** | ตัวเลือกไฟล์อวาตาร์ |

### แอสเซตจากบุคคลที่สาม (ที่ไม่ใช่โค้ด)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — บุคลิกที่คัดสรร 4 แบบต่อโหมด (이수민·정아람·박도윤·강예린) ผู้ใช้สามารถแทนที่ด้วย `nemotron-extras.json` ได้
- **[DiceBear](https://www.dicebear.com)** — อวาตาร์ 10 สไตล์ ดึงมาเป็นไฟล์ PNG และแคชไว้ในเครื่อง

---

## เบื้องหลังทางเทคนิค

ตัวเลือกการออกแบบบางอย่างที่ไม่เห็นชัดจากภาพหน้าจอ:

### การตรวจจับจุดจบประโยคแบบหลายรูปแบบ — ทำไมเทิร์นของคุณจึงจบเร็วแต่ไม่เร็วเกินไป

ผู้ช่วยด้วยเสียงสำหรับ CJK ทั่วไปมักตัดบทสนทนาตอนคุณพูด "음…" คำแรก หรือไม่ก็รอ 3 วินาทีหลังจากคุณพูดจบจริง ๆ `AdaptiveTurnDetector` ของ TalkMode อ่านสัญญาณสี่อย่างพร้อมกัน:

1. **กิจกรรมเสียง** (EnergyVAD ที่ไมโครโฟน) — ตัวอย่างความเงียบสะสมเป็นงบประมาณ
2. **ข้อความถอดเสียงแบบสตรีมมิง** (SpeechAnalyzer / SFSpeechRecognizer) — 연결 어미 ภาษาเกาหลี (`-고`, `-는데`) เพิ่ม 1.2 วินาที; 종결 어미 (`-습니다`, `-요`) ลด 400 มิลลิวินาที; คำลังเล (`음…`, `어…`) เพิ่ม 1.5 วินาที
3. **อัตราการพูด** (ตัวอักษร / วินาที) — คนที่พูดเร็วได้งบประมาณการหยุดที่น้อยลง
4. **สถานะสายตา** (yaw / pitch ของศีรษะผ่าน Vision) — การมองหน้าจอคูณเวลาหยุดด้วย 0.3-0.65 (กำลังรอ) การมองออกไปทางอื่นหลังประโยคที่สมบูรณ์คูณด้วย 1.4 *และ* เปิดใช้การจบทันที (คุณพูดจบแล้ว)

ทั้งสี่อย่างป้อนเข้าฟังก์ชัน `predictedSilenceMs()` เดียว แล้วถูกจำกัดด้วยขอบล่างต่อภาษา (CJK 900-7000 มิลลิวินาที, อังกฤษ 300-3000 มิลลิวินาที) ไม่มีตัวจับเวลาคู่ขนาน ไม่มี race condition

### เสียงที่เปิดตลอดเวลาเป็นองค์ประกอบสำคัญ

`AudioInputStream` เริ่ม `AVAudioEngine` **หนึ่งครั้งต่อเซสชันและไม่หยุดเลย** จนกว่าเซสชันจะจบ โค้ดก่อนหน้านี้หยุด/เริ่มใหม่ทุกขอบเขตของเฟส รูปแบบนั้นสะสมบั๊กบน macOS 26 (`couldn't get default input device, ID = 0`, การยกเลิก `format.sampleRate == inputHWFormat.sampleRate`) ตอนนี้ tap เดียวกระจายบัฟเฟอร์ไปยังผู้บริโภค N ราย (VAD, STT, ตัวตรวจจับการขัดจังหวะ, ตัวบันทึกการประชุม, ตัววัดระดับ) ผ่าน `AsyncStream`

### การแยกแยะผู้พูดบนเครื่อง

โหมดบันทึกการประชุมใช้ Apple Accelerate vDSP เพื่อคำนวณ **การฝังสเปกตรัม log-magnitude แบบนอร์มัลไลซ์ L2 ขนาด 24 มิติ** (FFT 1024, Hann window, hop 256) ต่อหนึ่งประโยค ความคล้ายแบบโคไซน์ > 0.82 = ผู้พูดคนเดียวกับก่อนหน้า ไม่เช่นนั้นกำหนด ID ใหม่ ไม่ต้องดาวน์โหลดโมเดล ไม่มีการเรียก API ผู้พูดจะคงอยู่ข้ามการประชุม — เปลี่ยนชื่อ "Speaker 1" → "지원" ครั้งเดียวแล้วจะคงอยู่

### LLM เป็นแบบ BYOK

`AssistantClient` เป็นโปรโตคอลเดียวที่มีการนำไปใช้งานแปดแบบ ผู้ให้บริการแบบ CLI (`CLIAssistantClient` สำหรับ `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) เปิดโปรเซสย่อยใน `~/.talk_mode_mac/work/` ด้วย `currentDirectoryURL` แบบแซนด์บ็อกซ์ สตรีม stdout ทีละประโยคเข้า `TTSQueue` และไม่เคยเห็นคีย์ API จาก TalkMode เอง คุณนำการสมัครสมาชิกที่คุณจ่ายอยู่แล้วมาใช้ได้เลย

### การวินิจฉัยที่เน้นความเป็นส่วนตัวเป็นค่าเริ่มต้น

เทเลเมทรี PostHog แบบเลือกเข้าร่วมเองจะส่งต่อเฉพาะ **เหตุการณ์ที่จัดหมวดหมู่แล้ว** ไม่ใช่ข้อความต้นฉบับ:

- `turn / llm / tts / minutes / alias` → ลดเหลือ `[category] len=N` ก่อนส่ง
- `skill` → เก็บ `skill_id` ทิ้ง `args`
- `fsm / endpointing / session / error / update` → เฉพาะข้อมูลเมตา ไม่มีข้อความถอดเสียง

ตรวจสอบได้ใน `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (มองเห็นได้ในสตริงของไบนารีถ้าคุณไม่เชื่อใจเรา)

### Markdown ถูกตัดออกสำหรับ TTS แต่แสดงผลสำหรับแชต

LLM ชอบ `**bold**` และ `### headings` AVSpeechSynthesizer จะอ่านมันว่า "ดอกจัน ดอกจัน bold ดอกจัน ดอกจัน" `MarkdownStripper.strip(_:)` ทำความสะอาดข้อความก่อนเข้า `TTSQueue` (กล่องแชตเก็บต้นฉบับไว้ผ่าน `AttributedString(markdown:)`)

### การแบ่งโมดูลด้วย SwiftPM

มีสองทาร์เก็ตที่ใช้ซ้ำได้อยู่ข้าง ๆ แอปหลัก:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — ฟังก์ชัน `timeout(for:localeID:)` แบบ Foundation ล้วน พร้อมยูนิตเทสต์ 14 รายการ ตัวคูณ `sec/char × 4` ต่อภาษาพร้อมขอบล่าง; ไม่สามารถถูกถดถอยอย่างเงียบ ๆ จากคอมมิตที่ไม่เกี่ยวข้องได้
- **`Endpointing`** (`Sources/Endpointing/`) — ครอบครอง `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState` ไม่ต้องพึ่งพา AVFoundation / Vision ยูนิตเทสต์ 7 รายการครอบคลุมการส่งต่อเมื่อมองออกไปทางอื่น การปฏิเสธเมื่อไมโครโฟนทำงาน และการล้าง latch

`swift test --filter EndpointingTests` และ `swift test --filter SpeechWatchdogTests` แต่ละคำสั่งรันกับโมดูลขนาดเล็ก — ทำซ้ำได้เร็ว

### State machine

ทุกการเปลี่ยนเฟส (`idle → listening → thinking → speaking → listening …`) ผ่าน `PhaseStateMachine.transition(to:reason:)` เดียว การเปลี่ยนที่ไม่ถูกต้องจะถูกปฏิเสธพร้อมเหตุผลที่บันทึกไว้ ปรากฏในไทม์ไลน์ของแท็บการวินิจฉัย ดังนั้นเมื่อมีอะไรติดขัด คุณจะเห็นว่าขอบ *ใด* ปฏิเสธที่จะทำงาน

---

## ชุมชน

- **Discussions** — คำถาม ไอเดีย คำขอคุณสมบัติ → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — รายงานข้อบกพร่อง → https://github.com/baryonlabs/talkmode-app/issues
- **อีเมล** — support@baryon.ai

## สัญญาอนุญาต

แอปที่คอมไพล์แล้วใช้งานได้ฟรี ไม่ว่าส่วนตัวหรือเชิงพาณิชย์ — ไฟล์ ZIP ของรีลีสมีบันเดิล `.app` ที่ลงนามแล้วหนึ่งรายการ

ซอร์สโค้ดในที่เก็บนี้อยู่ภายใต้สัญญาอนุญาต **GNU Affero General Public License v3.0** — ดูที่ [LICENSE](../LICENSE) คุณสามารถใช้ ศึกษา แก้ไข และเผยแพร่ซ้ำได้ แต่เวอร์ชันที่แก้ไขใด ๆ — รวมถึงเวอร์ชันที่ให้บริการเป็นบริการเครือข่าย — ต้องยังคงเปิดเผยภายใต้สัญญาอนุญาต AGPL-3.0 เดียวกัน Baryon Labs ถือลิขสิทธิ์; หากคุณต้องการเงื่อนไขนอกเหนือจาก AGPL-3.0 (เช่น สัญญาอนุญาตเชิงพาณิชย์) โปรดสอบถามผ่าน **Discussions**

สร้างขึ้นในกรุงโซลโดย [Baryon Labs](https://baryon.ai)

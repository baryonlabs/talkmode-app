<div align="center">

# TalkMode

**Mac mini biến thành một trợ lý thực thụ — giọng nói tiếng Hàn tức thì, ngay trên thiết bị, theo điều kiện của bạn.**
**Biến Mac mini thành một trợ lý thực thụ. Phản hồi bằng giọng nói tức thì, mọi thứ on-device, theo những quy tắc bạn đặt ra.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | Tiếng Việt | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Kho lưu trữ công khai cho TalkMode — mã nguồn, **Releases**, **Issues** và **Discussions**.
> Xem **[SECURITY.md](../SECURITY.md)** để biết chính xác cách ứng dụng xử lý dữ liệu của bạn.

---

## TalkMode là gì

TalkMode biến một chiếc Mac mini (hoặc bất kỳ máy Mac dùng Apple silicon nào) thành một **trợ lý giọng nói tiếng Hàn thời gian thực** hành xử như một đồng nghiệp, không phải một chatbot.

- **Chuyển lượt nói trong chưa đến một giây** với bộ xác định điểm kết thúc thích ứng được tinh chỉnh cho tiếng Hàn (ánh mắt + giọng nói + bản chép lời)
- **Nói để ngắt lời, hoặc nhìn đi chỗ khác để kết thúc** — tín hiệu đa phương thức, không chỉ là bộ đếm thời gian im lặng
- **4 chế độ**: trò chuyện · biên bản họp · động não (tập trung vào sự hưởng ứng) · tư vấn tâm lý (tập trung vào lắng nghe)
- **Phân tách người nói ngay trên thiết bị** cho biên bản họp (Apple Accelerate vDSP)
- **Kỹ năng**: đọc lịch, soạn thư, đọc SMS, truy vấn mức dùng CPU/RAM, lưu bộ nhớ, học biệt danh
- **8 nhà cung cấp LLM**: các CLI Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 ngôn ngữ giao diện**, hơn 50 ngôn ngữ vùng STT
- **Nhân vật**: các tệp Soul + Contract, theo từng ngôn ngữ, cùng một bộ được tuyển chọn từ NVIDIA Nemotron-Personas-Korea
- **Hình đại diện tùy chỉnh** qua DiceBear (10 phong cách), ImagePlayground (macOS 15.1+), hoặc hình ảnh của riêng bạn
- **Riêng tư theo mặc định**: không có gì rời khỏi máy Mac của bạn ngoại trừ (a) nhà cung cấp LLM bạn đã chọn và (b) dữ liệu chẩn đoán ẩn danh với toàn bộ văn bản tự do được rút gọn thành các giá trị độ dài

---

## Ảnh chụp màn hình

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Tab trò chuyện — chính" /></a><br/>
      <sub><b>Tab trò chuyện</b> — hình đại diện trợ lý, bản xem trước camera tùy chọn cho việc theo dõi ánh mắt, lớp phủ mức micro, và trò chuyện trực tiếp. Chip "gần đây" màu cam cho thấy tâm trạng đang hoạt động.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Tab trò chuyện — cuộc trò chuyện đang diễn ra" /></a><br/>
      <sub><b>Trò chuyện trực tiếp</b> — markdown được hiển thị trong các bong bóng, STT tự động thêm dấu câu, huy hiệu "thông báo khởi hành" xuất hiện khi một kỹ năng được chuẩn bị sẵn.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Cài đặt — tính cách trợ lý" /></a><br/>
      <sub><b>Cài đặt — Nhân vật</b> — ngôn ngữ giao diện / STT, phong cách và giới tính hình đại diện, tạo qua ImagePlayground, và hợp đồng <code>soul.md</code> trực tiếp định khung cho mọi câu trả lời.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Chẩn đoán — dòng thời gian" /></a><br/>
      <sub><b>Chẩn đoán</b> — pha, yaw/pitch, ánh mắt, các chỉ số STT/khuôn mặt/CPU, và một dòng thời gian cuộn của mọi quyết định xác định điểm kết thúc. Tắt dòng thời gian để tiết kiệm vài phần trăm CPU.</sub>
    </td>
  </tr>
</table>

---

## Các ngôn ngữ được hỗ trợ

TalkMode tách biệt **ngôn ngữ giao diện** (ngôn ngữ của menu, nút bấm và thông báo lỗi) khỏi **ngôn ngữ giọng nói** (ngôn ngữ mà trợ lý chép lời và trả lời). Hai thứ này có thể được đặt độc lập — đọc giao diện bằng tiếng Đức, nói chuyện với trợ lý bằng tiếng Hàn.

### Ngôn ngữ giao diện (20)

Đặt trong **Cài đặt → Ngôn ngữ → Ngôn ngữ giao diện**. Mọi ngôn ngữ đều được dịch đầy đủ — tất cả menu, nút bấm, cài đặt, mô tả kỹ năng và nhãn chẩn đoán.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Ngôn ngữ giọng nói / trò chuyện

Bất cứ thứ gì khung Speech của máy Mac bạn hỗ trợ — thường là **50-60 ngôn ngữ vùng** trên macOS Sonoma+. Đặt trong **Cài đặt → Ngôn ngữ → Ngôn ngữ nhận dạng giọng nói**; bộ chọn liệt kê mọi ngôn ngữ vùng do `SFSpeechRecognizer.supportedLocales()` trả về, với bốn ngôn ngữ vùng CJK + tiếng Anh được ghim ở trên cùng.

Luôn có sẵn trên một bản cài macOS Sonoma+ tiêu chuẩn (danh sách một phần — máy Mac của bạn có thể có nhiều hơn):

| Khu vực | Ngôn ngữ vùng |
|---|---|
| **Đông Á** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Tiếng Anh** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Tây Âu** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Trung / Đông Âu** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Hy Lạp / Do Thái** | Ελληνικά · עברית |
| **Trung Đông & Nam Á** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Đông Nam Á** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Khác** | Türkçe · Русский · Català · Қазақ |

> Bộ chính xác phụ thuộc vào phiên bản hệ điều hành và các ngôn ngữ đọc chính tả bạn đã tải xuống trong **Cài đặt Hệ thống → Bàn phím → Đọc chính tả**. TalkMode đọc danh sách trực tiếp khi khởi chạy — hãy mở bộ chọn trên máy Mac của bạn để có danh mục chính xác nhất.

### Giọng đọc TTS

*Đầu ra* giọng nói dùng `AVSpeechSynthesizer` — cùng động cơ với Siri / đọc chính tả của macOS. Giọng đọc được tải xuống trong **Cài đặt Hệ thống → Trợ năng → Nội dung được nói → Giọng hệ thống → Quản lý giọng**. Tiếng Hàn: Yuna / Sora; tiếng Anh: Samantha / Alex / Daniel / Karen / Moira; tiếng Nhật: Kyoko / O-Ren; tiếng Trung: Mei-Jia / Tian-Tian; v.v. Các giọng cao cấp (Yuna Premium, v.v.) có chất lượng cao hơn nhưng cần mạng cho đoạn đầu tiên.

---

> 🆕 **Latest features and install guide are in bản dịch này.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Cài đặt

### Homebrew (khuyến nghị)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Tải xuống trực tiếp

[Bản phát hành mới nhất](https://talkmode.baryon.ai/download/TalkMode-0.4.38.zip) → giải nén → kéo vào `Applications` → ở lần khởi chạy đầu tiên macOS có thể nói "từ nhà phát triển không xác định", nhấp chuột phải → Open một lần.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.38.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Tự động cập nhật

Sparkle 2 được tích hợp sẵn. Sau khi cài đặt (theo cách nào cũng được), TalkMode kiểm tra cập nhật trong nền — mở `TalkMode → Check for Updates…` hoặc `Cài đặt → Cập nhật` để điều khiển nó.

### Yêu cầu

- macOS **Sonoma (14.0)** trở lên
- Apple silicon (M1 / M2 / M3 / M4)
- Một nhà cung cấp LLM — tối thiểu là Claude CLI, Codex CLI, hoặc một khóa OpenAI

---

## Quyền

Quyền chỉ được yêu cầu **lần đầu tiên bạn sử dụng tính năng đó**:

| Tính năng | Quyền |
|---|---|
| Lắng nghe luôn bật | Micrô, Nhận dạng Giọng nói |
| Theo dõi ánh mắt (tùy chọn) | Camera |
| Phím Option phải để tắt tiếng TTS | Giám sát Đầu vào |
| Kỹ năng lịch | Lịch (Quyền Truy cập Đầy đủ) |
| Trình soạn email | Apple Events |
| Kỹ năng `messages.list_recent` | Quyền Truy cập Toàn bộ Đĩa (cấp thủ công trong Cài đặt Hệ thống) |

Không có gì được tải lên — STT chạy ngay trên thiết bị (hoặc trên máy chủ STT của Apple tùy theo ngôn ngữ vùng của bạn), hình đại diện là các tệp PNG cục bộ, và âm thanh biên bản họp vẫn nằm trong `~/.talk_mode_mac/recordings/`.

---

## Bảo mật & Quyền riêng tư

Những gì TalkMode giữ trên máy Mac của bạn, những gì rời khỏi nó và đi đến đâu, những gì được lưu trên đĩa, cùng cách xử lý khóa API và quyền — kèm theo một đợt rà soát bảo mật ở cấp độ mã nguồn và các kết quả của nó (không có lỗ hổng nào có thể bị khai thác từ xa; các hạn chế hiện tại được công bố một cách minh bạch) — được ghi lại trong **[SECURITY.md](../SECURITY.md)**.

---

## Được xây dựng với

TalkMode là một ứng dụng macOS dựa trên SwiftPM. Hai gói Swift của bên thứ ba, phần còn lại là các khung của Apple.

### Các gói Swift

| Gói | Phiên bản | Vai trò ở đây | Vì sao |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Tự động cập nhật trong ứng dụng qua appcast đã ký | Tiêu chuẩn nền tảng Apple; được 1Password, Tower, OBS sử dụng. Cập nhật ký EdDSA, tải xuống trong nền, mục menu "Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Chẩn đoán ẩn danh theo lựa chọn tham gia (nhật ký kiểu OpenTelemetry) | Cho phép chúng tôi thấy *những* chuyển pha nào đang bị treo trong thực tế mà không bao giờ nhìn thấy văn bản người dùng — mọi trường văn bản tự do được rút gọn thành giá trị độ dài trước khi gửi. |

### Các khung của Apple

| Khung | Dùng cho |
|---|---|
| **AVFoundation** | Đầu vào một-tap `AVAudioEngine`, TTS `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), camera `AVCaptureSession` |
| **Speech** | STT luồng `SpeechAnalyzer` (macOS 26) hoặc `SFSpeechRecognizer` với `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` cho tư thế đầu → ước lượng ánh mắt (giới hạn ~10 fps) |
| **Accelerate (vDSP)** | FFT 1024 điểm + cửa sổ Hann + nhúng phổ log-magnitude chuẩn hóa L2 cho phân tách người nói ngay trên thiết bị |
| **EventKit** | Kỹ năng đọc / tạo / cập nhật / xóa lịch (phạm vi quyền truy cập đầy đủ) |
| **ImagePlayground** | Tạo hình đại diện trên macOS 15.1+ (nếu không thì quay lại DiceBear PNG qua URLSession) |
| **CoreImage / CoreVideo** | Chuyển đổi khung hình camera cho đầu vào Vision |
| **AppKit + SwiftUI** | Cửa sổ cài đặt, bố cục nhiều tab, khung xem nhật ký trong ứng dụng |
| **Combine** | Truyền trạng thái `@Published` từ `ConversationEngine` đến toàn bộ giao diện |
| **OSLog** | Chẩn đoán unified-log (`subsystem=app.talkmode`) |
| **SQLite3** | Kho biệt danh cục bộ + bộ nhớ kỹ năng |
| **UniformTypeIdentifiers** | Bộ chọn tệp hình đại diện |

### Tài nguyên của bên thứ ba (phi mã nguồn)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 nhân vật được tuyển chọn cho mỗi chế độ (이수민·정아람·박도윤·강예린). Người dùng có thể ghi đè bằng `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 phong cách hình đại diện được lấy dưới dạng PNG, lưu vào bộ nhớ đệm cục bộ.

---

## Bối cảnh kỹ thuật

Một vài lựa chọn thiết kế không hiển nhiên qua ảnh chụp màn hình:

### Xác định điểm kết thúc đa phương thức — vì sao lượt của bạn kết thúc nhanh nhưng không quá nhanh

Các trợ lý giọng nói CJK tiêu chuẩn hoặc ngắt lời bạn ngay ở tiếng "ừm…" đầu tiên hoặc chờ 3 giây sau khi bạn thực sự nói xong. `AdaptiveTurnDetector` của TalkMode đọc bốn tín hiệu cùng một lúc:

1. **Hoạt động giọng nói** (EnergyVAD trên micro) — các mẫu im lặng tích lũy một ngân sách
2. **Bản chép lời luồng** (SpeechAnalyzer / SFSpeechRecognizer) — vĩ tố nối tiếng Hàn (`-고`, `-는데`) cộng thêm 1,2 giây; vĩ tố kết thúc (`-습니다`, `-요`) trừ đi 400 ms; các dấu hiệu ngập ngừng (`음…`, `어…`) cộng thêm 1,5 giây
3. **Tốc độ nói** (ký tự / giây) — người nói nhanh nhận được ngân sách tạm dừng nhỏ hơn
4. **Trạng thái ánh mắt** (yaw / pitch của đầu qua Vision) — nhìn vào màn hình nhân khoảng tạm dừng với 0,3-0,65 (đang chờ), nhìn đi chỗ khác sau một câu hoàn chỉnh nhân với 1,4 *và* kích hoạt một lần kích hoạt nhanh tức thì (bạn đã xong)

Cả bốn đều đưa vào một hàm `predictedSilenceMs()` duy nhất, được kẹp ở giá trị sàn theo từng ngôn ngữ (CJK 900-7000 ms, tiếng Anh 300-3000 ms). Không có bộ đếm thời gian song song, không có điều kiện tranh chấp.

### Âm thanh luôn bật là yếu tố chịu lực

`AudioInputStream` khởi động `AVAudioEngine` **một lần mỗi phiên và không bao giờ dừng nó** cho đến khi phiên kết thúc. Mã trước đây dừng/khởi động lại ở mỗi ranh giới pha; mẫu hình đó tích lũy lỗi trên macOS 26 (`couldn't get default input device, ID = 0`, các sự cố hủy `format.sampleRate == inputHWFormat.sampleRate`). Giờ đây một tap phát các bộ đệm tới N người tiêu thụ (VAD, STT, bộ phát hiện chen ngang, máy ghi cuộc họp, đồng hồ đo mức) qua `AsyncStream`.

### Phân tách người nói ngay trên thiết bị

Chế độ Biên bản họp dùng Apple Accelerate vDSP để tính một **nhúng phổ log-magnitude chuẩn hóa L2 24 chiều** (FFT 1024, cửa sổ Hann, hop 256) cho mỗi lần phát ngôn. Độ tương đồng cosine > 0,82 = cùng người nói như trước, nếu không sẽ gán một ID mới. Không tải mô hình, không gọi API. Người nói được duy trì xuyên các cuộc họp — đổi nhãn "Speaker 1" → "지원" một lần, nó sẽ giữ nguyên.

### LLM theo nguyên tắc BYOK

`AssistantClient` là một giao thức với tám hiện thực hóa. Các nhà cung cấp CLI (`CLIAssistantClient` cho `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) khởi chạy một tiến trình con trong `~/.talk_mode_mac/work/` với `currentDirectoryURL` được sandbox, truyền stdout từng câu một vào `TTSQueue`, và không bao giờ nhìn thấy khóa API từ chính TalkMode. Bạn mang theo bất kỳ gói đăng ký nào bạn đã trả tiền.

### Chẩn đoán riêng tư theo mặc định

Telemetry PostHog theo lựa chọn tham gia chỉ chuyển tiếp **các sự kiện đã phân loại**, không phải văn bản gốc:

- `turn / llm / tts / minutes / alias` → rút gọn thành `[category] len=N` trước khi gửi
- `skill` → giữ `skill_id`, bỏ `args`
- `fsm / endpointing / session / error / update` → chỉ siêu dữ liệu, không có bản chép lời

Hãy xác minh trong `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (hiển thị trong các chuỗi của tệp nhị phân nếu bạn không tin tôi).

### Markdown bị loại bỏ cho TTS, được hiển thị cho trò chuyện

Các LLM rất thích `**đậm**` và `### tiêu đề`. AVSpeechSynthesizer đọc chúng thành "dấu sao dấu sao đậm dấu sao dấu sao". `MarkdownStripper.strip(_:)` làm sạch văn bản ngay trước khi nó vào `TTSQueue` (bong bóng trò chuyện giữ bản gốc qua `AttributedString(markdown:)`).

### Phân tách SwiftPM theo mô-đun

Hai mục tiêu có thể tái sử dụng tồn tại bên cạnh ứng dụng chính:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — hàm `timeout(for:localeID:)` thuần Foundation với 14 bài kiểm thử đơn vị. Hệ số nhân `giây/ký tự × 4` theo từng ngôn ngữ kèm một giá trị sàn; không thể bị suy giảm âm thầm bởi một commit không liên quan.
- **`Endpointing`** (`Sources/Endpointing/`) — sở hữu `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Không phụ thuộc AVFoundation / Vision. 7 bài kiểm thử đơn vị bao quát việc bàn giao khi nhìn đi chỗ khác, từ chối khi micro hoạt động, xóa chốt.

`swift test --filter EndpointingTests` và `swift test --filter SpeechWatchdogTests` mỗi cái chạy trên một mô-đun nhỏ — lặp nhanh.

### Máy trạng thái

Mọi chuyển pha (`idle → listening → thinking → speaking → listening …`) đều đi qua một `PhaseStateMachine.transition(to:reason:)` duy nhất. Các chuyển đổi không hợp lệ bị từ chối kèm một lý do đã được ghi nhật ký. Điều này hiện ra trên dòng thời gian của tab Chẩn đoán, nên khi có thứ gì bị kẹt, bạn có thể thấy *cạnh nào* đã từ chối kích hoạt.

---

## Cộng đồng

- **Discussions** — câu hỏi, ý tưởng, yêu cầu tính năng → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — báo cáo lỗi → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## Giấy phép

Ứng dụng đã biên dịch được sử dụng miễn phí, cho cá nhân hoặc thương mại — các tệp ZIP phát hành chứa một gói `.app` đã ký duy nhất.

Mã nguồn trong kho lưu trữ này được cấp phép theo **GNU Affero General Public License v3.0** — xem [LICENSE](../LICENSE). Bạn có thể sử dụng, nghiên cứu, sửa đổi và phân phối lại, nhưng bất kỳ phiên bản đã sửa đổi nào — kể cả phiên bản được cung cấp dưới dạng dịch vụ mạng — đều phải giữ mã nguồn mở theo cùng giấy phép AGPL-3.0. Baryon Labs giữ bản quyền; nếu bạn cần các điều khoản ngoài AGPL-3.0 (ví dụ giấy phép thương mại), hãy hỏi qua **Discussions**.

Được tạo tại Seoul bởi [Baryon Labs](https://baryon.ai).

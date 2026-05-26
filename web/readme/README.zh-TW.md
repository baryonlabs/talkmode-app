<div align="center">

# TalkMode

**把 Mac mini 變成真正的助理 — 即時語音、全程 on-device、按你的規則來。**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | 繁體中文 | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> TalkMode 的公開儲存庫 — 原始碼、**Releases**、**Issues** 和 **Discussions**。
> 關於應用程式如何處理你的資料的確切方式，請參閱 **[SECURITY.md](../SECURITY.md)**。

---

## TalkMode 是什麼

TalkMode 把 Mac mini（或任何 Apple silicon Mac）變成一個**即時韓語語音助理**，它的行為像一位同事，而不是聊天機器人。

- 借助為韓語調校的自適應端點偵測器（視線 + 語音 + 轉錄），實現**亞秒級的輪次切換**
- **說話即可打斷，移開視線即可收尾** — 多模態線索，而不只是靜默計時器
- **4 種模式**：對話 · 會議記錄 · 腦力激盪（側重附和）· 心理諮商（側重傾聽）
- 為會議記錄提供 **on-device 語者分離**（Apple Accelerate vDSP）
- **技能**：讀取行事曆、草擬郵件、讀取簡訊、查詢 CPU/RAM、儲存記憶、學習別名
- **8 個 LLM 提供方**：Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLI + OpenAI + Mock
- **20 種介面語言**，50+ 種 STT 地區
- **角色**：依語言區分的 Soul + Contract 檔案，外加一套精選自 NVIDIA 的 Nemotron-Personas-Korea
- 透過 DiceBear（10 種風格）、ImagePlayground（macOS 15.1+）或你自己的圖片實現**自訂頭像**
- **預設隱私優先**：除 (a) 你選擇的 LLM 提供方和 (b) 已將所有自由文字剝離為長度值的匿名診斷資訊外，沒有任何內容離開你的 Mac

---

## 螢幕截圖

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="對話分頁 — 主畫面" /></a><br/>
      <sub><b>對話分頁</b> — 助理頭像、用於視線追蹤的選用攝影機預覽、麥克風音量疊加層以及即時聊天。橙色的「最近」標籤顯示目前的情緒。</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="對話分頁 — 對話進行中" /></a><br/>
      <sub><b>即時對話</b> — 氣泡中渲染 Markdown，STT 自動加上標點，當技能就緒時會顯示「出發提醒」徽章。</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="設定 — 助理人格" /></a><br/>
      <sub><b>設定 — 角色</b> — 介面 / STT 語言、頭像風格與性別、ImagePlayground 生成，以及為每則回覆定調的即時 <code>soul.md</code> 契約。</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="診斷 — 時間軸" /></a><br/>
      <sub><b>診斷</b> — 階段、yaw/pitch、視線、STT/人臉/CPU 讀數，以及每次端點偵測決策的滾動時間軸。關閉時間軸可節省幾個百分點的 CPU。</sub>
    </td>
  </tr>
</table>

---

## 支援的語言

TalkMode 將**介面語言**（選單、按鈕和錯誤訊息所用的語言）與**語音語言**（助理轉錄和回覆所用的語言）分開。兩者可以獨立設定 — 用德語介面，同時用韓語和助理交談。

### 介面語言（20 種）

在**設定 → 語言 → 介面語言**中設定。每種語言都已完整翻譯 — 所有選單、按鈕、設定、技能描述和診斷標籤。

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### 語音 / 對話語言

取決於你 Mac 的 Speech 框架所支援的範圍 — 在 macOS Sonoma+ 上通常為 **50-60 種地區**。在**設定 → 語言 → 語音辨識語言**中設定；選擇器會列出 `SFSpeechRecognizer.supportedLocales()` 回傳的所有地區，並將 4 種 CJK + 英語地區置頂。

在標準的 macOS Sonoma+ 安裝上始終可用（部分清單 — 你的 Mac 上可能更多）：

| 地區 | 語言地區 |
|---|---|
| **東亞** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **英語** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **西歐** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **中歐 / 東歐** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **希臘語 / 希伯來語** | Ελληνικά · עברית |
| **中東與南亞** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **東南亞** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **其他** | Türkçe · Русский · Català · Қазақ |

> 確切的集合取決於作業系統版本以及你在**系統設定 → 鍵盤 → 聽寫**下下載的聽寫語言。TalkMode 在啟動時讀取即時清單 — 請在你的 Mac 上開啟選擇器以取得權威清單。

### TTS 語音

語音*輸出*使用 `AVSpeechSynthesizer` — 與 macOS Siri / 聽寫相同的引擎。語音在**系統設定 → 輔助使用 → 朗讀內容 → 系統語音 → 管理語音**下下載。韓語：Yuna / Sora；英語：Samantha / Alex / Daniel / Karen / Moira；日語：Kyoko / O-Ren；中文：Mei-Jia / Tian-Tian；等等。進階語音（Yuna Premium 等）品質更高，但首個音訊區塊需要連網。

---

> 🆕 **Latest features and install guide are in this translation.** This translation covers the core docs; the visual install walkthrough, free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## 安裝

### Homebrew（建議）

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### 直接下載

[最新版本](https://talkmode.baryon.ai/download/TalkMode-0.4.32.zip) → 解壓縮 → 拖入 `Applications` → 首次啟動時 macOS 可能會提示「來自身分不明的開發者」，按右鍵 → 選擇一次「打開」。

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.32.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### 自動更新

內建 Sparkle 2。安裝後（無論用哪種方式），TalkMode 會在背景檢查更新 — 可透過 `TalkMode → 檢查更新…` 或 `設定 → 更新`來控制。

### 系統需求

- macOS **Sonoma (14.0)** 或更新版本
- Apple silicon (M1 / M2 / M3 / M4)
- 一個 LLM 提供方 — 至少是 Claude CLI、Codex CLI 或一個 OpenAI 金鑰

---

## 權限

權限**只在你首次使用相應功能時**才會被要求：

| 功能 | 權限 |
|---|---|
| 常時聆聽 | 麥克風、語音辨識 |
| 視線追蹤（選用） | 攝影機 |
| 用右 Option 鍵靜音 TTS | 輸入監控 |
| 行事曆技能 | 行事曆（完全存取權） |
| 郵件撰寫器 | Apple Events |
| `messages.list_recent` 技能 | 完整磁碟存取權（在系統設定中手動授予） |

沒有任何內容被上傳 — STT 在 on-device 執行（或依你的地區使用 Apple 的 STT 伺服器），頭像是本機 PNG，會議記錄的音訊保留在 `~/.talk_mode_mac/recordings/` 中。

---

## 安全與隱私

TalkMode 在你 Mac 上保留什麼、什麼內容會送往何處、什麼內容儲存在磁碟上、API 金鑰和權限如何處理 — 連同程式碼層級的安全審查及其結論（不存在可遠端利用的漏洞；目前的限制已透明揭露）— 都記錄在 **[SECURITY.md](../SECURITY.md)** 中。

---

## 技術堆疊

TalkMode 是一個基於 SwiftPM 的 macOS 應用程式。除兩個第三方 Swift 套件外，其餘都是 Apple 框架。

### Swift 套件

| 套件 | 版本 | 在此處的作用 | 原因 |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | 透過簽署的 appcast 實現應用程式內自動更新 | Apple 平台的標準；被 1Password、Tower、OBS 使用。EdDSA 簽署更新、背景下載、「檢查更新…」選單項目。 |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | 選擇加入的匿名診斷（OpenTelemetry 風格的記錄） | 讓我們在永遠看不到使用者文字的前提下，了解實際環境中*哪些*階段轉換出現停滯 — 所有自由格式欄位在傳送前都會縮減為長度值。 |

### Apple 框架

| 框架 | 用途 |
|---|---|
| **AVFoundation** | `AVAudioEngine` 單點擷取輸入、`AVSpeechSynthesizer` TTS（Yuna / Premium / Personal Voice）、`AVCaptureSession` 攝影機 |
| **Speech** | `SpeechAnalyzer`（macOS 26）或 `SFSpeechRecognizer` 串流 STT，啟用 `addsPunctuation` |
| **Vision** | 用於頭部姿態 → 視線估計的 `VNDetectFaceLandmarksRequest`（限流至約 10 fps） |
| **Accelerate (vDSP)** | 用於 on-device 語者分離的 1024 點 FFT + Hann 窗 + L2 正規化對數幅度頻譜嵌入 |
| **EventKit** | 行事曆讀取 / 建立 / 更新 / 刪除技能（完全存取範圍） |
| **ImagePlayground** | macOS 15.1+ 頭像生成（否則退回到透過 URLSession 取得的 DiceBear PNG） |
| **CoreImage / CoreVideo** | 用於 Vision 輸入的攝影機畫格轉換 |
| **AppKit + SwiftUI** | 設定視窗、多分頁版面配置、應用程式內記錄檢視 |
| **Combine** | 從 `ConversationEngine` 向所有 UI 傳播 `@Published` 狀態 |
| **OSLog** | 統一記錄診斷（`subsystem=app.talkmode`） |
| **SQLite3** | 本機別名儲存 + 技能記憶 |
| **UniformTypeIdentifiers** | 頭像檔案選擇器 |

### 第三方（非程式碼）資源

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)**（CC BY 4.0）— 每種模式 4 個精選角色（이수민·정아람·박도윤·강예린）。使用者可透過 `nemotron-extras.json` 覆寫。
- **[DiceBear](https://www.dicebear.com)** — 以 PNG 形式取得並本機快取的 10 種頭像風格。

---

## 技術背景

一些從螢幕截圖中看不出來的設計選擇：

### 多模態端點偵測 — 為什麼你的輪次結束得快但不會太快

標準的 CJK 語音助理要麼在你第一聲「嗯…」時就打斷你，要麼在你真正說完後再等 3 秒。TalkMode 的 `AdaptiveTurnDetector` 同時讀取四個訊號：

1. **語音活動**（麥克風上的 EnergyVAD）— 靜默樣本累積出一個預算
2. **串流轉錄**（SpeechAnalyzer / SFSpeechRecognizer）— 韓語連結詞尾（`-고`、`-는데`）增加 1.2 秒；終結詞尾（`-습니다`、`-요`）減少 400 毫秒；猶豫標記（`음…`、`어…`）增加 1.5 秒
3. **語速**（字元 / 秒）— 說話快的人獲得更小的停頓預算
4. **視線狀態**（透過 Vision 得到的頭部 yaw / pitch）— 看著螢幕會把停頓乘以 0.3-0.65（等待中），在完整句子之後移開視線則乘以 1.4 *並且*裝備一次即時快速觸發（你說完了）

四者全部匯入一個 `predictedSilenceMs()` 函式，並被鉗制到各語言的下限（CJK 900-7000 毫秒，英語 300-3000 毫秒）。沒有並行計時器，沒有競爭條件。

### 常時音訊是關鍵所在

`AudioInputStream` **每個工作階段只啟動一次 `AVAudioEngine`，並且在工作階段結束前從不停止它**。早期程式碼在每個階段邊界停止/重啟；這種模式在 macOS 26 上累積了大量 bug（`couldn't get default input device, ID = 0`、`format.sampleRate == inputHWFormat.sampleRate` 中止）。現在一個擷取點透過 `AsyncStream` 將緩衝區廣播給 N 個消費者（VAD、STT、打斷偵測器、會議錄製器、音量表）。

### on-device 語者分離

會議記錄模式使用 Apple Accelerate vDSP 為每段話語計算一個**24 維 L2 正規化對數幅度頻譜嵌入**（FFT 1024、Hann 窗、hop 256）。餘弦相似度 > 0.82 即與之前是同一語者，否則分配一個新 ID。無需下載模型，無需 API 呼叫。語者跨會議保持 — 把「語者 1」重新標註為「지원」一次，它就會一直保持。

### LLM 是 BYOK

`AssistantClient` 是一個協定，帶有八個實作。CLI 提供方（用於 `claude`、`codex`、`gemini`、`cursor-agent`、`kimi`、`opencode` 的 `CLIAssistantClient`）會以沙箱化的 `currentDirectoryURL` 在 `~/.talk_mode_mac/work/` 中啟動一個子行程，將 stdout 逐句串流傳入 `TTSQueue`，並且永遠不會從 TalkMode 本身看到 API 金鑰。你帶上自己已經在付費的訂閱即可。

### 預設隱私優先的診斷

選擇加入的 PostHog 遙測只轉發**已分類的事件**，而非底層文字：

- `turn / llm / tts / minutes / alias` → 傳送前縮減為 `[category] len=N`
- `skill` → 保留 `skill_id`，捨棄 `args`
- `fsm / endpointing / session / error / update` → 僅中繼資料，無轉錄文字

可在 `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` 中核實（如果你不信我，在二進位檔案的 strings 中也能看到）。

### Markdown 為 TTS 剝離，為聊天渲染

LLM 喜歡 `**bold**` 和 `### headings`。AVSpeechSynthesizer 會把它們唸成「星號 星號 粗體 星號 星號」。`MarkdownStripper.strip(_:)` 會在文字進入 `TTSQueue` 之前對其進行清理（聊天氣泡透過 `AttributedString(markdown:)` 保留原文）。

### 模組化 SwiftPM 拆分

主應用程式旁邊還有兩個可重複使用的目標：

- **`SpeechWatchdog`**（`Sources/SpeechWatchdog/`）— 純 Foundation 的 `timeout(for:localeID:)` 函式，帶 14 個單元測試。帶下限的、依語言的 `sec/char × 4` 乘數；不會被無關的提交悄悄回退。
- **`Endpointing`**（`Sources/Endpointing/`）— 擁有 `AdaptiveTurnDetector`、`VoiceActivity`、`GazeState`。不依賴 AVFoundation / Vision。7 個單元測試，涵蓋移開視線交接、麥克風啟用拒絕、閂鎖清除。

`swift test --filter EndpointingTests` 和 `swift test --filter SpeechWatchdogTests` 各自針對一個小模組執行 — 迭代迅速。

### 狀態機

每一次階段轉換（`idle → listening → thinking → speaking → listening …`）都經過同一個 `PhaseStateMachine.transition(to:reason:)`。非法轉換會被拒絕並記錄原因。它會顯示在診斷分頁的時間軸中，因此當某處卡住時，你能看到*哪條*邊拒絕了觸發。

---

## 社群

- **Discussions** — 問題、想法、功能請求 → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — bug 回報 → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## 授權

編譯後的應用程式可免費使用，無論個人還是商用 — 發佈的 ZIP 包含單個已簽署的 `.app` 套件。

本儲存庫中的原始碼採用 **GNU Affero General Public License v3.0** 授權 — 參見 [LICENSE](../LICENSE)。你可以使用、研究、修改和再散佈它，但任何修改版本 — 包括作為網路服務提供的版本 — 都必須以相同的 AGPL-3.0 授權保持開放。版權歸 Baryon Labs 所有；如果你需要 AGPL-3.0 之外的條款（例如商業授權），請透過 **Discussions** 詢問。

由 [Baryon Labs](https://baryon.ai) 在首爾製作。

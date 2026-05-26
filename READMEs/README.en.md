<div align="center">

# TalkMode

**Mac mini turned into a real assistant — instant Korean voice, on-device, your terms.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  English | <a href="readme/README.ko.md">한국어</a> | <a href="readme/README.ja.md">日本語</a> | <a href="readme/README.zh-CN.md">简体中文</a> | <a href="readme/README.zh-TW.md">繁體中文</a> | <a href="readme/README.es.md">Español</a> | <a href="readme/README.fr.md">Français</a> | <a href="readme/README.de.md">Deutsch</a> | <a href="readme/README.it.md">Italiano</a> | <a href="readme/README.pt.md">Português</a> | <a href="readme/README.ru.md">Русский</a> | <a href="readme/README.ar.md">العربية</a> | <a href="readme/README.hi.md">हिन्दी</a> | <a href="readme/README.id.md">Bahasa Indonesia</a> | <a href="readme/README.vi.md">Tiếng Việt</a> | <a href="readme/README.th.md">ไทย</a> | <a href="readme/README.tr.md">Türkçe</a> | <a href="readme/README.nl.md">Nederlands</a> | <a href="readme/README.pl.md">Polski</a> | <a href="readme/README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Public repository for TalkMode — source, **Releases**, **Issues** and **Discussions**.
> See **[SECURITY.md](SECURITY.md)** for exactly how the app handles your data.

---

## What is TalkMode

TalkMode turns a Mac mini (or any Apple-silicon Mac) into a **real-time Korean voice assistant** that behaves like a coworker, not a chatbot.

- **Sub-second turn-taking** with a Korean-tuned adaptive endpointer (gaze + voice + transcript)
- **Talk to interrupt, or look away to wrap up** — multimodal cues, not just silence timers
- **4 modes**: 대화 · 회의록 · 브레인스토밍(호응 중심) · 심리상담(경청 중심)
- **On-device speaker diarization** for meeting minutes (Apple Accelerate vDSP)
- **Skills**: read calendar, draft mail, read SMS, query CPU/RAM, save memory, learn aliases
- **8 LLM providers**: Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLIs + OpenAI + Mock
- **20 UI languages**, 50+ STT locales
- **Personas**: Soul + Contract files, per-language, + a curated set from NVIDIA's Nemotron-Personas-Korea
- **Custom avatars** via DiceBear (10 styles), ImagePlayground (macOS 15.1+), or your own image
- **Privacy by default**: nothing leaves your Mac except (a) the LLM provider you chose and (b) anonymised diagnostics with all free text stripped to length values

---

## Screenshots

<table>
  <tr>
    <td width="50%" align="center">
      <a href="docs/screenshots/conversation-main.png"><img src="docs/screenshots/conversation-main.png" alt="대화 탭 — 메인" /></a><br/>
      <sub><b>Conversation tab</b> — assistant avatar, optional camera preview for gaze, mic level overlay, and live chat. The orange "최근" chip shows the active mood.</sub>
    </td>
    <td width="50%" align="center">
      <a href="docs/screenshots/conversation-chat.png"><img src="docs/screenshots/conversation-chat.png" alt="대화 탭 — 대화 진행" /></a><br/>
      <sub><b>Live conversation</b> — markdown rendered in bubbles, STT auto-punctuated, "출발 알림" badge surfaces when a skill is staged.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="docs/screenshots/settings-persona.png"><img src="docs/screenshots/settings-persona.png" alt="설정 — 비서 인격" /></a><br/>
      <sub><b>Settings — Persona</b> — UI / STT language, avatar style and gender, ImagePlayground generation, and the live <code>soul.md</code> contract that frames every reply.</sub>
    </td>
    <td width="50%" align="center">
      <a href="docs/screenshots/diagnostics-timeline.png"><img src="docs/screenshots/diagnostics-timeline.png" alt="진단 — 타임라인" /></a><br/>
      <sub><b>Diagnostics</b> — phase, yaw/pitch, gaze, STT/face/CPU readouts, and a rolling timeline of every endpointing decision. Toggle the timeline off to save a few % CPU.</sub>
    </td>
  </tr>
</table>

---

## Supported languages

TalkMode separates **UI language** (what the menus, buttons, and error messages are in) from **speech language** (what the assistant transcribes and replies in). They can be set independently — read German UI, talk to the assistant in Korean.

### UI languages (20)

Set in **Settings → 언어 → UI 언어**. Every language is fully translated — all menus, buttons, settings, skill descriptions, and diagnostics labels.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Speech / conversation languages

Whatever your Mac's Speech framework supports — typically **50-60 locales** on macOS Sonoma+. Set in **Settings → 언어 → 음성 인식 언어**; the picker lists every locale returned by `SFSpeechRecognizer.supportedLocales()` with the four CJK + English locales pinned to the top.

Always available on a stock macOS Sonoma+ install (a partial list — your Mac may have more):

| Region | Locales |
|---|---|
| **East Asia** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **English** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Western Europe** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Central / Eastern Europe** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Greek / Hebrew** | Ελληνικά · עברית |
| **Middle East & South Asia** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Southeast Asia** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Other** | Türkçe · Русский · Català · Қазақ |

> The exact set depends on the OS version and the dictation languages you've downloaded under **System Settings → Keyboard → Dictation**. TalkMode reads the live list at launch — open the picker on your Mac for the authoritative inventory.

### TTS voices

Speech *output* uses `AVSpeechSynthesizer` — same engine as macOS Siri / dictation. Voices download under **System Settings → Accessibility → Spoken Content → System Voice → Manage Voices**. Korean: Yuna / Sora; English: Samantha / Alex / Daniel / Karen / Moira; Japanese: Kyoko / O-Ren; Chinese: Mei-Jia / Tian-Tian; etc. Premium voices (Yuna Premium, etc.) are higher-quality but require network for the initial chunk.

---

## Install

### Homebrew (recommended)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Direct download

[Latest release](https://talkmode.baryon.ai/download/TalkMode-0.4.23.zip) → unzip → drag into `Applications` → first launch macOS may say "from unknown developer", right-click → Open once.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.23.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Auto-update

Sparkle 2 is built in. Once installed (either way), TalkMode checks for updates in the background — open `TalkMode → Check for Updates…` or `Settings → Update` to control it.

### Requirements

- macOS **Sonoma (14.0)** or later
- Apple silicon (M1 / M2 / M3 / M4)
- An LLM provider — at minimum the Claude CLI, Codex CLI, or an OpenAI key

---

## Permissions

Permissions are asked **only the first time you use the feature**:

| Feature | Permission |
|---|---|
| Always-on listening | Microphone, Speech Recognition |
| Gaze tracking (optional) | Camera |
| Right-Option to silence TTS | Input Monitoring |
| Calendar skills | Calendars (Full Access) |
| Email composer | Apple Events |
| `messages.list_recent` skill | Full Disk Access (manually grant in System Settings) |

Nothing is uploaded — STT runs on-device (or Apple's STT server depending on your locale), avatars are local PNGs, and the meeting minutes audio stays in `~/.talk_mode_mac/recordings/`.

---

## Security & Privacy

What TalkMode keeps on your Mac, what leaves it and to where, what is stored on disk, and how API keys and permissions are handled — together with a code-level security review and its findings (no remotely exploitable vulnerability; current limitations disclosed transparently) — is documented in **[SECURITY.md](SECURITY.md)**.

---

## Built with

TalkMode is a SwiftPM-based macOS app. Two third-party Swift packages, the rest is Apple frameworks.

### Swift packages

| Package | Version | What it does here | Why |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | In-app auto-update via signed appcast | Apple-platform standard; used by 1Password, Tower, OBS. EdDSA-signed updates, background download, "Check for Updates…" menu item. |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Opt-in anonymous diagnostics (OpenTelemetry-style logs) | Lets us see *which* phase transitions are stalling in the wild without ever seeing user text — all free-form fields are reduced to length values before send. |

### Apple frameworks

| Framework | Used for |
|---|---|
| **AVFoundation** | `AVAudioEngine` single-tap input, `AVSpeechSynthesizer` TTS (Yuna / Premium / Personal Voice), `AVCaptureSession` camera |
| **Speech** | `SpeechAnalyzer` (macOS 26) or `SFSpeechRecognizer` streaming STT with `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` for head pose → gaze estimation (throttled to ~10 fps) |
| **Accelerate (vDSP)** | 1024-point FFT + Hann window + L2-normalised log-magnitude spectral embedding for on-device speaker diarisation |
| **EventKit** | Calendar read / create / update / delete skills (full-access scope) |
| **ImagePlayground** | macOS 15.1+ avatar generation (falls back to DiceBear PNG via URLSession otherwise) |
| **CoreImage / CoreVideo** | Camera frame conversion for Vision input |
| **AppKit + SwiftUI** | Settings window, multi-tab layout, in-app log view |
| **Combine** | `@Published` state propagation from `ConversationEngine` to all UI |
| **OSLog** | Unified-log diagnostics (`subsystem=app.talkmode`) |
| **SQLite3** | Local alias store + skill memory |
| **UniformTypeIdentifiers** | Avatar file picker |

### Third-party (non-code) assets

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 curated personas per mode (이수민·정아람·박도윤·강예린). Users can override with `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 avatar styles fetched as PNG, cached locally.

---

## Technical background

A few design choices that aren't obvious from the screenshots:

### Multimodal endpointing — why your turn ends fast but not too fast

Standard CJK voice assistants either cut you off on the first "음…" or wait 3 seconds after you actually finish. TalkMode's `AdaptiveTurnDetector` reads four signals at once:

1. **Voice activity** (EnergyVAD on the mic) — silence samples accumulate a budget
2. **Streaming transcript** (SpeechAnalyzer / SFSpeechRecognizer) — Korean 연결 어미 (`-고`, `-는데`) adds 1.2 s; 종결 어미 (`-습니다`, `-요`) subtracts 400 ms; hesitation markers (`음…`, `어…`) add 1.5 s
3. **Speech rate** (chars / sec) — fast talkers get a smaller pause budget
4. **Gaze state** (head yaw / pitch via Vision) — looking at the screen multiplies pause by 0.3-0.65 (waiting), looking away after a complete sentence multiplies by 1.4 *and* arms an immediate fast-fire (you're done)

All four feed one `predictedSilenceMs()` function, clamped to the per-language floor (CJK 900-7000 ms, English 300-3000 ms). No parallel timers, no race conditions.

### Always-on audio is load-bearing

`AudioInputStream` starts `AVAudioEngine` **once per session and never stops it** until the session ends. Earlier code stopped/restarted on every phase boundary; that pattern accumulated bugs on macOS 26 (`couldn't get default input device, ID = 0`, `format.sampleRate == inputHWFormat.sampleRate` aborts). Now one tap broadcasts buffers to N consumers (VAD, STT, barge-in detector, meeting recorder, level meter) via `AsyncStream`.

### On-device speaker diarisation

Meeting Minutes mode uses Apple Accelerate vDSP to compute a **24-dimensional L2-normalised log-magnitude spectral embedding** (FFT 1024, Hann window, hop 256) per utterance. Cosine similarity > 0.82 = same speaker as before, otherwise assign a new ID. No model download, no API call. Speakers persist across meetings — relabel "Speaker 1" → "지원" once, it sticks.

### LLM is BYOK

`AssistantClient` is one protocol with eight implementations. The CLI providers (`CLIAssistantClient` for `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) launch a subprocess in `~/.talk_mode_mac/work/` with a sandboxed `currentDirectoryURL`, stream stdout sentence-by-sentence into `TTSQueue`, and never see an API key from TalkMode itself. You bring whatever subscription you already pay for.

### Privacy-by-default diagnostics

The opt-in PostHog telemetry only forwards **categorised events**, not the underlying text:

- `turn / llm / tts / minutes / alias` → reduced to `[category] len=N` before send
- `skill` → keeps `skill_id`, drops `args`
- `fsm / endpointing / session / error / update` → metadata only, no transcript

Verify in `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (visible in the binary's strings if you don't trust me).

### Markdown stripped for TTS, rendered for chat

LLMs love `**bold**` and `### headings`. AVSpeechSynthesizer reads them as "asterisk asterisk bold asterisk asterisk". `MarkdownStripper.strip(_:)` cleans the text right before it enters `TTSQueue` (chat bubble keeps the original via `AttributedString(markdown:)`).

### Modular SwiftPM split

Two reusable targets live alongside the main app:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — pure-Foundation `timeout(for:localeID:)` function with 14 unit tests. Per-language `sec/char × 4` multiplier with a floor; can't be silently regressed by an unrelated commit.
- **`Endpointing`** (`Sources/Endpointing/`) — owns `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. No AVFoundation / Vision dependency. 7 unit tests covering look-away handoff, mic-active reject, latch clearing.

`swift test --filter EndpointingTests` and `swift test --filter SpeechWatchdogTests` each run against a tiny module — fast iteration.

### State machine

Every phase transition (`idle → listening → thinking → speaking → listening …`) goes through one `PhaseStateMachine.transition(to:reason:)`. Illegal transitions are rejected with a logged reason. Surfaces in the Diagnostics tab's timeline so when something is stuck, you can see *which* edge refused to fire.

---

## Community

- **Discussions** — questions, ideas, feature requests → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — bug reports → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## License

The compiled app is free to use, personal or commercial — the release ZIPs contain a single signed `.app` bundle.

The source in this repository is licensed under the **GNU Affero General Public License v3.0** — see [LICENSE](LICENSE). You may use, study, modify, and redistribute it, but any modified version — including one offered as a network service — must remain open under the same AGPL-3.0 license. Baryon Labs holds the copyright; if you need terms outside AGPL-3.0 (e.g. a commercial license), ask via **Discussions**.

Made in Seoul by [Baryon Labs](https://baryon.ai).

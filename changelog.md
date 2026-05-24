# Changelog

All notable changes to **TalkMode**. Newest release first. Versions follow
`MAJOR.MINOR.PATCH`; the app auto-updates via Sparkle from
[appcast.xml](https://talkmode.baryon.ai/appcast.xml).

## 0.4.18 — 2026-05-24

### Fixed
- LLM 요청 fail → 퇴근 → 출근 빠르게 누르면 앱이 응답없음 되던 freeze 수정.
  setEnabled() 가 startSession/endSession Task 를 unawaited 로 spawn 해서
  두 task 가 동시에 AVAudioEngine 을 시작하려다 AVAudioSession 충돌로 hang
  됐다. 단일 sessionTask 체인으로 직렬화.

## 0.4.17 — 2026-05-24

### Fixed
- 출근(Start) / 퇴근(Stop) 시 앱이 즉시 응답없음 되던 freeze 수정.
  AudioInputStream.start()/stop() 의 engine.prepare/installTap/start/
  removeTap/stop 가 모두 @MainActor 동기였고 macOS 26 의 TCC + privacy-
  indicator 처리로 호출당 300–800ms 메인을 잠궜다. 전체 시퀀스를 백그라운드
  큐로 분리.

### Changed
- Barge-in 기본 ON. 에이전트가 답할 때 사용자가 350ms+ 말하면 TTS 즉시
  중단. 자연 대화의 기본값. 끄려면 설정 → Barge-in.

## 0.4.16 — 2026-05-24

### Fixed
- 퇴근(stop) / mode switch 시 main thread freeze 수정 — AudioRecorder.close()가
  writeQueue.sync로 디스크 finalize를 main에서 기다리던 패턴을 비동기 dispatch로
  교체. Minutes 모드를 길게 한 뒤일수록 freeze가 길었음.

### Changed
- Voice picker가 Premium / Enhanced / Standard SwiftUI Section으로 그룹화.
  Premium 음성이 맨 위에 모여 식별 쉬워짐.

## 0.4.15 — 2026-05-22

### Fixed
- Hosted Baryon backend was regressing to English replies for non-Korean
  / non-English locales. System prompt now resolves the BCP-47 locale to
  the user-facing language name (35 locales covered + `Locale` fallback)
  so a Japanese / Spanish / Vietnamese user always gets answers in their
  language.

### Changed
- System prompt also asks for voice-friendly responses (1–3 sentences,
  no markdown / lists / code blocks) so qwen3-coder stops returning
  fenced code blocks that TTS has to strip.

## 0.4.14 — 2026-05-22

### Added
- Hosted Baryon AI default backend: first-time users get 30 free calls per
  device with no Claude CLI / Codex CLI / OpenAI setup needed. Switch in
  `Settings → LLM provider` after the quota.

### Docs
- Install guide now walks Homebrew prereq + macOS 15+ Gatekeeper
  "Open Anyway" steps — clears the "확인되지 않은 개발자" block first-time
  users were getting stuck on.

## 0.4.13 — 2026-05-20

### Fixed
- Meeting Minutes no longer pegs the CPU — the speaker classifier FFT
  runs on a dedicated background queue.
- Minutes transcript view stops re-rendering on every STT chunk
  (MinutesStore isolation).
- Tool calls (camera vision, calendar, mail, …) no longer get blocked by
  the model's "I need permission" / "I cannot do this in this
  environment" responses — the tool manifest now overrides that instinct.

## 0.4.12 — 2026-05-20

### Fixed
- Tool calls (notably "describe what the camera sees") leaked raw JSON
  into the chat bubble when the assistant prepended a sentence before
  the tool call; the skill now fires reliably.

## 0.4.11 — 2026-05-18

### Changed
- Gaze tracking now runs through a debounced state machine, so a brief
  glance away no longer ends your turn early.

## 0.4.10 — 2026-05-18

### Added
- Camera vision: ask the assistant to describe what the camera sees and
  it captures a still frame and describes it.

## 0.4.9 — 2026-05-17

### Fixed
- The gaze camera now reliably turns on whenever you start speaking. The
  resume was gated on the conversation phase and could be silently
  skipped.

## 0.4.8 — 2026-05-17

### Added
- The voice picker now suggests downloading higher-quality **Premium**
  voices when none is installed for the current speech language.

### Changed
- Camera-gaze resume now records why it was skipped (conversation phase,
  camera-session state) in the **Diagnostics** tab — instrumentation for a
  "the camera doesn't turn on when I speak" report.

## 0.4.7 — 2026-05-17

### Fixed
- Crash when restarting a session (clock-out then clock-in) with the gaze
  camera enabled. Configuring the `AVCaptureSession` on the main thread
  while it started on a background thread aborted the process; all session
  work — configure, start/stop, pause/resume, preview attachment — is now
  serialized on one queue.

## 0.4.6 — 2026-05-17

### Changed
- In-app **Discussions**, bug-report and share links now point to the
  public `talkmode-app` repository.

## 0.4.5 — 2026-05-17

### Added
- **Settings → Voice:** pick a specific Apple voice for the current speech
  language, or leave it on Automatic.

### Fixed
- Camera gaze now resumes on **every** turn — previously it activated only
  on the first utterance of a session.
- Auto-update feed URL. Sparkle update checks failed because the old feed
  URL no longer resolved; it now points at `talkmode.baryon.ai`.

## 0.4.4 — 2026-05-17

### Added
- The interface palette adapts to the system **Light / Dark** appearance —
  warm cream under Light, warm charcoal under Dark.

## 0.4.2 — 2026-05-16

### Added
- Full UI translation across all **20 supported languages**, with the
  README available in every language.

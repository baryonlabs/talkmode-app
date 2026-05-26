# Changelog

All notable changes to **TalkMode**. Newest release first. Versions follow
`MAJOR.MINOR.PATCH`; the app auto-updates via Sparkle from
[appcast.xml](https://talkmode.baryon.ai/appcast.xml).

## Website — 2026-05-26

### Added
- `web/404.html` — branded dark-mode 404 page. PR #2 by @Shinyvedaas
  added the initial light-mode design; we then matched it to the site
  palette + added PostHog/GA snippets + `noindex` so the not-found
  page doesn't get indexed.
- SEO pass: robots.txt + sitemap.xml (with hreflang for 20 languages),
  per-page canonical, Open Graph + Twitter Cards, Schema.org
  SoftwareApplication + FAQPage JSON-LD, llms.txt (per llmstxt.org).
- FAQ section on the homepage (6 questions, mirrored as FAQPage
  structured data for SERP rich results).
- Free-for-work values strip above the footer.
- Google Analytics (gtag.js, G-Z1WQBLGEZL) alongside the existing
  PostHog product analytics.
- Install guide: full step-by-step `/install` page with mocked-up
  macOS dialogs and a real placeholder slot for user-captured
  screenshots (made obsolete by 0.4.23's Apple notarization — Step 3
  was removed).
- Signup page `/signup` with 4-question survey and newsletter opt-in.

### Changed
- Homepage signup CTA removed (per request); `/signup` page itself
  stays live for users who navigate directly.
- All 'unidentified developer' / Gatekeeper-unblock guidance removed
  from index.html / install.html / 18 translated readmes once 0.4.23
  notarization made it obsolete.
- 18 translated readmes get a callout above the Install section
  pointing at the English / Korean docs for the newest features
  (Translate, Obsidian sync, local LLM).

## 0.4.36 — 2026-05-26

### Added
- Translate-mode locale picker right in the conversation tab. Flip
  source / target language between turns without going to
  Settings → Language. Settings still owns the canonical control;
  this is just the in-place shortcut the translate workflow wanted.

## 0.4.35 — 2026-05-26

### Fixed
- **Camera-off freeze (CameraStream lock re-entrant deadlock).** Same
  shape as the AudioInputStream bug fixed in 0.4.30 — `stop()` held
  `self.lock` while calling `continuation.finish()`, whose
  `onTermination` closure tries to re-acquire the lock. NSLock is
  non-recursive, so the main thread waited on its own held mutex
  forever. Toggling the camera off was a reliable repro.
  Fix: snapshot continuations under the lock, release, then finish().
  Diagnosed in seconds via `freeze-dump.sh`.

## 0.4.34 — 2026-05-26

### Changed
- AEC-on still silenced STT in some setups (the 0.4.26 regression).
  Two changes that should either fix it or pin the exact failing layer:
  - Explicit reset of `isVoiceProcessingInputMuted` and
    `isVoiceProcessingBypassed` so a stuck OS-side toggle doesn't mute
    input when the host turns Voice Processing on.
  - Log the input format before / after VP, the muted / bypassed / AGC
    state, and the RMS energy of the first 10 buffers so
    `freeze-dump.sh` can tell us which layer is wrong on a hung setup.

## 0.4.33 — 2026-05-26

### Fixed
- **Single 안녕 triggers infinite echo loop with barge-in on.** When
  AEC was off and barge-in on, the assistant's TTS leaked through
  laptop speakers into the mic, STT turned the leak into another
  '안녕' transcript, turn-detector fired, repeat.
  Barge-in does NOT need STT transcripts to work — `BargeInDetector`
  watches raw VAD energy. STT transcripts are now suppressed
  unconditionally while phase == .speaking; user-initiated barge-in
  still cuts the assistant off the moment the VAD sees real voice
  activity.

## 0.4.32 — 2026-05-26

### Changed
- Free hosted-backend quota raised from 30 to 1000 calls per device.
  Server-side rate limit was bumped; client mirror now matches.
  Existing users capped at 30 from the old build automatically get 970
  calls back — the lock is `max(0, maxFree - count)` and `maxFree` is
  now 1000.

## 0.4.31 — 2026-05-26

### Fixed
- `freeze-dump.sh` reported the wrong bundle version when the running
  TalkMode lived outside `/Applications`. The helper now resolves the
  .app from the live PID's binary path via `ps` and reads that
  bundle's Info.plist directly. During 0.4.30's debugging session this
  helper bug misled us for an hour into thinking the user was on 0.4.12
  when they were actually running a hand-extracted 0.4.24 from `/tmp`.

## 0.4.30 — 2026-05-26

### Fixed
- ★ **The actual root cause behind every '응답 없음' freeze we have
  been guessing around since 0.4.18.** Freeze-dump sample finally
  pinned it:

  ```
  ConversationEngine.endSession
    → AudioInputStream.stop                    (AudioInputStream.swift:135)
      → AsyncStream.Continuation.finish()
        → closure in AudioInputStream.subscribe (line 174)
          → _pthread_mutex_firstfit_lock_slow  ← DEADLOCK
  ```

  `stop()` was holding `self.lock` while iterating `continuations.values`
  and calling `continuation.finish()` on each. `finish()` synchronously
  invokes the `onTermination` closure that `subscribe()` set up — that
  closure also calls `self.lock.lock()`. NSLock is non-recursive, so the
  same thread waiting on its own held mutex hangs forever. Every
  'assistant request failed → 퇴근 → 출근 응답없음' freeze report we
  tried to band-aid in 0.4.22 / 0.4.24 / 0.4.28 was a symptom of this
  single deadlock.
  Fix: snapshot continuations under the lock, release the lock, then
  call `finish()`. `onTermination` is free to acquire the lock — we
  are not holding it anymore.

## 0.4.29 — 2026-05-26

### Added
- `~/.talk_mode_mac/freeze-dump.sh` auto-installed on every launch.
  When the user hits a freeze, they run
  `bash ~/.talk_mode_mac/freeze-dump.sh` in a second terminal — it
  captures `/usr/bin/sample` (5s), `/usr/bin/log show` (last 2 min),
  recent logs/ into a single timestamped file under
  `~/.talk_mode_mac/diagnostics/`. The maintainer reads that file and
  gets the exact stuck call site instead of guessing.

## 0.4.28 — 2026-05-24

### Fixed
- Two compounding patches for the 'request failed twice then 출근 hangs'
  loop:
  - `AudioInputStream.stop` and `CameraStream.stop` get 3-second timeouts
    so a stuck background `stopRunning` / `engine.stop` doesn't block
    the session task chain forever. Defence-in-depth — 0.4.30 ended up
    being the real fix.
  - `fail()` now cancels `llmTask` and `ttsQueue` before the auto-
    teardown so repeated failures don't accumulate stale streaming work.

## 0.4.27 — 2026-05-24

### Fixed
- 0.4.26's always-on `setVoiceProcessingEnabled(true)` silenced STT in
  some setups — mic level showed activity but live transcript stayed
  empty. AEC is now opt-in via Settings → Behavior → 'Echo cancellation
  (AEC)'. Default OFF restores 0.4.25 behavior.

## 0.4.26 — 2026-05-24

### Added
- Acoustic Echo Cancellation via Apple's Voice Processing IO unit. The
  speaker output signal — including our own TTS — is subtracted from
  the mic input. Always-on (later reverted to opt-in in 0.4.27 after
  user-reported regressions).

## 0.4.25 — 2026-05-24

### Fixed
- 'assistant request failed' left 출근 / 퇴근 buttons unresponsive.
  `fail()` set phase to .error but left `isEnabled = true`; UI's 출근
  is gated on `!isEnabled`. Now `fail()` also calls `setEnabled(false)`
  so the session tears down and 출근 lights up again.

## 0.4.24 — 2026-05-24

### Fixed
- Freeze on 출근→퇴근→출근 (camera race attempted fix). `CameraStream.stop`
  made async + endSession awaits it. Defence in depth — the actual root
  cause turned out to be the AudioInputStream deadlock fixed in 0.4.30.

## 0.4.23 — 2026-05-26

### Added
- Apple notarization. Bundle is signed with our Developer ID Application
  cert and the notarization ticket is stapled onto the .app — first
  launch no longer triggers the 'unidentified developer' Gatekeeper
  warning. Inside-out signing of Sparkle.framework now covers Autoupdate
  + the Mach-Os inside Downloader.xpc / Installer.xpc / Updater.app.

### Changed
- Install guide drops Step 3 (Gatekeeper unblock) — installation is
  now two steps: Homebrew + TalkMode.

## 0.4.22 — 2026-05-24

### Fixed
- LLM 요청 fail → 퇴근 → 출근 시 응답없음 회귀. 0.4.18 의 sessionTask
  직렬화로 task 순서는 잡혔지만 각 endSession 가 fire-and-forget 으로
  background cleanup 을 안 기다려, 새 startSession 의 engine.start() 가
  이전 engine.stop() 와 같은 AVAudioSession 에서 race 되어 hang 했다.
  AudioInputStream.stop() async 화 + endSession 가 audioInput / stt.stop
  모두 await.

### Added
- MLX provider (Apple Silicon · mlx_lm.server). 설정 → 어시스턴트 → MLX.
  기본 http://localhost:8080 + mlx-community/Qwen2.5-7B-Instruct-4bit.

## 0.4.21 — 2026-05-24

### Added
- Obsidian vault 자동 동기. 설정 → Obsidian 에서 vault 경로 선택 +
  4 채널(회의록/일반대화/Memory/통역) 토글. {vault}/{subfolder}/ 하위에
  자동으로 markdown 저장. plugin / CLI 불필요 — direct path write.

## 0.4.20 — 2026-05-24

### Added
- 통역 모드 (Translate). 사용자가 언어 A 로 말하면 TalkMode 가 언어 B 로
  말함. 설정 → 언어 에서 source / target locale 선택. STT/TTS locale 이
  effectiveSTTLocale / effectiveTTSLocale computed property 로 분기.
  Translate 모드일 때 PersonaStore.systemPrompt 가 persona/skill/nemotron
  overlay 전부 단락하고 순수 인터프리터 prompt 만 출력.

## 0.4.19 — 2026-05-24

### Added
- 로컬 LLM 지원: LM Studio (기본 http://localhost:1234) 와 Ollama (기본
  http://localhost:11434) 가 신규 AssistantProvider 로 추가. 완전 오프라인
  음성 비서가 가능해짐. 단일 LocalOpenAICompatClient 가 둘 다 처리
  (OpenAI 호환 /v1/chat/completions). 설정 → 어시스턴트 에서 둘 중 선택
  + base URL / model 자유 변경.
- Info.plist 에 NSAllowsLocalNetworking 추가 — http://localhost 호출이
  ATS 에 막히지 않도록.

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

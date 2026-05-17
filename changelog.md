# Changelog

All notable changes to **TalkMode**. Newest release first. Versions follow
`MAJOR.MINOR.PATCH`; the app auto-updates via Sparkle from
[appcast.xml](https://talkmode.baryon.ai/appcast.xml).

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

<div align="center">

# TalkMode

**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | 한국어 | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> TalkMode 공개 저장소 — 소스, **릴리스**, **이슈**, **토론**.
> 앱이 사용자의 데이터를 정확히 어떻게 다루는지는 **[SECURITY.md](../SECURITY.md)** 를 참고하세요.

---

## TalkMode란

TalkMode는 맥 미니(또는 모든 Apple silicon Mac)를 챗봇이 아니라 동료처럼 행동하는 **실시간 한국어 음성 비서**로 바꿔 줍니다.

- 한국어에 맞춰진 적응형 엔드포인터(시선 + 음성 + 전사)로 **1초 미만의 턴 전환**
- **말을 걸어 끼어들거나, 시선을 돌려 마무리** — 단순한 침묵 타이머가 아닌 멀티모달 신호
- **4가지 모드**: 대화 · 회의록 · 브레인스토밍(호응 중심) · 심리상담(경청 중심)
- 회의록을 위한 **on-device 화자 분리**(Apple Accelerate vDSP)
- **스킬**: 캘린더 읽기, 메일 작성, 문자 읽기, CPU/RAM 조회, 메모리 저장, 별칭 학습
- **8개 LLM 제공자**: Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLI + OpenAI + Mock
- **20개 UI 언어**, 50개 이상 STT 로케일
- **페르소나**: 언어별 Soul + Contract 파일, 그리고 NVIDIA의 Nemotron-Personas-Korea에서 선별한 세트
- DiceBear(10가지 스타일), ImagePlayground(macOS 15.1+), 또는 직접 만든 이미지로 **커스텀 아바타**
- **기본적으로 프라이버시 우선**: (a) 사용자가 선택한 LLM 제공자와 (b) 모든 자유 텍스트를 길이 값으로 치환한 익명 진단 정보를 제외하고는 어떤 것도 Mac을 떠나지 않습니다

---

## 스크린샷

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="대화 탭 — 메인" /></a><br/>
      <sub><b>대화 탭</b> — 비서 아바타, 시선 추적용 선택 카메라 미리보기, 마이크 레벨 오버레이, 실시간 채팅. 주황색 "최근" 칩은 현재 무드를 보여줍니다.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="대화 탭 — 대화 진행" /></a><br/>
      <sub><b>실시간 대화</b> — 버블에 마크다운 렌더링, STT 자동 구두점, 스킬이 준비되면 "출발 알림" 배지가 나타납니다.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="설정 — 비서 인격" /></a><br/>
      <sub><b>설정 — 페르소나</b> — UI / STT 언어, 아바타 스타일과 성별, ImagePlayground 생성, 그리고 모든 답변의 틀을 잡는 실시간 <code>soul.md</code> 계약.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="진단 — 타임라인" /></a><br/>
      <sub><b>진단</b> — 페이즈, yaw/pitch, 시선, STT/얼굴/CPU 수치, 그리고 모든 엔드포인팅 결정의 롤링 타임라인. 타임라인을 끄면 CPU를 몇 % 절약할 수 있습니다.</sub>
    </td>
  </tr>
</table>

---

## 지원 언어

TalkMode는 **UI 언어**(메뉴, 버튼, 오류 메시지의 언어)와 **음성 언어**(비서가 전사하고 답변하는 언어)를 분리합니다. 둘은 독립적으로 설정할 수 있습니다 — 독일어 UI를 보면서 비서와 한국어로 대화하세요.

### UI 언어 (20개)

**설정 → 언어 → UI 언어**에서 설정합니다. 모든 언어가 완전히 번역되어 있습니다 — 메뉴, 버튼, 설정, 스킬 설명, 진단 라벨 전부.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### 음성 / 대화 언어

Mac의 Speech 프레임워크가 지원하는 모든 언어 — macOS Sonoma+에서는 보통 **50~60개 로케일**입니다. **설정 → 언어 → 음성 인식 언어**에서 설정하며, 선택기는 `SFSpeechRecognizer.supportedLocales()`가 반환하는 모든 로케일을 나열하고 4개 CJK + 영어 로케일을 맨 위에 고정합니다.

기본 macOS Sonoma+ 설치에서 항상 사용 가능한 언어(일부 목록 — 사용자 Mac에는 더 많을 수 있습니다):

| 지역 | 로케일 |
|---|---|
| **동아시아** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **영어** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **서유럽** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **중부 / 동유럽** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **그리스어 / 히브리어** | Ελληνικά · עברית |
| **중동 & 남아시아** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **동남아시아** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **기타** | Türkçe · Русский · Català · Қазақ |

> 정확한 목록은 OS 버전과 **시스템 설정 → 키보드 → 받아쓰기**에서 다운로드한 받아쓰기 언어에 따라 달라집니다. TalkMode는 실행 시 실시간 목록을 읽습니다 — 정확한 목록은 사용자 Mac에서 선택기를 열어 확인하세요.

### TTS 음성

음성 *출력*은 `AVSpeechSynthesizer`를 사용합니다 — macOS Siri / 받아쓰기와 동일한 엔진입니다. 음성은 **시스템 설정 → 손쉬운 사용 → 콘텐츠 말하기 → 시스템 음성 → 음성 관리**에서 다운로드합니다. 한국어: Yuna / Sora; 영어: Samantha / Alex / Daniel / Karen / Moira; 일본어: Kyoko / O-Ren; 중국어: Mei-Jia / Tian-Tian 등. 프리미엄 음성(Yuna Premium 등)은 더 높은 품질이지만 첫 청크에 네트워크가 필요합니다.

---

## 설치

설치는 두 단계입니다.

### 1단계 — Homebrew 설치 (한 번만)

Homebrew는 macOS용 패키지 관리자입니다. 터미널(Spotlight에서 "터미널" 검색)에서 `brew --version` 을 입력했을 때 버전이 나오면 이미 설치된 상태이니 2단계로 건너뛰세요.

처음이라면 터미널에서:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

설치 중 Mac 로그인 비밀번호와 Command Line Tools 동의 화면이 뜹니다. 안내대로 진행하세요(보통 5–15분 소요). 끝나면 터미널을 한 번 닫았다 다시 엽니다.

> 자세한 한국어 가이드는 [Homebrew 공식 사이트](https://brew.sh/index_ko) 또는 [블로그 가이드](https://velog.io/@nancy_yeonjeong/맥북Mac-터미널-Brew-설치)를 참고하세요.

### 2단계 — TalkMode 설치

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

`Applications` 폴더에 `TalkMode.app` 가 생깁니다. Launchpad나 Spotlight에서 "TalkMode" 검색으로 실행하세요.

### 직접 다운로드 (Homebrew 없이)

[최신 릴리스](https://talkmode.baryon.ai/download/TalkMode-0.4.35.zip) → 압축 해제 → `Applications`로 드래그.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.35.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### 자동 업데이트

Sparkle 2가 내장되어 있습니다. 첫 실행 차단을 한 번 푼 뒤에는 백그라운드 업데이트가 다시 차단되지 않습니다 — `TalkMode → 업데이트 확인…` 또는 `설정 → 업데이트`에서 제어하세요.

### 요구 사항

- macOS **Sonoma (14.0)** 이상 — Sonoma / Sequoia (15) / Tahoe (26) 모두 동작 확인
- Apple silicon (M1 / M2 / M3 / M4)
- LLM 제공자 — **기본값은 Baryon AI 호스팅(설정 불필요 · 무료 1000회)**. 1000회 이후에는 `설정 → LLM 제공자` 에서 Claude CLI · Codex CLI · OpenAI 키 중 하나로 전환하세요.

---

## 권한

권한은 **해당 기능을 처음 사용할 때만** 요청됩니다:

| 기능 | 권한 |
|---|---|
| 상시 청취 | 마이크, 음성 인식 |
| 시선 추적 (선택) | 카메라 |
| 오른쪽 Option으로 TTS 끄기 | 입력 모니터링 |
| 캘린더 스킬 | 캘린더 (전체 접근) |
| 이메일 작성기 | Apple Events |
| `messages.list_recent` 스킬 | 전체 디스크 접근 (시스템 설정에서 수동 부여) |

업로드되는 것은 없습니다 — STT는 on-device(또는 로케일에 따라 Apple의 STT 서버)에서 실행되고, 아바타는 로컬 PNG이며, 회의록 오디오는 `~/.talk_mode_mac/recordings/`에 남습니다.

---

## 보안 & 프라이버시

TalkMode가 Mac에 보관하는 것, 무엇이 어디로 나가는지, 디스크에 저장되는 것, API 키와 권한이 어떻게 처리되는지 — 코드 수준 보안 검토 및 그 결과(원격으로 악용 가능한 취약점 없음; 현재 한계는 투명하게 공개)와 함께 — 모두 **[SECURITY.md](../SECURITY.md)** 에 문서화되어 있습니다.

---

## 사용 기술

TalkMode는 SwiftPM 기반 macOS 앱입니다. 서드파티 Swift 패키지 2개를 제외한 나머지는 Apple 프레임워크입니다.

### Swift 패키지

| 패키지 | 버전 | 여기서 하는 일 | 이유 |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | 서명된 appcast를 통한 인앱 자동 업데이트 | Apple 플랫폼 표준; 1Password, Tower, OBS에서 사용. EdDSA 서명 업데이트, 백그라운드 다운로드, "업데이트 확인…" 메뉴 항목. |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | 옵트인 익명 진단(OpenTelemetry 스타일 로그) | 사용자 텍스트를 전혀 보지 않고도 실제 환경에서 *어떤* 페이즈 전환이 멈추는지 파악할 수 있게 합니다 — 모든 자유 형식 필드는 전송 전 길이 값으로 축소됩니다. |

### Apple 프레임워크

| 프레임워크 | 용도 |
|---|---|
| **AVFoundation** | `AVAudioEngine` 단일 탭 입력, `AVSpeechSynthesizer` TTS (Yuna / Premium / Personal Voice), `AVCaptureSession` 카메라 |
| **Speech** | `SpeechAnalyzer` (macOS 26) 또는 `SFSpeechRecognizer` 스트리밍 STT, `addsPunctuation` 적용 |
| **Vision** | 머리 자세 → 시선 추정을 위한 `VNDetectFaceLandmarksRequest` (약 10 fps로 스로틀) |
| **Accelerate (vDSP)** | on-device 화자 분리를 위한 1024 포인트 FFT + Hann 윈도 + L2 정규화 로그 크기 스펙트럼 임베딩 |
| **EventKit** | 캘린더 읽기 / 생성 / 수정 / 삭제 스킬 (전체 접근 범위) |
| **ImagePlayground** | macOS 15.1+ 아바타 생성 (그 외에는 URLSession을 통한 DiceBear PNG로 폴백) |
| **CoreImage / CoreVideo** | Vision 입력을 위한 카메라 프레임 변환 |
| **AppKit + SwiftUI** | 설정 창, 멀티 탭 레이아웃, 인앱 로그 보기 |
| **Combine** | `ConversationEngine`에서 모든 UI로의 `@Published` 상태 전파 |
| **OSLog** | 통합 로그 진단 (`subsystem=app.talkmode`) |
| **SQLite3** | 로컬 별칭 저장소 + 스킬 메모리 |
| **UniformTypeIdentifiers** | 아바타 파일 선택기 |

### 서드파티 (비코드) 자산

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 모드별 선별된 페르소나 4종 (이수민·정아람·박도윤·강예린). 사용자는 `nemotron-extras.json`으로 덮어쓸 수 있습니다.
- **[DiceBear](https://www.dicebear.com)** — PNG로 가져와 로컬에 캐시되는 10가지 아바타 스타일.

---

## 기술적 배경

스크린샷만으로는 명확하지 않은 몇 가지 설계 선택:

### 멀티모달 엔드포인팅 — 턴이 빠르되 너무 빠르지 않게 끝나는 이유

표준 CJK 음성 비서는 첫 "음…"에서 말을 끊거나 실제로 끝낸 뒤 3초를 기다립니다. TalkMode의 `AdaptiveTurnDetector`는 네 가지 신호를 동시에 읽습니다:

1. **음성 활동** (마이크의 EnergyVAD) — 침묵 샘플이 예산을 누적
2. **스트리밍 전사** (SpeechAnalyzer / SFSpeechRecognizer) — 한국어 연결 어미(`-고`, `-는데`)는 1.2초 추가; 종결 어미(`-습니다`, `-요`)는 400ms 차감; 망설임 표지(`음…`, `어…`)는 1.5초 추가
3. **말 속도** (초당 글자 수) — 빠르게 말하는 사람은 더 작은 침묵 예산
4. **시선 상태** (Vision을 통한 머리 yaw / pitch) — 화면을 보면 침묵에 0.3~0.65 곱(대기), 완전한 문장 뒤 시선을 돌리면 1.4를 곱하고 *동시에* 즉시 빠른 발화를 준비(끝났음)

네 가지 모두 하나의 `predictedSilenceMs()` 함수로 들어가며, 언어별 하한(CJK 900~7000ms, 영어 300~3000ms)으로 클램프됩니다. 병렬 타이머 없음, 경쟁 조건 없음.

### 상시 오디오가 핵심

`AudioInputStream`은 `AVAudioEngine`을 **세션당 한 번 시작하고 세션이 끝날 때까지 절대 멈추지 않습니다**. 이전 코드는 모든 페이즈 경계마다 멈추고 다시 시작했는데, 그 패턴은 macOS 26에서 버그를 누적시켰습니다(`couldn't get default input device, ID = 0`, `format.sampleRate == inputHWFormat.sampleRate` 중단). 이제 하나의 탭이 `AsyncStream`을 통해 N개 소비자(VAD, STT, 끼어들기 감지기, 회의 녹음기, 레벨 미터)에 버퍼를 브로드캐스트합니다.

### on-device 화자 분리

회의록 모드는 Apple Accelerate vDSP를 사용해 발화마다 **24차원 L2 정규화 로그 크기 스펙트럼 임베딩**(FFT 1024, Hann 윈도, hop 256)을 계산합니다. 코사인 유사도 > 0.82이면 이전과 같은 화자, 아니면 새 ID를 부여합니다. 모델 다운로드 없음, API 호출 없음. 화자는 회의 간 유지됩니다 — "화자 1" → "지원"으로 한 번 다시 라벨링하면 그대로 유지됩니다.

### LLM은 BYOK

`AssistantClient`는 8개 구현을 가진 하나의 프로토콜입니다. CLI 제공자(`claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`용 `CLIAssistantClient`)는 샌드박스화된 `currentDirectoryURL`로 `~/.talk_mode_mac/work/`에서 서브프로세스를 실행하고, stdout을 문장 단위로 `TTSQueue`에 스트리밍하며, TalkMode 자체에서 API 키를 보는 일은 없습니다. 이미 결제 중인 구독을 그대로 가져오면 됩니다.

### 기본적으로 프라이버시 우선인 진단

옵트인 PostHog 텔레메트리는 기반 텍스트가 아니라 **분류된 이벤트**만 전달합니다:

- `turn / llm / tts / minutes / alias` → 전송 전 `[category] len=N`으로 축소
- `skill` → `skill_id`는 유지, `args`는 제거
- `fsm / endpointing / session / error / update` → 메타데이터만, 전사 없음

`Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift`에서 확인하세요(저를 못 믿겠으면 바이너리 strings에서도 보입니다).

### 마크다운은 TTS용으로 제거, 채팅용으로 렌더링

LLM은 `**bold**`와 `### headings`를 좋아합니다. AVSpeechSynthesizer는 이를 "별표 별표 굵게 별표 별표"로 읽습니다. `MarkdownStripper.strip(_:)`은 텍스트가 `TTSQueue`에 들어가기 직전에 정리합니다(채팅 버블은 `AttributedString(markdown:)`을 통해 원본을 유지).

### 모듈형 SwiftPM 분리

메인 앱 옆에 재사용 가능한 두 개의 타깃이 있습니다:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — 14개 단위 테스트가 있는 순수 Foundation `timeout(for:localeID:)` 함수. 하한이 있는 언어별 `sec/char × 4` 곱셈자; 무관한 커밋이 조용히 회귀시킬 수 없습니다.
- **`Endpointing`** (`Sources/Endpointing/`) — `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`를 소유합니다. AVFoundation / Vision 의존성 없음. 시선 전환, 마이크 활성 거부, 래치 해제를 다루는 7개 단위 테스트.

`swift test --filter EndpointingTests`와 `swift test --filter SpeechWatchdogTests`는 각각 작은 모듈에 대해 실행됩니다 — 빠른 반복.

### 상태 머신

모든 페이즈 전환(`idle → listening → thinking → speaking → listening …`)은 하나의 `PhaseStateMachine.transition(to:reason:)`을 거칩니다. 잘못된 전환은 로그된 이유와 함께 거부됩니다. 진단 탭의 타임라인에 표시되므로 무언가 멈췄을 때 *어떤* 엣지가 발화를 거부했는지 볼 수 있습니다.

---

## 커뮤니티

- **토론** — 질문, 아이디어, 기능 요청 → https://github.com/baryonlabs/talkmode-app/discussions
- **이슈** — 버그 신고 → https://github.com/baryonlabs/talkmode-app/issues
- **이메일** — support@baryon.ai

## 라이선스

컴파일된 앱은 개인용이든 상업용이든 무료로 사용할 수 있습니다 — 릴리스 ZIP에는 서명된 단일 `.app` 번들이 들어 있습니다.

이 저장소의 소스는 **GNU Affero General Public License v3.0**으로 라이선스됩니다 — [LICENSE](../LICENSE)를 참고하세요. 사용, 학습, 수정, 재배포할 수 있지만, 수정된 버전 — 네트워크 서비스로 제공되는 것을 포함 — 은 동일한 AGPL-3.0 라이선스로 공개되어야 합니다. 저작권은 Baryon Labs가 보유합니다; AGPL-3.0 외의 조건(예: 상업용 라이선스)이 필요하면 **토론**을 통해 문의하세요.

[Baryon Labs](https://baryon.ai)가 서울에서 만들었습니다.

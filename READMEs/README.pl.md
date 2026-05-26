<div align="center">

# TalkMode

**Mac mini zamieniony w prawdziwego asystenta — natychmiastowy głos po koreańsku, na urządzeniu, na Twoich zasadach.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | Polski | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Publiczne repozytorium TalkMode — kod źródłowy, **Releases**, **Issues** i **Discussions**.
> Zobacz **[SECURITY.md](../SECURITY.md)**, aby dokładnie poznać sposób, w jaki aplikacja obsługuje Twoje dane.

---

## Czym jest TalkMode

TalkMode zamienia Mac mini (lub dowolnego Maca z procesorem Apple silicon) w **koreańskiego asystenta głosowego działającego w czasie rzeczywistym**, który zachowuje się jak współpracownik, a nie chatbot.

- **Wymiana tur w czasie poniżej sekundy** dzięki adaptacyjnemu detektorowi zakończenia wypowiedzi dostrojonemu do języka koreańskiego (wzrok + głos + transkrypcja)
- **Mów, aby przerwać, lub odwróć wzrok, aby zakończyć** — wskazówki multimodalne, nie tylko liczniki ciszy
- **4 tryby**: rozmowa · protokół spotkania · burza mózgów (nacisk na potakiwanie) · poradnictwo psychologiczne (nacisk na słuchanie)
- **Rozpoznawanie mówców na urządzeniu** dla protokołów spotkań (Apple Accelerate vDSP)
- **Umiejętności**: odczyt kalendarza, redagowanie poczty, odczyt SMS-ów, zapytania o CPU/RAM, zapis pamięci, nauka aliasów
- **8 dostawców LLM**: interfejsy CLI Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 języków interfejsu**, ponad 50 ustawień regionalnych STT
- **Persony**: pliki Soul + Contract dla każdego języka, plus wyselekcjonowany zestaw z Nemotron-Personas-Korea firmy NVIDIA
- **Niestandardowe awatary** za pośrednictwem DiceBear (10 stylów), ImagePlayground (macOS 15.1+) lub własnego obrazu
- **Prywatność domyślnie**: nic nie opuszcza Twojego Maca poza (a) wybranym przez Ciebie dostawcą LLM oraz (b) zanonimizowaną diagnostyką, w której cały dowolny tekst jest zredukowany do wartości długości

---

## Zrzuty ekranu

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Karta rozmowy — główna" /></a><br/>
      <sub><b>Karta rozmowy</b> — awatar asystenta, opcjonalny podgląd kamery do śledzenia wzroku, nakładka poziomu mikrofonu i czat na żywo. Pomarańczowy znacznik „최근" pokazuje aktywny nastrój.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Karta rozmowy — rozmowa w toku" /></a><br/>
      <sub><b>Rozmowa na żywo</b> — markdown renderowany w dymkach, STT z automatyczną interpunkcją, plakietka „출발 알림" pojawia się, gdy umiejętność jest przygotowana.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Ustawienia — osobowość asystenta" /></a><br/>
      <sub><b>Ustawienia — Persona</b> — język interfejsu / STT, styl i płeć awatara, generowanie ImagePlayground oraz aktywny kontrakt <code>soul.md</code>, który kształtuje każdą odpowiedź.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnostyka — oś czasu" /></a><br/>
      <sub><b>Diagnostyka</b> — faza, yaw/pitch, wzrok, odczyty STT/twarzy/CPU oraz przewijana oś czasu każdej decyzji o zakończeniu wypowiedzi. Wyłącz oś czasu, aby zaoszczędzić kilka procent CPU.</sub>
    </td>
  </tr>
</table>

---

## Obsługiwane języki

TalkMode oddziela **język interfejsu** (język menu, przycisków i komunikatów o błędach) od **języka mowy** (język, w którym asystent transkrybuje i odpowiada). Można je ustawić niezależnie — czytaj interfejs po niemiecku, rozmawiaj z asystentem po koreańsku.

### Języki interfejsu (20)

Ustawiane w **Settings → 언어 → UI 언어**. Każdy język jest w pełni przetłumaczony — wszystkie menu, przyciski, ustawienia, opisy umiejętności i etykiety diagnostyczne.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Języki mowy / rozmowy

Wszystko, co obsługuje framework Speech Twojego Maca — zwykle **50-60 ustawień regionalnych** na macOS Sonoma+. Ustawiane w **Settings → 언어 → 음성 인식 언어**; lista wyboru pokazuje każde ustawienie regionalne zwrócone przez `SFSpeechRecognizer.supportedLocales()`, z czterema ustawieniami CJK + angielskim przypiętymi na górze.

Zawsze dostępne w standardowej instalacji macOS Sonoma+ (lista częściowa — Twój Mac może mieć ich więcej):

| Region | Ustawienia regionalne |
|---|---|
| **Azja Wschodnia** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Angielski** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Europa Zachodnia** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Europa Środkowa / Wschodnia** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Grecki / hebrajski** | Ελληνικά · עברית |
| **Bliski Wschód i Azja Południowa** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Azja Południowo-Wschodnia** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Inne** | Türkçe · Русский · Català · Қазақ |

> Dokładny zestaw zależy od wersji systemu operacyjnego oraz języków dyktowania pobranych w **System Settings → Keyboard → Dictation**. TalkMode odczytuje aktualną listę przy uruchomieniu — otwórz listę wyboru na swoim Macu, aby zobaczyć wiarygodny spis.

### Głosy TTS

*Wyjście* mowy korzysta z `AVSpeechSynthesizer` — tego samego silnika co macOS Siri / dyktowanie. Głosy pobiera się w **System Settings → Accessibility → Spoken Content → System Voice → Manage Voices**. Koreański: Yuna / Sora; angielski: Samantha / Alex / Daniel / Karen / Moira; japoński: Kyoko / O-Ren; chiński: Mei-Jia / Tian-Tian; itd. Głosy premium (Yuna Premium itp.) mają wyższą jakość, ale wymagają sieci dla pierwszego fragmentu.

---

> 🆕 **Latest features and install guide are in tym tłumaczeniu.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Instalacja

### Homebrew (zalecane)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Pobieranie bezpośrednie

[Latest release](https://talkmode.baryon.ai/download/TalkMode-0.4.29.zip) → rozpakuj → przeciągnij do `Applications` → przy pierwszym uruchomieniu macOS może powiedzieć „from unknown developer", kliknij prawym przyciskiem → Open jeden raz.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.29.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Automatyczne aktualizacje

Sparkle 2 jest wbudowany. Po zainstalowaniu (dowolnym sposobem) TalkMode sprawdza aktualizacje w tle — otwórz `TalkMode → Check for Updates…` lub `Settings → Update`, aby tym sterować.

### Wymagania

- macOS **Sonoma (14.0)** lub nowszy
- Apple silicon (M1 / M2 / M3 / M4)
- Dostawca LLM — przynajmniej Claude CLI, Codex CLI lub klucz OpenAI

---

## Uprawnienia

Uprawnienia są wymagane **tylko przy pierwszym użyciu danej funkcji**:

| Funkcja | Uprawnienie |
|---|---|
| Stałe nasłuchiwanie | Microphone, Speech Recognition |
| Śledzenie wzroku (opcjonalne) | Camera |
| Prawy Option do wyciszenia TTS | Input Monitoring |
| Umiejętności kalendarza | Calendars (Full Access) |
| Edytor wiadomości e-mail | Apple Events |
| Umiejętność `messages.list_recent` | Full Disk Access (ręcznie przyznawane w System Settings) |

Nic nie jest wysyłane — STT działa na urządzeniu (lub na serwerze STT firmy Apple, w zależności od ustawień regionalnych), awatary to lokalne pliki PNG, a dźwięk protokołu spotkania pozostaje w `~/.talk_mode_mac/recordings/`.

---

## Bezpieczeństwo i prywatność

To, co TalkMode przechowuje na Twoim Macu, co go opuszcza i dokąd trafia, co jest zapisywane na dysku oraz jak obsługiwane są klucze API i uprawnienia — wraz z przeglądem bezpieczeństwa na poziomie kodu i jego wynikami (brak luki możliwej do zdalnego wykorzystania; obecne ograniczenia ujawnione przejrzyście) — jest udokumentowane w **[SECURITY.md](../SECURITY.md)**.

---

## Zbudowane z

TalkMode to aplikacja macOS oparta na SwiftPM. Dwa pakiety Swift firm trzecich, reszta to frameworki Apple.

### Pakiety Swift

| Pakiet | Wersja | Co tu robi | Dlaczego |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Automatyczna aktualizacja w aplikacji przez podpisany appcast | Standard platformy Apple; używany przez 1Password, Tower, OBS. Aktualizacje podpisane EdDSA, pobieranie w tle, pozycja menu „Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Opcjonalna anonimowa diagnostyka (logi w stylu OpenTelemetry) | Pozwala zobaczyć, *które* przejścia faz utykają w praktyce, bez oglądania tekstu użytkownika — wszystkie pola dowolnego tekstu są redukowane do wartości długości przed wysłaniem. |

### Frameworki Apple

| Framework | Używany do |
|---|---|
| **AVFoundation** | Wejście single-tap `AVAudioEngine`, TTS `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), kamera `AVCaptureSession` |
| **Speech** | Strumieniowe STT `SpeechAnalyzer` (macOS 26) lub `SFSpeechRecognizer` z `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` dla pozycji głowy → szacowanie wzroku (ograniczone do ~10 fps) |
| **Accelerate (vDSP)** | 1024-punktowe FFT + okno Hanna + znormalizowane L2 osadzanie spektralne log-magnitude dla rozpoznawania mówców na urządzeniu |
| **EventKit** | Umiejętności odczytu / tworzenia / aktualizacji / usuwania kalendarza (zakres pełnego dostępu) |
| **ImagePlayground** | Generowanie awatarów na macOS 15.1+ (w przeciwnym razie powrót do PNG DiceBear przez URLSession) |
| **CoreImage / CoreVideo** | Konwersja klatek kamery dla wejścia Vision |
| **AppKit + SwiftUI** | Okno ustawień, układ wielokartowy, widok logów w aplikacji |
| **Combine** | Propagacja stanu `@Published` z `ConversationEngine` do całego interfejsu |
| **OSLog** | Diagnostyka unified log (`subsystem=app.talkmode`) |
| **SQLite3** | Lokalny magazyn aliasów + pamięć umiejętności |
| **UniformTypeIdentifiers** | Wybór pliku awatara |

### Zasoby firm trzecich (nie kod)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 wyselekcjonowane persony na tryb (이수민·정아람·박도윤·강예린). Użytkownicy mogą je nadpisać plikiem `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 stylów awatarów pobieranych jako PNG, buforowanych lokalnie.

---

## Tło techniczne

Kilka decyzji projektowych, które nie są oczywiste na zrzutach ekranu:

### Multimodalne wykrywanie zakończenia wypowiedzi — dlaczego Twoja tura kończy się szybko, ale nie za szybko

Standardowi asystenci głosowi CJK albo przerywają Ci przy pierwszym „음…", albo czekają 3 sekundy po tym, jak naprawdę skończysz. `AdaptiveTurnDetector` w TalkMode odczytuje cztery sygnały jednocześnie:

1. **Aktywność głosowa** (EnergyVAD na mikrofonie) — próbki ciszy gromadzą budżet
2. **Strumieniowa transkrypcja** (SpeechAnalyzer / SFSpeechRecognizer) — koreańskie 연결 어미 (`-고`, `-는데`) dodaje 1,2 s; 종결 어미 (`-습니다`, `-요`) odejmuje 400 ms; znaczniki wahania (`음…`, `어…`) dodają 1,5 s
3. **Tempo mowy** (znaki / sekundę) — szybko mówiący otrzymują mniejszy budżet pauzy
4. **Stan wzroku** (yaw / pitch głowy przez Vision) — patrzenie na ekran mnoży pauzę przez 0,3-0,65 (czekanie), odwrócenie wzroku po pełnym zdaniu mnoży przez 1,4 *oraz* uzbraja natychmiastowe szybkie wyzwolenie (skończyłeś)

Wszystkie cztery zasilają jedną funkcję `predictedSilenceMs()`, ograniczoną do dolnego progu zależnego od języka (CJK 900-7000 ms, angielski 300-3000 ms). Brak równoległych liczników, brak warunków wyścigu.

### Stale włączony dźwięk ma kluczowe znaczenie

`AudioInputStream` uruchamia `AVAudioEngine` **raz na sesję i nigdy go nie zatrzymuje** aż do końca sesji. Wcześniejszy kod zatrzymywał/restartował przy każdej granicy fazy; ten wzorzec gromadził błędy na macOS 26 (`couldn't get default input device, ID = 0`, przerwania `format.sampleRate == inputHWFormat.sampleRate`). Teraz jeden tap rozsyła bufory do N konsumentów (VAD, STT, detektor przerwania, rejestrator spotkań, miernik poziomu) przez `AsyncStream`.

### Rozpoznawanie mówców na urządzeniu

Tryb Protokołu Spotkania używa Apple Accelerate vDSP do obliczenia **24-wymiarowego znormalizowanego L2 osadzenia spektralnego log-magnitude** (FFT 1024, okno Hanna, hop 256) na wypowiedź. Podobieństwo cosinusowe > 0,82 = ten sam mówca co wcześniej, w przeciwnym razie przypisywane jest nowe ID. Brak pobierania modelu, brak wywołań API. Mówcy są zachowywani między spotkaniami — zmień etykietę „Speaker 1" → „지원" raz, a pozostanie.

### LLM to BYOK

`AssistantClient` to jeden protokół z ośmioma implementacjami. Dostawcy CLI (`CLIAssistantClient` dla `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) uruchamiają podproces w `~/.talk_mode_mac/work/` z izolowanym `currentDirectoryURL`, strumieniują stdout zdanie po zdaniu do `TTSQueue` i nigdy nie widzą klucza API od samego TalkMode. Przynosisz dowolną subskrypcję, za którą już płacisz.

### Diagnostyka z prywatnością jako domyślną

Opcjonalna telemetria PostHog przekazuje tylko **skategoryzowane zdarzenia**, a nie tekst bazowy:

- `turn / llm / tts / minutes / alias` → redukowane do `[category] len=N` przed wysłaniem
- `skill` → zachowuje `skill_id`, odrzuca `args`
- `fsm / endpointing / session / error / update` → tylko metadane, brak transkrypcji

Sprawdź w `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (widoczne w ciągach binarnych, jeśli mi nie ufasz).

### Markdown usuwany dla TTS, renderowany dla czatu

LLM-y uwielbiają `**bold**` i `### headings`. AVSpeechSynthesizer odczytuje je jako „gwiazdka gwiazdka bold gwiazdka gwiazdka". `MarkdownStripper.strip(_:)` czyści tekst tuż przed jego wejściem do `TTSQueue` (dymek czatu zachowuje oryginał przez `AttributedString(markdown:)`).

### Modularny podział SwiftPM

Obok głównej aplikacji istnieją dwa cele wielokrotnego użytku:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — czysto-Foundation funkcja `timeout(for:localeID:)` z 14 testami jednostkowymi. Mnożnik `sec/char × 4` dla każdego języka z dolnym progiem; nie może zostać po cichu zregresowany przez niepowiązany commit.
- **`Endpointing`** (`Sources/Endpointing/`) — posiada `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Brak zależności od AVFoundation / Vision. 7 testów jednostkowych obejmujących przekazanie przy odwróceniu wzroku, odrzucenie przy aktywnym mikrofonie i czyszczenie zatrzasku.

`swift test --filter EndpointingTests` i `swift test --filter SpeechWatchdogTests` — każdy działa na małym module, co umożliwia szybką iterację.

### Maszyna stanów

Każde przejście fazy (`idle → listening → thinking → speaking → listening …`) przechodzi przez jedną `PhaseStateMachine.transition(to:reason:)`. Nieprawidłowe przejścia są odrzucane z zalogowanym powodem. Widoczne na osi czasu karty Diagnostyka, więc gdy coś się zacina, możesz zobaczyć, *która* krawędź odmówiła zadziałania.

---

## Społeczność

- **Discussions** — pytania, pomysły, prośby o funkcje → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — zgłoszenia błędów → https://github.com/baryonlabs/talkmode-app/issues
- **E-mail** — support@baryon.ai

## Licencja

Skompilowana aplikacja jest darmowa do użytku osobistego i komercyjnego — pliki ZIP wydania zawierają jeden podpisany pakiet `.app`.

Kod źródłowy w tym repozytorium jest objęty licencją **GNU Affero General Public License v3.0** — zobacz [LICENSE](../LICENSE). Możesz go używać, badać, modyfikować i redystrybuować, ale każda zmodyfikowana wersja — w tym oferowana jako usługa sieciowa — musi pozostać otwarta na tej samej licencji AGPL-3.0. Prawa autorskie należą do Baryon Labs; jeśli potrzebujesz warunków poza AGPL-3.0 (np. licencji komercyjnej), zapytaj poprzez **Discussions**.

Stworzone w Seulu przez [Baryon Labs](https://baryon.ai).

<div align="center">

# TalkMode

**Ein Mac mini, der zum echten Assistenten wird — sofortige koreanische Sprache, auf dem Gerät, nach deinen Regeln.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | Deutsch | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Öffentliches Repository für TalkMode — Quellcode, **Releases**, **Issues** und **Discussions**.
> Siehe **[SECURITY.md](../SECURITY.md)** für genaue Angaben dazu, wie die App mit deinen Daten umgeht.

---

## Was ist TalkMode

TalkMode verwandelt einen Mac mini (oder jeden Apple-silicon-Mac) in einen **koreanischen Echtzeit-Sprachassistenten**, der sich wie ein Kollege verhält, nicht wie ein Chatbot.

- **Sprecherwechsel im Sub-Sekunden-Bereich** mit einem koreanisch abgestimmten adaptiven Endpunkterkenner (Blick + Stimme + Transkript)
- **Sprich, um zu unterbrechen, oder blick weg, um abzuschließen** — multimodale Signale, nicht nur Stille-Timer
- **4 Modi**: Gespräch · Besprechungsprotokoll · Brainstorming (auf Bestärkung ausgerichtet) · psychologische Begleitung (auf Zuhören ausgerichtet)
- **Sprecherdiarisierung auf dem Gerät** für Besprechungsprotokolle (Apple Accelerate vDSP)
- **Skills**: Kalender lesen, E-Mails entwerfen, SMS lesen, CPU/RAM abfragen, Erinnerungen speichern, Aliasse lernen
- **8 LLM-Anbieter**: Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLIs + OpenAI + Mock
- **20 UI-Sprachen**, über 50 STT-Gebietsschemata
- **Personas**: Soul- und Contract-Dateien, pro Sprache, plus ein kuratierter Satz aus NVIDIAs Nemotron-Personas-Korea
- **Eigene Avatare** über DiceBear (10 Stile), ImagePlayground (macOS 15.1+) oder dein eigenes Bild
- **Datenschutz standardmäßig**: Nichts verlässt deinen Mac außer (a) dem von dir gewählten LLM-Anbieter und (b) anonymisierte Diagnosedaten, bei denen jeglicher Freitext auf Längenwerte reduziert wird

---

## Screenshots

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Gesprächs-Tab — Hauptansicht" /></a><br/>
      <sub><b>Gesprächs-Tab</b> — Assistenten-Avatar, optionale Kameravorschau für den Blick, Mikrofonpegel-Overlay und Live-Chat. Der orangefarbene Chip „최근" zeigt die aktive Stimmung an.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Gesprächs-Tab — laufendes Gespräch" /></a><br/>
      <sub><b>Live-Gespräch</b> — Markdown in Sprechblasen gerendert, STT mit automatischer Zeichensetzung, das Abzeichen „출발 알림" erscheint, wenn eine Skill bereitgestellt ist.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Einstellungen — Assistenten-Persönlichkeit" /></a><br/>
      <sub><b>Einstellungen — Persona</b> — UI-/STT-Sprache, Avatar-Stil und Geschlecht, ImagePlayground-Generierung und der lebendige <code>soul.md</code>-Vertrag, der jede Antwort einrahmt.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnose — Zeitleiste" /></a><br/>
      <sub><b>Diagnose</b> — Phase, Yaw/Pitch, Blick, STT-/Gesichts-/CPU-Anzeigen und eine fortlaufende Zeitleiste jeder Endpunkterkennungs-Entscheidung. Schalte die Zeitleiste aus, um ein paar Prozent CPU zu sparen.</sub>
    </td>
  </tr>
</table>

---

## Unterstützte Sprachen

TalkMode trennt die **UI-Sprache** (in der Menüs, Schaltflächen und Fehlermeldungen vorliegen) von der **Sprechsprache** (in der der Assistent transkribiert und antwortet). Sie lassen sich unabhängig einstellen — lies die Oberfläche auf Deutsch und sprich mit dem Assistenten auf Koreanisch.

### UI-Sprachen (20)

Einzustellen unter **Einstellungen → 언어 → UI-Sprache**. Jede Sprache ist vollständig übersetzt — alle Menüs, Schaltflächen, Einstellungen, Skill-Beschreibungen und Diagnose-Bezeichnungen.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Sprech- / Gesprächssprachen

Was auch immer das Speech-Framework deines Macs unterstützt — typischerweise **50-60 Gebietsschemata** unter macOS Sonoma+. Einzustellen unter **Einstellungen → 언어 → Spracherkennungssprache**; die Auswahl listet jedes von `SFSpeechRecognizer.supportedLocales()` zurückgegebene Gebietsschema auf, wobei die vier CJK- + Englisch-Gebietsschemata oben angeheftet sind.

Auf einer Standardinstallation von macOS Sonoma+ immer verfügbar (eine unvollständige Liste — dein Mac kann mehr haben):

| Region | Gebietsschemata |
|---|---|
| **Ostasien** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Englisch** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Westeuropa** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Mittel- / Osteuropa** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Griechisch / Hebräisch** | Ελληνικά · עברית |
| **Naher Osten & Südasien** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Südostasien** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Sonstige** | Türkçe · Русский · Català · Қазақ |

> Der genaue Satz hängt von der Betriebssystemversion und den Diktatsprachen ab, die du unter **Systemeinstellungen → Tastatur → Diktat** heruntergeladen hast. TalkMode liest die Live-Liste beim Start — öffne die Auswahl auf deinem Mac für die maßgebliche Übersicht.

### TTS-Stimmen

Die Sprach*ausgabe* verwendet `AVSpeechSynthesizer` — dieselbe Engine wie Siri / Diktat von macOS. Stimmen werden unter **Systemeinstellungen → Bedienungshilfen → Gesprochene Inhalte → Systemstimme → Stimmen verwalten** heruntergeladen. Koreanisch: Yuna / Sora; Englisch: Samantha / Alex / Daniel / Karen / Moira; Japanisch: Kyoko / O-Ren; Chinesisch: Mei-Jia / Tian-Tian; usw. Premium-Stimmen (Yuna Premium usw.) sind höherwertig, benötigen aber für das erste Segment eine Netzwerkverbindung.

---

> 🆕 **Latest features and install guide are in dieser Übersetzung.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Installation

### Homebrew (empfohlen)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Direkter Download

[Neueste Version](https://talkmode.baryon.ai/download/TalkMode-0.4.34.zip) → entpacken → in `Applications` ziehen → beim ersten Start sagt macOS möglicherweise „von einem nicht identifizierten Entwickler", Rechtsklick → einmal Öffnen.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.34.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Automatische Aktualisierung

Sparkle 2 ist integriert. Nach der Installation (auf beide Arten) sucht TalkMode im Hintergrund nach Updates — öffne `TalkMode → Check for Updates…` oder `Settings → Update`, um es zu steuern.

### Voraussetzungen

- macOS **Sonoma (14.0)** oder neuer
- Apple silicon (M1 / M2 / M3 / M4)
- Ein LLM-Anbieter — mindestens das Claude CLI, das Codex CLI oder ein OpenAI-Schlüssel

---

## Berechtigungen

Berechtigungen werden **nur beim ersten Verwenden der Funktion** abgefragt:

| Funktion | Berechtigung |
|---|---|
| Dauerhaftes Zuhören | Mikrofon, Spracherkennung |
| Blickverfolgung (optional) | Kamera |
| Rechte Wahltaste zum Stummschalten der TTS | Eingabeüberwachung |
| Kalender-Skills | Kalender (Vollzugriff) |
| E-Mail-Verfasser | Apple Events |
| Skill `messages.list_recent` | Vollständiger Festplattenzugriff (manuell in den Systemeinstellungen gewähren) |

Es wird nichts hochgeladen — STT läuft auf dem Gerät (oder je nach Gebietsschema auf Apples STT-Server), Avatare sind lokale PNGs, und das Audio der Besprechungsprotokolle verbleibt in `~/.talk_mode_mac/recordings/`.

---

## Sicherheit & Datenschutz

Was TalkMode auf deinem Mac behält, was es verlässt und wohin, was auf der Festplatte gespeichert wird und wie API-Schlüssel und Berechtigungen gehandhabt werden — zusammen mit einer Sicherheitsüberprüfung auf Code-Ebene und deren Ergebnissen (keine aus der Ferne ausnutzbare Schwachstelle; aktuelle Einschränkungen werden transparent offengelegt) — ist in **[SECURITY.md](../SECURITY.md)** dokumentiert.

---

## Erstellt mit

TalkMode ist eine SwiftPM-basierte macOS-App. Zwei Swift-Pakete von Drittanbietern, der Rest sind Apple-Frameworks.

### Swift-Pakete

| Paket | Version | Was es hier tut | Warum |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | In-App-Auto-Update über einen signierten Appcast | Standard auf Apple-Plattformen; genutzt von 1Password, Tower, OBS. EdDSA-signierte Updates, Hintergrund-Download, Menüpunkt „Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Opt-in anonyme Diagnose (Logs im OpenTelemetry-Stil) | Lässt uns sehen, *welche* Phasenübergänge im Feld hängen bleiben, ohne je Nutzertext zu sehen — alle Freitextfelder werden vor dem Senden auf Längenwerte reduziert. |

### Apple-Frameworks

| Framework | Verwendet für |
|---|---|
| **AVFoundation** | Single-Tap-Eingabe mit `AVAudioEngine`, TTS mit `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), Kamera mit `AVCaptureSession` |
| **Speech** | Streaming-STT mit `SpeechAnalyzer` (macOS 26) oder `SFSpeechRecognizer` mit `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` für die Kopfhaltung → Blickschätzung (gedrosselt auf ~10 fps) |
| **Accelerate (vDSP)** | 1024-Punkt-FFT + Hann-Fenster + L2-normalisiertes Log-Magnitude-Spektral-Embedding für die Sprecherdiarisierung auf dem Gerät |
| **EventKit** | Skills zum Lesen / Erstellen / Aktualisieren / Löschen von Kalendern (Vollzugriffs-Bereich) |
| **ImagePlayground** | Avatar-Generierung unter macOS 15.1+ (greift sonst auf DiceBear-PNG via URLSession zurück) |
| **CoreImage / CoreVideo** | Kamerabild-Konvertierung für die Vision-Eingabe |
| **AppKit + SwiftUI** | Einstellungsfenster, mehrteiliges Tab-Layout, In-App-Log-Ansicht |
| **Combine** | `@Published`-Zustandsverbreitung von `ConversationEngine` an die gesamte UI |
| **OSLog** | Unified-Log-Diagnose (`subsystem=app.talkmode`) |
| **SQLite3** | Lokaler Alias-Speicher + Skill-Speicher |
| **UniformTypeIdentifiers** | Avatar-Dateiauswahl |

### Drittanbieter-Assets (kein Code)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 kuratierte Personas pro Modus (이수민·정아람·박도윤·강예린). Nutzer können sie mit `nemotron-extras.json` überschreiben.
- **[DiceBear](https://www.dicebear.com)** — 10 Avatar-Stile, als PNG abgerufen und lokal zwischengespeichert.

---

## Technischer Hintergrund

Einige Designentscheidungen, die aus den Screenshots nicht offensichtlich sind:

### Multimodale Endpunkterkennung — warum dein Redebeitrag schnell, aber nicht zu schnell endet

Standard-CJK-Sprachassistenten unterbrechen dich entweder beim ersten „음…" oder warten 3 Sekunden, nachdem du tatsächlich fertig bist. Der `AdaptiveTurnDetector` von TalkMode liest vier Signale gleichzeitig:

1. **Sprachaktivität** (EnergyVAD am Mikrofon) — Stille-Stichproben sammeln ein Budget an
2. **Streaming-Transkript** (SpeechAnalyzer / SFSpeechRecognizer) — koreanische Verbindungsendungen 연결 어미 (`-고`, `-는데`) addieren 1,2 s; Schlussendungen 종결 어미 (`-습니다`, `-요`) ziehen 400 ms ab; Zögermarker (`음…`, `어…`) addieren 1,5 s
3. **Sprechtempo** (Zeichen / Sekunde) — schnell Sprechende erhalten ein kleineres Pausenbudget
4. **Blickzustand** (Kopf-Yaw / -Pitch via Vision) — auf den Bildschirm zu schauen multipliziert die Pause mit 0,3-0,65 (wartend), nach einem vollständigen Satz wegzuschauen multipliziert sie mit 1,4 *und* aktiviert einen sofortigen Schnellauslöser (du bist fertig)

Alle vier speisen eine einzige `predictedSilenceMs()`-Funktion, begrenzt auf den sprachspezifischen Mindestwert (CJK 900-7000 ms, Englisch 300-3000 ms). Keine parallelen Timer, keine Race Conditions.

### Dauerhaft aktives Audio ist tragend

`AudioInputStream` startet `AVAudioEngine` **einmal pro Sitzung und stoppt es nie**, bis die Sitzung endet. Frührer Code stoppte/startete an jeder Phasengrenze neu; dieses Muster häufte unter macOS 26 Bugs an (`couldn't get default input device, ID = 0`, Abbrüche durch `format.sampleRate == inputHWFormat.sampleRate`). Jetzt verteilt ein einziger Tap die Puffer über `AsyncStream` an N Verbraucher (VAD, STT, Barge-in-Detektor, Besprechungsrekorder, Pegelanzeige).

### Sprecherdiarisierung auf dem Gerät

Der Modus für Besprechungsprotokolle verwendet Apple Accelerate vDSP, um pro Äußerung ein **24-dimensionales L2-normalisiertes Log-Magnitude-Spektral-Embedding** (FFT 1024, Hann-Fenster, Hop 256) zu berechnen. Kosinus-Ähnlichkeit > 0,82 = derselbe Sprecher wie zuvor, andernfalls wird eine neue ID vergeben. Kein Modell-Download, kein API-Aufruf. Sprecher bleiben über Besprechungen hinweg erhalten — benenne „Sprecher 1" → „지원" einmal um, und es bleibt bestehen.

### Das LLM ist BYOK

`AssistantClient` ist ein Protokoll mit acht Implementierungen. Die CLI-Anbieter (`CLIAssistantClient` für `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) starten einen Unterprozess in `~/.talk_mode_mac/work/` mit einem isolierten `currentDirectoryURL`, streamen stdout satzweise in die `TTSQueue` und sehen niemals einen API-Schlüssel von TalkMode selbst. Du bringst das Abonnement mit, für das du ohnehin schon zahlst.

### Diagnose mit Datenschutz standardmäßig

Die Opt-in-Telemetrie von PostHog leitet nur **kategorisierte Ereignisse** weiter, nicht den zugrunde liegenden Text:

- `turn / llm / tts / minutes / alias` → vor dem Senden auf `[category] len=N` reduziert
- `skill` → behält `skill_id`, verwirft `args`
- `fsm / endpointing / session / error / update` → nur Metadaten, kein Transkript

Überprüfe es in `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (in den Strings der Binärdatei sichtbar, falls du mir nicht vertraust).

### Markdown für TTS entfernt, für den Chat gerendert

LLMs lieben `**bold**` und `### headings`. AVSpeechSynthesizer liest sie als „Sternchen Sternchen fett Sternchen Sternchen". `MarkdownStripper.strip(_:)` säubert den Text genau bevor er in die `TTSQueue` gelangt (die Chat-Sprechblase behält das Original über `AttributedString(markdown:)`).

### Modulare SwiftPM-Aufteilung

Zwei wiederverwendbare Targets liegen neben der Haupt-App:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — reine Foundation-Funktion `timeout(for:localeID:)` mit 14 Unit-Tests. Sprachspezifischer `sec/char × 4`-Multiplikator mit einem Mindestwert; kann durch einen unzusammenhängenden Commit nicht stillschweigend verschlechtert werden.
- **`Endpointing`** (`Sources/Endpointing/`) — beheimatet `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Keine Abhängigkeit von AVFoundation / Vision. 7 Unit-Tests, die die Übergabe beim Wegschauen, die Ablehnung bei aktivem Mikrofon und das Löschen von Latches abdecken.

`swift test --filter EndpointingTests` und `swift test --filter SpeechWatchdogTests` laufen jeweils gegen ein winziges Modul — schnelle Iteration.

### Zustandsmaschine

Jeder Phasenübergang (`idle → listening → thinking → speaking → listening …`) läuft über ein einziges `PhaseStateMachine.transition(to:reason:)`. Unzulässige Übergänge werden mit einem protokollierten Grund abgelehnt. Das erscheint in der Zeitleiste des Diagnose-Tabs, sodass du bei einer Blockade sehen kannst, *welche* Kante sich weigerte zu feuern.

---

## Community

- **Discussions** — Fragen, Ideen, Funktionswünsche → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — Fehlerberichte → https://github.com/baryonlabs/talkmode-app/issues
- **E-Mail** — support@baryon.ai

## Lizenz

Die kompilierte App ist kostenlos nutzbar, privat oder kommerziell — die Release-ZIPs enthalten ein einzelnes signiertes `.app`-Bundle.

Der Quellcode in diesem Repository ist unter der **GNU Affero General Public License v3.0** lizenziert — siehe [LICENSE](../LICENSE). Du darfst ihn nutzen, studieren, ändern und weiterverbreiten, aber jede geänderte Version — auch eine, die als Netzwerkdienst angeboten wird — muss unter derselben AGPL-3.0-Lizenz offen bleiben. Baryon Labs hält das Urheberrecht; falls du Bedingungen außerhalb der AGPL-3.0 benötigst (z. B. eine kommerzielle Lizenz), frage über **Discussions** an.

Erstellt in Seoul von [Baryon Labs](https://baryon.ai).

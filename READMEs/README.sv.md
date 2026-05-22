<div align="center">

# TalkMode

**En Mac mini förvandlad till en riktig assistent — direkt koreansk röst, på enheten, på dina villkor.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | Svenska
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Offentligt arkiv för TalkMode — källkod, **Releases**, **Issues** och **Discussions**.
> Se **[SECURITY.md](../SECURITY.md)** för exakt hur appen hanterar dina data.

---

## Vad är TalkMode

TalkMode förvandlar en Mac mini (eller vilken Mac med Apple silicon som helst) till en **koreansk röstassistent i realtid** som beter sig som en kollega, inte en chatbot.

- **Turtagning på under en sekund** med en koreansk-anpassad adaptiv slutpunktsdetektor (blick + röst + transkription)
- **Prata för att avbryta, eller titta bort för att avsluta** — multimodala ledtrådar, inte bara tystnadstimers
- **4 lägen**: samtal · mötesprotokoll · brainstorming (fokus på instämmande) · psykologisk rådgivning (fokus på lyssnande)
- **Talaridentifiering på enheten** för mötesprotokoll (Apple Accelerate vDSP)
- **Färdigheter**: läsa kalender, skriva utkast till e-post, läsa SMS, fråga om CPU/RAM, spara minne, lära sig alias
- **8 LLM-leverantörer**: CLI:er för Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 gränssnittsspråk**, 50+ STT-språkinställningar
- **Personas**: Soul- + Contract-filer, per språk, plus en kurerad uppsättning från NVIDIA:s Nemotron-Personas-Korea
- **Anpassade avatarer** via DiceBear (10 stilar), ImagePlayground (macOS 15.1+) eller din egen bild
- **Integritet som standard**: inget lämnar din Mac förutom (a) den LLM-leverantör du valt och (b) anonymiserad diagnostik där all fritext har reducerats till längdvärden

---

## Skärmbilder

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Samtalsflik — huvudvy" /></a><br/>
      <sub><b>Samtalsflik</b> — assistentens avatar, valfri kameraförhandsvisning för blickspårning, mikrofonnivåöverlägg och livechatt. Den orange chippen "최근" visar det aktiva humöret.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Samtalsflik — samtal pågår" /></a><br/>
      <sub><b>Livesamtal</b> — markdown renderad i bubblor, STT automatiskt skiljeteckensatt, märket "출발 알림" visas när en färdighet är förberedd.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Inställningar — assistentpersonlighet" /></a><br/>
      <sub><b>Inställningar — Persona</b> — gränssnitts-/STT-språk, avatarstil och kön, ImagePlayground-generering och det aktiva <code>soul.md</code>-kontraktet som ramar in varje svar.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnostik — tidslinje" /></a><br/>
      <sub><b>Diagnostik</b> — fas, yaw/pitch, blick, STT-/ansikts-/CPU-avläsningar och en rullande tidslinje över varje slutpunktsbeslut. Stäng av tidslinjen för att spara några procent CPU.</sub>
    </td>
  </tr>
</table>

---

## Språk som stöds

TalkMode skiljer **gränssnittsspråket** (vilket språk menyer, knappar och felmeddelanden är på) från **talspråket** (vilket språk assistenten transkriberar och svarar på). De kan ställas in oberoende av varandra — läs gränssnittet på tyska, prata med assistenten på koreanska.

### Gränssnittsspråk (20)

Ställs in i **Settings → 언어 → UI 언어**. Varje språk är fullständigt översatt — alla menyer, knappar, inställningar, färdighetsbeskrivningar och diagnostiketiketter.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Tal-/samtalsspråk

Allt som din Macs Speech-ramverk stöder — vanligtvis **50-60 språkinställningar** på macOS Sonoma+. Ställs in i **Settings → 언어 → 음성 인식 언어**; väljaren listar varje språkinställning som `SFSpeechRecognizer.supportedLocales()` returnerar, med de fyra CJK- + engelska språkinställningarna fästa överst.

Alltid tillgängliga i en standardinstallation av macOS Sonoma+ (en delvis lista — din Mac kan ha fler):

| Region | Språkinställningar |
|---|---|
| **Östasien** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Engelska** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Västeuropa** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Central-/Östeuropa** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Grekiska / hebreiska** | Ελληνικά · עברית |
| **Mellanöstern och Sydasien** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Sydostasien** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Övrigt** | Türkçe · Русский · Català · Қазақ |

> Den exakta uppsättningen beror på OS-versionen och de dikteringsspråk du har laddat ner under **System Settings → Keyboard → Dictation**. TalkMode läser den aktuella listan vid start — öppna väljaren på din Mac för den definitiva förteckningen.

### TTS-röster

Tal*utmatning* använder `AVSpeechSynthesizer` — samma motor som macOS Siri / diktering. Röster laddas ner under **System Settings → Accessibility → Spoken Content → System Voice → Manage Voices**. Koreanska: Yuna / Sora; engelska: Samantha / Alex / Daniel / Karen / Moira; japanska: Kyoko / O-Ren; kinesiska: Mei-Jia / Tian-Tian; osv. Premiumröster (Yuna Premium osv.) har högre kvalitet men kräver nätverk för det första segmentet.

---

## Installation

### Homebrew (rekommenderas)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Direkt nedladdning

[Latest release](https://talkmode.baryon.ai/download/TalkMode-0.4.15.zip) → packa upp → dra till `Applications` → vid första öppningen kan macOS säga "from unknown developer", högerklicka → Open en gång.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.15.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Automatisk uppdatering

Sparkle 2 är inbyggt. När det väl är installerat (på vilket sätt som helst) söker TalkMode efter uppdateringar i bakgrunden — öppna `TalkMode → Check for Updates…` eller `Settings → Update` för att styra det.

### Krav

- macOS **Sonoma (14.0)** eller senare
- Apple silicon (M1 / M2 / M3 / M4)
- En LLM-leverantör — minst Claude CLI, Codex CLI eller en OpenAI-nyckel

---

## Behörigheter

Behörigheter efterfrågas **endast första gången du använder funktionen**:

| Funktion | Behörighet |
|---|---|
| Ständigt påslagen lyssning | Microphone, Speech Recognition |
| Blickspårning (valfritt) | Camera |
| Höger Option för att tysta TTS | Input Monitoring |
| Kalenderfärdigheter | Calendars (Full Access) |
| E-postredigerare | Apple Events |
| Färdigheten `messages.list_recent` | Full Disk Access (beviljas manuellt i System Settings) |

Inget laddas upp — STT körs på enheten (eller på Apples STT-server beroende på din språkinställning), avatarer är lokala PNG-filer och ljudet från mötesprotokoll stannar i `~/.talk_mode_mac/recordings/`.

---

## Säkerhet och integritet

Vad TalkMode behåller på din Mac, vad som lämnar den och vart, vad som lagras på disken och hur API-nycklar och behörigheter hanteras — tillsammans med en säkerhetsgranskning på kodnivå och dess resultat (ingen fjärrutnyttjbar sårbarhet; nuvarande begränsningar transparent redovisade) — finns dokumenterat i **[SECURITY.md](../SECURITY.md)**.

---

## Byggd med

TalkMode är en SwiftPM-baserad macOS-app. Två Swift-paket från tredje part, resten är Apple-ramverk.

### Swift-paket

| Paket | Version | Vad det gör här | Varför |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Automatisk uppdatering i appen via signerad appcast | Standard på Apple-plattformen; används av 1Password, Tower, OBS. EdDSA-signerade uppdateringar, nedladdning i bakgrunden, menyalternativet "Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Frivillig anonym diagnostik (loggar i OpenTelemetry-stil) | Låter oss se *vilka* fasövergångar som hakar upp sig i verkligheten utan att någonsin se användartext — alla fritextfält reduceras till längdvärden före sändning. |

### Apple-ramverk

| Ramverk | Används för |
|---|---|
| **AVFoundation** | `AVAudioEngine` single-tap-ingång, `AVSpeechSynthesizer` TTS (Yuna / Premium / Personal Voice), `AVCaptureSession`-kamera |
| **Speech** | `SpeechAnalyzer` (macOS 26) eller `SFSpeechRecognizer` strömmande STT med `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` för huvudställning → blickuppskattning (begränsad till ~10 fps) |
| **Accelerate (vDSP)** | 1024-punkts FFT + Hann-fönster + L2-normaliserad log-magnitude spektral inbäddning för talaridentifiering på enheten |
| **EventKit** | Färdigheter för att läsa / skapa / uppdatera / radera kalender (omfattning för full åtkomst) |
| **ImagePlayground** | Avatargenerering på macOS 15.1+ (faller annars tillbaka på DiceBear-PNG via URLSession) |
| **CoreImage / CoreVideo** | Konvertering av kamerabildrutor för Vision-ingång |
| **AppKit + SwiftUI** | Inställningsfönster, layout med flera flikar, loggvy i appen |
| **Combine** | Spridning av `@Published`-tillstånd från `ConversationEngine` till hela gränssnittet |
| **OSLog** | Diagnostik via unified log (`subsystem=app.talkmode`) |
| **SQLite3** | Lokalt aliaslager + färdighetsminne |
| **UniformTypeIdentifiers** | Filväljare för avatarer |

### Tredjepartstillgångar (ej kod)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 kurerade personas per läge (이수민·정아람·박도윤·강예린). Användare kan åsidosätta dem med `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 avatarstilar hämtade som PNG, cachade lokalt.

---

## Teknisk bakgrund

Några designval som inte är uppenbara från skärmbilderna:

### Multimodal slutpunktsdetektering — varför din tur slutar snabbt men inte för snabbt

Vanliga CJK-röstassistenter avbryter dig antingen vid det första "음…" eller väntar 3 sekunder efter att du faktiskt är klar. TalkModes `AdaptiveTurnDetector` läser fyra signaler samtidigt:

1. **Röstaktivitet** (EnergyVAD på mikrofonen) — tystnadsprover bygger upp en budget
2. **Strömmande transkription** (SpeechAnalyzer / SFSpeechRecognizer) — koreanska 연결 어미 (`-고`, `-는데`) lägger till 1,2 s; 종결 어미 (`-습니다`, `-요`) drar av 400 ms; tvekansmarkörer (`음…`, `어…`) lägger till 1,5 s
3. **Talhastighet** (tecken / sekund) — snabbtalare får en mindre pausbudget
4. **Blicktillstånd** (huvudets yaw / pitch via Vision) — att titta på skärmen multiplicerar pausen med 0,3-0,65 (väntar), att titta bort efter en fullständig mening multiplicerar med 1,4 *och* aktiverar en omedelbar snabbutlösning (du är klar)

Alla fyra matar in i en enda `predictedSilenceMs()`-funktion, begränsad till det språkspecifika golvet (CJK 900-7000 ms, engelska 300-3000 ms). Inga parallella timers, inga kapplöpningstillstånd.

### Ständigt påslaget ljud är avgörande

`AudioInputStream` startar `AVAudioEngine` **en gång per session och stoppar den aldrig** förrän sessionen avslutas. Tidigare kod stoppade/startade om vid varje fasgräns; det mönstret samlade på sig buggar på macOS 26 (`couldn't get default input device, ID = 0`, `format.sampleRate == inputHWFormat.sampleRate`-avbrott). Nu sänder en enda tap ut buffertar till N konsumenter (VAD, STT, avbrottsdetektor, mötesinspelare, nivåmätare) via `AsyncStream`.

### Talaridentifiering på enheten

Läget Mötesprotokoll använder Apple Accelerate vDSP för att beräkna en **24-dimensionell L2-normaliserad log-magnitude spektral inbäddning** (FFT 1024, Hann-fönster, hop 256) per yttrande. Cosinuslikhet > 0,82 = samma talare som tidigare, annars tilldelas ett nytt ID. Ingen modellnedladdning, inget API-anrop. Talare bevaras mellan möten — märk om "Speaker 1" → "지원" en gång, och det består.

### LLM är BYOK

`AssistantClient` är ett enda protokoll med åtta implementeringar. CLI-leverantörerna (`CLIAssistantClient` för `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) startar en underprocess i `~/.talk_mode_mac/work/` med en sandlådad `currentDirectoryURL`, strömmar stdout mening för mening till `TTSQueue` och ser aldrig en API-nyckel från TalkMode självt. Du tar med vilken prenumeration du redan betalar för.

### Diagnostik med integritet som standard

Den frivilliga PostHog-telemetrin vidarebefordrar endast **kategoriserade händelser**, inte den underliggande texten:

- `turn / llm / tts / minutes / alias` → reduceras till `[category] len=N` före sändning
- `skill` → behåller `skill_id`, släpper `args`
- `fsm / endpointing / session / error / update` → endast metadata, ingen transkription

Verifiera i `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (synligt i binärens strängar om du inte litar på mig).

### Markdown borttaget för TTS, renderat för chatt

LLM:er älskar `**bold**` och `### headings`. AVSpeechSynthesizer läser dem som "asterisk asterisk bold asterisk asterisk". `MarkdownStripper.strip(_:)` rensar texten precis innan den går in i `TTSQueue` (chattbubblan behåller originalet via `AttributedString(markdown:)`).

### Modulär SwiftPM-uppdelning

Två återanvändbara mål finns vid sidan av huvudappen:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — ren Foundation-funktion `timeout(for:localeID:)` med 14 enhetstester. Multiplikator `sec/char × 4` per språk med ett golv; kan inte regresseras i tysthet av en orelaterad commit.
- **`Endpointing`** (`Sources/Endpointing/`) — äger `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Inget beroende av AVFoundation / Vision. 7 enhetstester som täcker överlämning vid bortvänd blick, avvisning vid aktiv mikrofon och rensning av spärr.

`swift test --filter EndpointingTests` och `swift test --filter SpeechWatchdogTests` körs var och en mot en liten modul — snabb iteration.

### Tillståndsmaskin

Varje fasövergång (`idle → listening → thinking → speaking → listening …`) går genom en enda `PhaseStateMachine.transition(to:reason:)`. Ogiltiga övergångar avvisas med en loggad orsak. Visas i tidslinjen på fliken Diagnostik, så när något fastnar kan du se *vilken* kant som vägrade att utlösas.

---

## Gemenskap

- **Discussions** — frågor, idéer, funktionsförslag → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — buggrapporter → https://github.com/baryonlabs/talkmode-app/issues
- **E-post** — support@baryon.ai

## Licens

Den kompilerade appen är gratis att använda, privat eller kommersiellt — release-ZIP-filerna innehåller ett enda signerat `.app`-paket.

Källkoden i detta arkiv är licensierad under **GNU Affero General Public License v3.0** — se [LICENSE](../LICENSE). Du får använda, studera, modifiera och vidaredistribuera den, men varje modifierad version — inklusive en som erbjuds som en nätverkstjänst — måste förbli öppen under samma AGPL-3.0-licens. Baryon Labs innehar upphovsrätten; om du behöver villkor utanför AGPL-3.0 (t.ex. en kommersiell licens), fråga via **Discussions**.

Skapad i Seoul av [Baryon Labs](https://baryon.ai).

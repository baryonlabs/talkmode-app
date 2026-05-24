<div align="center">

# TalkMode

**Een Mac mini omgetoverd tot een echte assistent — directe Koreaanse stem, on-device, op jouw voorwaarden.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | Nederlands | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Openbare repository voor TalkMode — broncode, **Releases**, **Issues** en **Discussions**.
> Zie **[SECURITY.md](../SECURITY.md)** voor precies hoe de app met je gegevens omgaat.

---

## Wat is TalkMode

TalkMode verandert een Mac mini (of elke Apple-silicon Mac) in een **realtime Koreaanse spraakassistent** die zich gedraagt als een collega, niet als een chatbot.

- **Beurtwisseling binnen een seconde** met een op het Koreaans afgestemde adaptieve eindpuntdetector (blik + stem + transcript)
- **Praat om te onderbreken, of kijk weg om af te ronden** — multimodale signalen, niet alleen stiltetimers
- **4 modi**: gesprek · vergadernotulen · brainstorm (gericht op bijval) · psychologische begeleiding (gericht op luisteren)
- **On-device sprekerherkenning** voor vergadernotulen (Apple Accelerate vDSP)
- **Vaardigheden**: agenda lezen, e-mail opstellen, sms lezen, CPU/RAM opvragen, geheugen opslaan, aliassen leren
- **8 LLM-aanbieders**: CLI's van Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 interfacetalen**, 50+ STT-locales
- **Persona's**: Soul- + Contract-bestanden, per taal, plus een geselecteerde set uit NVIDIA's Nemotron-Personas-Korea
- **Aangepaste avatars** via DiceBear (10 stijlen), ImagePlayground (macOS 15.1+) of je eigen afbeelding
- **Privacy als standaard**: niets verlaat je Mac behalve (a) de LLM-aanbieder die je hebt gekozen en (b) geanonimiseerde diagnostiek waarbij alle vrije tekst is teruggebracht tot lengtewaarden

---

## Schermafbeeldingen

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Gesprekstabblad — hoofdscherm" /></a><br/>
      <sub><b>Gesprekstabblad</b> — assistent-avatar, optionele camerapreview voor blikdetectie, microfoonniveau-overlay en live chat. De oranje chip "최근" toont de actieve stemming.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Gesprekstabblad — gesprek loopt" /></a><br/>
      <sub><b>Live gesprek</b> — markdown weergegeven in bubbels, STT automatisch van leestekens voorzien, de badge "출발 알림" verschijnt wanneer een vaardigheid klaarstaat.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Instellingen — assistent-persoonlijkheid" /></a><br/>
      <sub><b>Instellingen — Persona</b> — interface-/STT-taal, avatarstijl en geslacht, ImagePlayground-generatie en het live <code>soul.md</code>-contract dat elk antwoord kadert.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnostiek — tijdlijn" /></a><br/>
      <sub><b>Diagnostiek</b> — fase, yaw/pitch, blik, STT-/gezichts-/CPU-metingen en een doorlopende tijdlijn van elke eindpuntbeslissing. Schakel de tijdlijn uit om een paar procent CPU te besparen.</sub>
    </td>
  </tr>
</table>

---

## Ondersteunde talen

TalkMode scheidt de **interfacetaal** (waarin de menu's, knoppen en foutmeldingen zijn) van de **spraaktaal** (waarin de assistent transcribeert en antwoordt). Ze kunnen onafhankelijk worden ingesteld — lees de interface in het Duits, praat met de assistent in het Koreaans.

### Interfacetalen (20)

Instelbaar via **Settings → 언어 → UI 언어**. Elke taal is volledig vertaald — alle menu's, knoppen, instellingen, vaardigheidsbeschrijvingen en diagnoselabels.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Spraak-/gesprekstalen

Wat het Speech-framework van je Mac ook ondersteunt — doorgaans **50-60 locales** op macOS Sonoma+. Instelbaar via **Settings → 언어 → 음성 인식 언어**; de keuzelijst toont elke locale die `SFSpeechRecognizer.supportedLocales()` retourneert, met de vier CJK- + Engelse locales bovenaan vastgezet.

Altijd beschikbaar op een standaard macOS Sonoma+-installatie (een gedeeltelijke lijst — je Mac heeft er mogelijk meer):

| Regio | Locales |
|---|---|
| **Oost-Azië** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Engels** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **West-Europa** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Centraal-/Oost-Europa** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Grieks / Hebreeuws** | Ελληνικά · עברית |
| **Midden-Oosten en Zuid-Azië** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Zuidoost-Azië** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Overig** | Türkçe · Русский · Català · Қазақ |

> De exacte set hangt af van de OS-versie en de dicteertalen die je hebt gedownload onder **System Settings → Keyboard → Dictation**. TalkMode leest bij het opstarten de live lijst — open de keuzelijst op je Mac voor de definitieve inventaris.

### TTS-stemmen

Spraak*uitvoer* gebruikt `AVSpeechSynthesizer` — dezelfde engine als macOS Siri / dictee. Stemmen worden gedownload via **System Settings → Accessibility → Spoken Content → System Voice → Manage Voices**. Koreaans: Yuna / Sora; Engels: Samantha / Alex / Daniel / Karen / Moira; Japans: Kyoko / O-Ren; Chinees: Mei-Jia / Tian-Tian; enz. Premiumstemmen (Yuna Premium, enz.) zijn van hogere kwaliteit maar vereisen netwerk voor het eerste fragment.

---

> 🆕 **Latest features and install guide are in deze vertaling.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Installatie

### Homebrew (aanbevolen)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Directe download

[Latest release](https://talkmode.baryon.ai/download/TalkMode-0.4.22.zip) → uitpakken → naar `Applications` slepen → bij de eerste keer openen kan macOS "from unknown developer" zeggen, klik eenmaal met de rechtermuisknop → Open.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.22.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Automatische updates

Sparkle 2 is ingebouwd. Eenmaal geïnstalleerd (op welke manier dan ook) controleert TalkMode op de achtergrond op updates — open `TalkMode → Check for Updates…` of `Settings → Update` om dit te beheren.

### Vereisten

- macOS **Sonoma (14.0)** of later
- Apple silicon (M1 / M2 / M3 / M4)
- Een LLM-aanbieder — minimaal de Claude CLI, Codex CLI of een OpenAI-sleutel

---

## Machtigingen

Machtigingen worden **alleen de eerste keer dat je de functie gebruikt** gevraagd:

| Functie | Machtiging |
|---|---|
| Altijd-aan luisteren | Microphone, Speech Recognition |
| Blikdetectie (optioneel) | Camera |
| Right-Option om TTS te dempen | Input Monitoring |
| Agendavaardigheden | Calendars (Full Access) |
| E-mailopsteller | Apple Events |
| Vaardigheid `messages.list_recent` | Full Disk Access (handmatig toekennen in System Settings) |

Er wordt niets geüpload — STT draait on-device (of op de STT-server van Apple, afhankelijk van je locale), avatars zijn lokale PNG's en de audio van vergadernotulen blijft in `~/.talk_mode_mac/recordings/`.

---

## Beveiliging en privacy

Wat TalkMode op je Mac bewaart, wat je Mac verlaat en waarheen, wat op schijf wordt opgeslagen en hoe API-sleutels en machtigingen worden afgehandeld — samen met een beveiligingsbeoordeling op codeniveau en de bevindingen ervan (geen op afstand uitbuitbare kwetsbaarheid; huidige beperkingen transparant bekendgemaakt) — is gedocumenteerd in **[SECURITY.md](../SECURITY.md)**.

---

## Gebouwd met

TalkMode is een op SwiftPM gebaseerde macOS-app. Twee Swift-pakketten van derden, de rest zijn Apple-frameworks.

### Swift-pakketten

| Pakket | Versie | Wat het hier doet | Waarom |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Automatische update in de app via ondertekende appcast | Standaard op het Apple-platform; gebruikt door 1Password, Tower, OBS. EdDSA-ondertekende updates, download op de achtergrond, menu-item "Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Opt-in anonieme diagnostiek (OpenTelemetry-achtige logs) | Hiermee kunnen we zien *welke* faseovergangen in de praktijk vastlopen zonder ooit gebruikerstekst te zien — alle vrije tekstvelden worden vóór verzending teruggebracht tot lengtewaarden. |

### Apple-frameworks

| Framework | Gebruikt voor |
|---|---|
| **AVFoundation** | `AVAudioEngine` single-tap-invoer, `AVSpeechSynthesizer` TTS (Yuna / Premium / Personal Voice), `AVCaptureSession` camera |
| **Speech** | `SpeechAnalyzer` (macOS 26) of `SFSpeechRecognizer` streaming-STT met `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` voor hoofdhouding → blikschatting (beperkt tot ~10 fps) |
| **Accelerate (vDSP)** | 1024-punts FFT + Hann-venster + L2-genormaliseerde log-magnitude spectrale embedding voor on-device sprekerherkenning |
| **EventKit** | Vaardigheden voor agenda lezen / aanmaken / bijwerken / verwijderen (full-access-bereik) |
| **ImagePlayground** | Avatargeneratie op macOS 15.1+ (valt anders terug op DiceBear-PNG via URLSession) |
| **CoreImage / CoreVideo** | Conversie van cameraframes voor Vision-invoer |
| **AppKit + SwiftUI** | Instellingenvenster, indeling met meerdere tabbladen, logweergave in de app |
| **Combine** | Propagatie van `@Published`-status van `ConversationEngine` naar alle UI |
| **OSLog** | Unified-log-diagnostiek (`subsystem=app.talkmode`) |
| **SQLite3** | Lokale aliasopslag + vaardigheidsgeheugen |
| **UniformTypeIdentifiers** | Bestandskiezer voor avatars |

### Assets van derden (geen code)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 geselecteerde persona's per modus (이수민·정아람·박도윤·강예린). Gebruikers kunnen deze overschrijven met `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 avatarstijlen opgehaald als PNG, lokaal in cache opgeslagen.

---

## Technische achtergrond

Een paar ontwerpkeuzes die niet duidelijk zijn op de schermafbeeldingen:

### Multimodale eindpuntdetectie — waarom je beurt snel maar niet té snel eindigt

Standaard CJK-spraakassistenten onderbreken je ofwel bij de eerste "음…" of wachten 3 seconden nadat je daadwerkelijk klaar bent. TalkMode's `AdaptiveTurnDetector` leest vier signalen tegelijk:

1. **Spraakactiviteit** (EnergyVAD op de microfoon) — stiltemonsters bouwen een budget op
2. **Streaming transcript** (SpeechAnalyzer / SFSpeechRecognizer) — Koreaanse 연결 어미 (`-고`, `-는데`) voegt 1,2 s toe; 종결 어미 (`-습니다`, `-요`) trekt 400 ms af; aarzelingsmarkeringen (`음…`, `어…`) voegen 1,5 s toe
3. **Spreeksnelheid** (tekens / seconde) — snelle sprekers krijgen een kleiner pauzebudget
4. **Blikstatus** (hoofd-yaw / -pitch via Vision) — naar het scherm kijken vermenigvuldigt de pauze met 0,3-0,65 (wachtend), wegkijken na een volledige zin vermenigvuldigt met 1,4 *en* activeert een directe snelle trigger (je bent klaar)

Alle vier voeden één `predictedSilenceMs()`-functie, begrensd tot de taalspecifieke ondergrens (CJK 900-7000 ms, Engels 300-3000 ms). Geen parallelle timers, geen race conditions.

### Altijd-aan audio is van cruciaal belang

`AudioInputStream` start `AVAudioEngine` **eenmaal per sessie en stopt deze nooit** tot de sessie eindigt. Eerdere code stopte/herstartte bij elke fasegrens; dat patroon stapelde bugs op in macOS 26 (`couldn't get default input device, ID = 0`, `format.sampleRate == inputHWFormat.sampleRate`-aborts). Nu zendt één tap buffers uit naar N consumenten (VAD, STT, onderbrekingsdetector, vergaderopnemer, niveaumeter) via `AsyncStream`.

### On-device sprekerherkenning

De modus Vergadernotulen gebruikt Apple Accelerate vDSP om per uiting een **24-dimensionale L2-genormaliseerde log-magnitude spectrale embedding** te berekenen (FFT 1024, Hann-venster, hop 256). Cosinusgelijkenis > 0,82 = dezelfde spreker als eerder, anders wordt een nieuwe ID toegewezen. Geen modeldownload, geen API-aanroep. Sprekers blijven behouden tussen vergaderingen — herbenoem "Speaker 1" → "지원" één keer en het blijft hangen.

### LLM is BYOK

`AssistantClient` is één protocol met acht implementaties. De CLI-aanbieders (`CLIAssistantClient` voor `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) starten een subproces in `~/.talk_mode_mac/work/` met een sandboxed `currentDirectoryURL`, streamen stdout zin voor zin naar `TTSQueue` en zien nooit een API-sleutel van TalkMode zelf. Je brengt het abonnement mee waar je toch al voor betaalt.

### Privacy-by-default diagnostiek

De opt-in PostHog-telemetrie stuurt alleen **gecategoriseerde gebeurtenissen** door, niet de onderliggende tekst:

- `turn / llm / tts / minutes / alias` → vóór verzending teruggebracht tot `[category] len=N`
- `skill` → behoudt `skill_id`, laat `args` weg
- `fsm / endpointing / session / error / update` → alleen metadata, geen transcript

Controleer in `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (zichtbaar in de strings van de binary als je me niet vertrouwt).

### Markdown gestript voor TTS, weergegeven voor chat

LLM's zijn dol op `**bold**` en `### headings`. AVSpeechSynthesizer leest die voor als "asterisk asterisk bold asterisk asterisk". `MarkdownStripper.strip(_:)` schoont de tekst op vlak voordat deze in `TTSQueue` terechtkomt (de chatbubbel behoudt het origineel via `AttributedString(markdown:)`).

### Modulaire SwiftPM-opsplitsing

Twee herbruikbare targets staan naast de hoofd-app:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — pure-Foundation `timeout(for:localeID:)`-functie met 14 unittests. Per-taal `sec/char × 4`-vermenigvuldiger met een ondergrens; kan niet stilletjes worden teruggedraaid door een niet-gerelateerde commit.
- **`Endpointing`** (`Sources/Endpointing/`) — bezit `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Geen AVFoundation-/Vision-afhankelijkheid. 7 unittests die de overdracht bij wegkijken, microfoon-actief-afwijzing en latch-wissing dekken.

`swift test --filter EndpointingTests` en `swift test --filter SpeechWatchdogTests` draaien elk tegen een klein module — snelle iteratie.

### Toestandsmachine

Elke faseovergang (`idle → listening → thinking → speaking → listening …`) gaat via één `PhaseStateMachine.transition(to:reason:)`. Ongeldige overgangen worden afgewezen met een gelogde reden. Verschijnt in de tijdlijn van het tabblad Diagnostiek, zodat je bij vastlopen kunt zien *welke* rand weigerde te activeren.

---

## Community

- **Discussions** — vragen, ideeën, functieverzoeken → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — bugrapporten → https://github.com/baryonlabs/talkmode-app/issues
- **E-mail** — support@baryon.ai

## Licentie

De gecompileerde app is gratis te gebruiken, persoonlijk of commercieel — de release-ZIP's bevatten één enkele ondertekende `.app`-bundel.

De broncode in deze repository valt onder de **GNU Affero General Public License v3.0** — zie [LICENSE](../LICENSE). Je mag deze gebruiken, bestuderen, wijzigen en herdistribueren, maar elke gewijzigde versie — inclusief een versie die als netwerkdienst wordt aangeboden — moet open blijven onder dezelfde AGPL-3.0-licentie. Baryon Labs houdt het auteursrecht; heb je voorwaarden buiten AGPL-3.0 nodig (bijv. een commerciële licentie), vraag dit dan via **Discussions**.

Gemaakt in Seoul door [Baryon Labs](https://baryon.ai).

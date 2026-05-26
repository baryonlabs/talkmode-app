<div align="center">

# TalkMode

**Un Mac mini trasformato in un vero assistente — voce coreana istantanea, sul dispositivo, alle tue condizioni.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | Italiano | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Repository pubblico di TalkMode — codice sorgente, **Releases**, **Issues** e **Discussions**.
> Consulta **[SECURITY.md](../SECURITY.md)** per sapere esattamente come l'app gestisce i tuoi dati.

---

## Che cos'è TalkMode

TalkMode trasforma un Mac mini (o qualsiasi Mac con Apple silicon) in un **assistente vocale coreano in tempo reale** che si comporta come un collega, non come un chatbot.

- **Alternanza di turno in meno di un secondo** con un rilevatore di fine discorso adattivo calibrato sul coreano (sguardo + voce + trascrizione)
- **Parla per interrompere, o distogli lo sguardo per concludere** — segnali multimodali, non solo timer di silenzio
- **4 modalità**: conversazione · verbale di riunione · brainstorming (incentrata sul sostegno) · sostegno psicologico (incentrata sull'ascolto)
- **Diarizzazione dei parlanti sul dispositivo** per i verbali di riunione (Apple Accelerate vDSP)
- **Skill**: leggere il calendario, redigere e-mail, leggere gli SMS, interrogare CPU/RAM, salvare ricordi, imparare alias
- **8 provider di LLM**: CLI di Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 lingue dell'interfaccia**, oltre 50 impostazioni locali per lo STT
- **Persone**: file Anima + Contratto, per lingua, più un insieme curato tratto da Nemotron-Personas-Korea di NVIDIA
- **Avatar personalizzati** tramite DiceBear (10 stili), ImagePlayground (macOS 15.1+) o una tua immagine
- **Privacy per impostazione predefinita**: nulla lascia il tuo Mac tranne (a) il provider di LLM che hai scelto e (b) diagnostica anonimizzata con tutto il testo libero ridotto a valori di lunghezza

---

## Schermate

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Scheda conversazione — principale" /></a><br/>
      <sub><b>Scheda conversazione</b> — avatar dell'assistente, anteprima opzionale della fotocamera per lo sguardo, sovrapposizione del livello del microfono e chat dal vivo. Il chip arancione "최근" mostra l'umore attivo.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Scheda conversazione — conversazione in corso" /></a><br/>
      <sub><b>Conversazione dal vivo</b> — markdown reso nelle bolle, STT con punteggiatura automatica, il badge "출발 알림" compare quando una skill è preparata.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Impostazioni — personalità dell'assistente" /></a><br/>
      <sub><b>Impostazioni — Persona</b> — lingua dell'interfaccia / STT, stile e genere dell'avatar, generazione con ImagePlayground e il contratto vivo <code>soul.md</code> che inquadra ogni risposta.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnostica — cronologia" /></a><br/>
      <sub><b>Diagnostica</b> — fase, yaw/pitch, sguardo, letture di STT/volto/CPU e una cronologia scorrevole di ogni decisione di fine discorso. Disattiva la cronologia per risparmiare qualche punto percentuale di CPU.</sub>
    </td>
  </tr>
</table>

---

## Lingue supportate

TalkMode separa la **lingua dell'interfaccia** (quella in cui sono menu, pulsanti e messaggi di errore) dalla **lingua del parlato** (quella in cui l'assistente trascrive e risponde). Si impostano in modo indipendente — leggi l'interfaccia in tedesco e parla con l'assistente in coreano.

### Lingue dell'interfaccia (20)

Si impostano in **Impostazioni → 언어 → Lingua dell'interfaccia**. Ogni lingua è completamente tradotta — tutti i menu, i pulsanti, le impostazioni, le descrizioni delle skill e le etichette diagnostiche.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Lingue del parlato / della conversazione

Tutto ciò che supporta il framework Speech del tuo Mac — in genere **50-60 impostazioni locali** su macOS Sonoma+. Si imposta in **Impostazioni → 언어 → Lingua di riconoscimento vocale**; il selettore elenca ogni impostazione locale restituita da `SFSpeechRecognizer.supportedLocales()` con le quattro impostazioni CJK + inglese fissate in cima.

Sempre disponibili in un'installazione standard di macOS Sonoma+ (elenco parziale — il tuo Mac potrebbe averne di più):

| Regione | Impostazioni locali |
|---|---|
| **Asia orientale** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Inglese** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Europa occidentale** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Europa centrale / orientale** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Greco / Ebraico** | Ελληνικά · עברית |
| **Medio Oriente e Asia meridionale** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Sud-est asiatico** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Altre** | Türkçe · Русский · Català · Қазақ |

> L'insieme esatto dipende dalla versione del sistema operativo e dalle lingue di dettatura che hai scaricato in **Impostazioni di Sistema → Tastiera → Dettatura**. TalkMode legge l'elenco dal vivo all'avvio — apri il selettore sul tuo Mac per l'inventario definitivo.

### Voci TTS

L'*output* vocale usa `AVSpeechSynthesizer` — lo stesso motore di Siri / dettatura di macOS. Le voci si scaricano in **Impostazioni di Sistema → Accessibilità → Contenuto pronunciato → Voce di sistema → Gestisci voci**. Coreano: Yuna / Sora; inglese: Samantha / Alex / Daniel / Karen / Moira; giapponese: Kyoko / O-Ren; cinese: Mei-Jia / Tian-Tian; ecc. Le voci premium (Yuna Premium, ecc.) sono di qualità superiore ma richiedono la rete per il primo segmento.

---

> 🆕 **Latest features and install guide are in questa traduzione.** This translation covers the core docs; the visual install walkthrough, free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Installazione

### Homebrew (consigliato)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Download diretto

[Ultima versione](https://talkmode.baryon.ai/download/TalkMode-0.4.25.zip) → estrai → trascina in `Applications` → al primo avvio macOS potrebbe dire "da uno sviluppatore non identificato", fai clic destro → Apri una volta.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.25.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Aggiornamento automatico

Sparkle 2 è integrato. Una volta installato (in entrambi i modi), TalkMode controlla gli aggiornamenti in background — apri `TalkMode → Check for Updates…` o `Settings → Update` per controllarlo.

### Requisiti

- macOS **Sonoma (14.0)** o successivo
- Apple silicon (M1 / M2 / M3 / M4)
- Un provider di LLM — come minimo la CLI di Claude, la CLI di Codex o una chiave OpenAI

---

## Autorizzazioni

Le autorizzazioni vengono richieste **solo la prima volta che usi la funzione**:

| Funzione | Autorizzazione |
|---|---|
| Ascolto sempre attivo | Microfono, Riconoscimento vocale |
| Tracciamento dello sguardo (opzionale) | Fotocamera |
| Tasto Opzione destro per silenziare il TTS | Monitoraggio input |
| Skill del calendario | Calendari (Accesso completo) |
| Compositore di e-mail | Apple Events |
| Skill `messages.list_recent` | Accesso completo al disco (concedilo manualmente nelle Impostazioni di Sistema) |

Nulla viene caricato — lo STT viene eseguito sul dispositivo (o sul server STT di Apple a seconda dell'impostazione locale), gli avatar sono PNG locali e l'audio dei verbali di riunione rimane in `~/.talk_mode_mac/recordings/`.

---

## Sicurezza e privacy

Cosa TalkMode conserva sul tuo Mac, cosa ne esce e verso dove, cosa viene memorizzato su disco e come vengono gestite le chiavi API e le autorizzazioni — insieme a una revisione di sicurezza a livello di codice e ai suoi risultati (nessuna vulnerabilità sfruttabile da remoto; limitazioni attuali divulgate in modo trasparente) — è documentato in **[SECURITY.md](../SECURITY.md)**.

---

## Realizzato con

TalkMode è un'app macOS basata su SwiftPM. Due pacchetti Swift di terze parti, il resto sono framework Apple.

### Pacchetti Swift

| Pacchetto | Versione | Cosa fa qui | Perché |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Aggiornamento automatico in-app tramite un appcast firmato | Standard della piattaforma Apple; usato da 1Password, Tower, OBS. Aggiornamenti firmati EdDSA, download in background, voce di menu "Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Diagnostica anonima opzionale (log in stile OpenTelemetry) | Ci consente di vedere *quali* transizioni di fase si bloccano sul campo senza mai vedere il testo dell'utente — tutti i campi a testo libero vengono ridotti a valori di lunghezza prima dell'invio. |

### Framework Apple

| Framework | Usato per |
|---|---|
| **AVFoundation** | Input a tap singolo con `AVAudioEngine`, TTS con `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), fotocamera con `AVCaptureSession` |
| **Speech** | STT in streaming con `SpeechAnalyzer` (macOS 26) o `SFSpeechRecognizer` con `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` per la posa della testa → stima dello sguardo (limitato a ~10 fps) |
| **Accelerate (vDSP)** | FFT a 1024 punti + finestra di Hann + embedding spettrale log-magnitude normalizzato L2 per la diarizzazione dei parlanti sul dispositivo |
| **EventKit** | Skill di lettura / creazione / aggiornamento / eliminazione del calendario (ambito ad accesso completo) |
| **ImagePlayground** | Generazione di avatar su macOS 15.1+ (altrimenti ripiega su un PNG DiceBear tramite URLSession) |
| **CoreImage / CoreVideo** | Conversione dei fotogrammi della fotocamera per l'input di Vision |
| **AppKit + SwiftUI** | Finestra delle impostazioni, layout a più schede, vista del log in-app |
| **Combine** | Propagazione dello stato tramite `@Published` da `ConversationEngine` a tutta l'interfaccia |
| **OSLog** | Diagnostica del log unificato (`subsystem=app.talkmode`) |
| **SQLite3** | Archivio di alias locale + memoria delle skill |
| **UniformTypeIdentifiers** | Selettore di file per l'avatar |

### Risorse di terze parti (non codice)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 persone curate per modalità (이수민·정아람·박도윤·강예린). Gli utenti possono sovrascriverle con `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 stili di avatar recuperati come PNG, memorizzati nella cache localmente.

---

## Contesto tecnico

Alcune scelte progettuali che non risultano evidenti dalle schermate:

### Rilevamento di fine discorso multimodale — perché il tuo turno finisce in fretta ma non troppo

Gli assistenti vocali CJK standard o ti interrompono al primo "음…" o aspettano 3 secondi dopo che hai davvero finito. Il `AdaptiveTurnDetector` di TalkMode legge quattro segnali contemporaneamente:

1. **Attività vocale** (EnergyVAD sul microfono) — i campioni di silenzio accumulano un budget
2. **Trascrizione in streaming** (SpeechAnalyzer / SFSpeechRecognizer) — le desinenze di collegamento coreane 연결 어미 (`-고`, `-는데`) aggiungono 1,2 s; le desinenze conclusive 종결 어미 (`-습니다`, `-요`) tolgono 400 ms; i marcatori di esitazione (`음…`, `어…`) aggiungono 1,5 s
3. **Velocità del parlato** (caratteri / secondo) — chi parla velocemente ottiene un budget di pausa più ridotto
4. **Stato dello sguardo** (yaw / pitch della testa tramite Vision) — guardare lo schermo moltiplica la pausa per 0,3-0,65 (in attesa), distogliere lo sguardo dopo una frase completa la moltiplica per 1,4 *e* arma un attivatore rapido immediato (hai finito)

Tutti e quattro alimentano un'unica funzione `predictedSilenceMs()`, vincolata al minimo per lingua (CJK 900-7000 ms, inglese 300-3000 ms). Nessun timer parallelo, nessuna race condition.

### L'audio sempre attivo è portante

`AudioInputStream` avvia `AVAudioEngine` **una volta per sessione e non lo ferma mai** finché la sessione non termina. Il codice precedente lo fermava/riavviava a ogni confine di fase; quel modello accumulava bug su macOS 26 (`couldn't get default input device, ID = 0`, interruzioni dovute a `format.sampleRate == inputHWFormat.sampleRate`). Ora un solo tap trasmette i buffer a N consumatori (VAD, STT, rilevatore di interruzione, registratore di riunioni, indicatore di livello) tramite `AsyncStream`.

### Diarizzazione dei parlanti sul dispositivo

La modalità Verbale di riunione usa Apple Accelerate vDSP per calcolare un **embedding spettrale log-magnitude a 24 dimensioni normalizzato L2** (FFT 1024, finestra di Hann, hop 256) per ogni enunciato. Similarità del coseno > 0,82 = stesso parlante di prima, altrimenti viene assegnato un nuovo ID. Nessun download di modelli, nessuna chiamata API. I parlanti persistono tra le riunioni — rietichetta "Parlante 1" → "지원" una volta e resta così.

### Il LLM è BYOK

`AssistantClient` è un unico protocollo con otto implementazioni. I provider CLI (`CLIAssistantClient` per `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) avviano un sottoprocesso in `~/.talk_mode_mac/work/` con un `currentDirectoryURL` isolato, trasmettono stdout frase per frase nella `TTSQueue` e non vedono mai una chiave API da TalkMode stesso. Porti l'abbonamento che già paghi.

### Diagnostica con privacy per impostazione predefinita

La telemetria opzionale di PostHog inoltra solo **eventi categorizzati**, non il testo sottostante:

- `turn / llm / tts / minutes / alias` → ridotti a `[category] len=N` prima dell'invio
- `skill` → mantiene `skill_id`, scarta `args`
- `fsm / endpointing / session / error / update` → solo metadati, nessuna trascrizione

Verificalo in `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (visibile nelle stringhe del binario se non ti fidi di me).

### Markdown rimosso per il TTS, reso per la chat

I LLM adorano `**bold**` e `### headings`. AVSpeechSynthesizer li legge come "asterisco asterisco grassetto asterisco asterisco". `MarkdownStripper.strip(_:)` ripulisce il testo appena prima che entri nella `TTSQueue` (la bolla della chat conserva l'originale tramite `AttributedString(markdown:)`).

### Suddivisione modulare di SwiftPM

Due target riutilizzabili convivono accanto all'app principale:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — funzione `timeout(for:localeID:)` in puro Foundation con 14 test unitari. Moltiplicatore `sec/char × 4` per lingua con un minimo; non può subire regressioni silenziose a causa di un commit non correlato.
- **`Endpointing`** (`Sources/Endpointing/`) — ospita `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Nessuna dipendenza da AVFoundation / Vision. 7 test unitari che coprono il passaggio di consegne quando si distoglie lo sguardo, il rifiuto con microfono attivo, l'azzeramento dei latch.

`swift test --filter EndpointingTests` e `swift test --filter SpeechWatchdogTests` vengono eseguiti ciascuno su un modulo minuscolo — iterazione rapida.

### Macchina a stati

Ogni transizione di fase (`idle → listening → thinking → speaking → listening …`) passa per un unico `PhaseStateMachine.transition(to:reason:)`. Le transizioni illegali vengono rifiutate con un motivo registrato. Compare nella cronologia della scheda Diagnostica, così quando qualcosa si blocca puoi vedere *quale* arco si è rifiutato di scattare.

---

## Comunità

- **Discussions** — domande, idee, richieste di funzionalità → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — segnalazioni di bug → https://github.com/baryonlabs/talkmode-app/issues
- **E-mail** — support@baryon.ai

## Licenza

L'app compilata è di libero utilizzo, personale o commerciale — gli ZIP delle versioni contengono un singolo bundle `.app` firmato.

Il codice sorgente in questo repository è concesso in licenza secondo la **GNU Affero General Public License v3.0** — vedi [LICENSE](../LICENSE). Puoi usarlo, studiarlo, modificarlo e ridistribuirlo, ma qualsiasi versione modificata — inclusa una offerta come servizio di rete — deve rimanere aperta sotto la stessa licenza AGPL-3.0. Baryon Labs detiene il copyright; se hai bisogno di condizioni al di fuori di AGPL-3.0 (ad esempio una licenza commerciale), chiedi tramite **Discussions**.

Realizzato a Seoul da [Baryon Labs](https://baryon.ai).

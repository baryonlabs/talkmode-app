<div align="center">

# TalkMode

**Un Mac mini transformé en véritable assistant — voix coréenne instantanée, sur l'appareil, selon vos règles.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | Français | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Dépôt public de TalkMode — code source, **Releases**, **Issues** et **Discussions**.
> Consultez **[SECURITY.md](../SECURITY.md)** pour savoir précisément comment l'application traite vos données.

---

## Qu'est-ce que TalkMode

TalkMode transforme un Mac mini (ou n'importe quel Mac Apple silicon) en un **assistant vocal coréen en temps réel** qui se comporte comme un collègue, pas comme un chatbot.

- **Prise de parole en moins d'une seconde** grâce à un détecteur de fin de parole adaptatif réglé pour le coréen (regard + voix + transcription)
- **Parlez pour interrompre, ou détournez le regard pour conclure** — des signaux multimodaux, pas seulement des minuteurs de silence
- **4 modes** : conversation · compte rendu de réunion · brainstorming (axé sur l'encouragement) · accompagnement psychologique (axé sur l'écoute)
- **Diarisation des locuteurs sur l'appareil** pour les comptes rendus de réunion (Apple Accelerate vDSP)
- **Skills** : lire le calendrier, rédiger des e-mails, lire les SMS, interroger le CPU/RAM, enregistrer des souvenirs, apprendre des alias
- **8 fournisseurs de LLM** : CLIs Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 langues d'interface**, plus de 50 paramètres régionaux de STT
- **Personas** : fichiers Âme + Contrat, par langue, ainsi qu'un ensemble sélectionné issu de Nemotron-Personas-Korea de NVIDIA
- **Avatars personnalisés** via DiceBear (10 styles), ImagePlayground (macOS 15.1+) ou votre propre image
- **Confidentialité par défaut** : rien ne quitte votre Mac, sauf (a) le fournisseur de LLM que vous avez choisi et (b) des diagnostics anonymisés dont tout le texte libre est réduit à des valeurs de longueur

---

## Captures d'écran

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Onglet conversation — principal" /></a><br/>
      <sub><b>Onglet conversation</b> — avatar de l'assistant, aperçu caméra optionnel pour le regard, superposition du niveau du micro et chat en direct. La pastille orange « 최근 » affiche l'humeur active.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Onglet conversation — conversation en cours" /></a><br/>
      <sub><b>Conversation en direct</b> — markdown rendu dans des bulles, STT avec ponctuation automatique, le badge « 출발 알림 » apparaît lorsqu'une skill est préparée.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Réglages — personnalité de l'assistant" /></a><br/>
      <sub><b>Réglages — Persona</b> — langue d'interface / STT, style et genre de l'avatar, génération ImagePlayground et le contrat vivant <code>soul.md</code> qui encadre chaque réponse.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnostics — chronologie" /></a><br/>
      <sub><b>Diagnostics</b> — phase, yaw/pitch, regard, relevés STT/visage/CPU et une chronologie défilante de chaque décision de fin de parole. Désactivez la chronologie pour économiser quelques % de CPU.</sub>
    </td>
  </tr>
</table>

---

## Langues prises en charge

TalkMode distingue la **langue de l'interface** (celle des menus, des boutons et des messages d'erreur) de la **langue de la parole** (celle dans laquelle l'assistant transcrit et répond). Elles se règlent indépendamment — lisez l'interface en allemand et parlez à l'assistant en coréen.

### Langues d'interface (20)

Se règle dans **Réglages → 언어 → Langue de l'interface**. Chaque langue est entièrement traduite — tous les menus, boutons, réglages, descriptions de skills et étiquettes de diagnostic.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Langues de parole / conversation

Tout ce que prend en charge le framework Speech de votre Mac — généralement **50 à 60 paramètres régionaux** sous macOS Sonoma+. Se règle dans **Réglages → 언어 → Langue de reconnaissance vocale** ; le sélecteur liste chaque paramètre régional renvoyé par `SFSpeechRecognizer.supportedLocales()` avec les quatre paramètres CJC + anglais épinglés en haut.

Toujours disponibles sur une installation standard de macOS Sonoma+ (liste partielle — votre Mac peut en avoir davantage) :

| Région | Paramètres régionaux |
|---|---|
| **Asie de l'Est** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Anglais** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Europe de l'Ouest** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Europe centrale / de l'Est** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Grec / Hébreu** | Ελληνικά · עברית |
| **Moyen-Orient et Asie du Sud** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Asie du Sud-Est** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Autres** | Türkçe · Русский · Català · Қазақ |

> L'ensemble exact dépend de la version du système d'exploitation et des langues de dictée que vous avez téléchargées sous **Réglages Système → Clavier → Dictée**. TalkMode lit la liste en direct au lancement — ouvrez le sélecteur sur votre Mac pour l'inventaire faisant foi.

### Voix de synthèse (TTS)

La *sortie* vocale utilise `AVSpeechSynthesizer` — le même moteur que Siri / la dictée de macOS. Les voix se téléchargent sous **Réglages Système → Accessibilité → Contenu énoncé → Voix du système → Gérer les voix**. Coréen : Yuna / Sora ; anglais : Samantha / Alex / Daniel / Karen / Moira ; japonais : Kyoko / O-Ren ; chinois : Mei-Jia / Tian-Tian ; etc. Les voix premium (Yuna Premium, etc.) sont de meilleure qualité mais nécessitent le réseau pour le premier fragment.

---

> 🆕 **Latest features and install guide are in cette traduction.** This translation covers the core docs; the visual install walkthrough, free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Installation

### Homebrew (recommandé)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Téléchargement direct

[Dernière version](https://talkmode.baryon.ai/download/TalkMode-0.4.37.zip) → décompresser → glisser dans `Applications` → au premier lancement, macOS peut indiquer « d'un développeur non identifié », faites un clic droit → Ouvrir une fois.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.37.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Mise à jour automatique

Sparkle 2 est intégré. Une fois installé (de l'une ou l'autre façon), TalkMode recherche les mises à jour en arrière-plan — ouvrez `TalkMode → Check for Updates…` ou `Settings → Update` pour le contrôler.

### Configuration requise

- macOS **Sonoma (14.0)** ou ultérieur
- Apple silicon (M1 / M2 / M3 / M4)
- Un fournisseur de LLM — au minimum le CLI Claude, le CLI Codex ou une clé OpenAI

---

## Autorisations

Les autorisations ne sont demandées **que la première fois que vous utilisez la fonction** :

| Fonction | Autorisation |
|---|---|
| Écoute toujours active | Microphone, Reconnaissance vocale |
| Suivi du regard (optionnel) | Caméra |
| Option droite pour couper le TTS | Surveillance des saisies |
| Skills de calendrier | Calendriers (Accès complet) |
| Rédacteur d'e-mails | Apple Events |
| Skill `messages.list_recent` | Accès complet au disque (à accorder manuellement dans les Réglages Système) |

Rien n'est téléversé — le STT s'exécute sur l'appareil (ou sur le serveur STT d'Apple selon votre paramètre régional), les avatars sont des PNG locaux et l'audio des comptes rendus de réunion reste dans `~/.talk_mode_mac/recordings/`.

---

## Sécurité et confidentialité

Ce que TalkMode conserve sur votre Mac, ce qui en sort et vers où, ce qui est stocké sur le disque, et la manière dont les clés d'API et les autorisations sont gérées — ainsi qu'une revue de sécurité au niveau du code et ses conclusions (aucune vulnérabilité exploitable à distance ; limites actuelles divulguées en toute transparence) — est documenté dans **[SECURITY.md](../SECURITY.md)**.

---

## Construit avec

TalkMode est une application macOS basée sur SwiftPM. Deux paquets Swift tiers, le reste étant des frameworks Apple.

### Paquets Swift

| Paquet | Version | Ce qu'il fait ici | Pourquoi |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Mise à jour automatique intégrée via un appcast signé | Standard de la plateforme Apple ; utilisé par 1Password, Tower, OBS. Mises à jour signées EdDSA, téléchargement en arrière-plan, élément de menu « Check for Updates… ». |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Diagnostics anonymes facultatifs (journaux de style OpenTelemetry) | Nous permet de voir *quelles* transitions de phase bloquent en conditions réelles sans jamais voir le texte de l'utilisateur — tous les champs en texte libre sont réduits à des valeurs de longueur avant l'envoi. |

### Frameworks Apple

| Framework | Utilisé pour |
|---|---|
| **AVFoundation** | Entrée à tap unique avec `AVAudioEngine`, TTS avec `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), caméra avec `AVCaptureSession` |
| **Speech** | STT en streaming avec `SpeechAnalyzer` (macOS 26) ou `SFSpeechRecognizer` avec `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` pour la pose de la tête → estimation du regard (limité à ~10 fps) |
| **Accelerate (vDSP)** | FFT 1024 points + fenêtre de Hann + embedding spectral log-magnitude normalisé L2 pour la diarisation des locuteurs sur l'appareil |
| **EventKit** | Skills de lecture / création / mise à jour / suppression de calendrier (portée d'accès complet) |
| **ImagePlayground** | Génération d'avatars sous macOS 15.1+ (repli sur un PNG DiceBear via URLSession sinon) |
| **CoreImage / CoreVideo** | Conversion des images de la caméra pour l'entrée Vision |
| **AppKit + SwiftUI** | Fenêtre de réglages, mise en page multi-onglets, vue de journal intégrée |
| **Combine** | Propagation de l'état via `@Published` de `ConversationEngine` vers toute l'interface |
| **OSLog** | Diagnostics du journal unifié (`subsystem=app.talkmode`) |
| **SQLite3** | Magasin d'alias local + mémoire des skills |
| **UniformTypeIdentifiers** | Sélecteur de fichiers d'avatar |

### Ressources tierces (hors code)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 personas sélectionnées par mode (이수민·정아람·박도윤·강예린). Les utilisateurs peuvent les remplacer avec `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 styles d'avatar récupérés en PNG, mis en cache localement.

---

## Contexte technique

Quelques choix de conception qui ne sautent pas aux yeux sur les captures d'écran :

### Détection multimodale de fin de parole — pourquoi votre tour se termine vite mais pas trop vite

Les assistants vocaux CJC standards vous coupent dès le premier « 음… » ou attendent 3 secondes après que vous ayez réellement terminé. Le `AdaptiveTurnDetector` de TalkMode lit quatre signaux à la fois :

1. **Activité vocale** (EnergyVAD sur le micro) — les échantillons de silence accumulent un budget
2. **Transcription en streaming** (SpeechAnalyzer / SFSpeechRecognizer) — les terminatives de liaison coréennes 연결 어미 (`-고`, `-는데`) ajoutent 1,2 s ; les terminatives finales 종결 어미 (`-습니다`, `-요`) retirent 400 ms ; les marqueurs d'hésitation (`음…`, `어…`) ajoutent 1,5 s
3. **Débit de parole** (caractères / seconde) — les personnes qui parlent vite obtiennent un budget de pause plus court
4. **État du regard** (yaw / pitch de la tête via Vision) — regarder l'écran multiplie la pause par 0,3-0,65 (en attente), détourner le regard après une phrase complète la multiplie par 1,4 *et* arme un déclenchement rapide immédiat (vous avez terminé)

Les quatre alimentent une seule fonction `predictedSilenceMs()`, bornée au plancher par langue (CJC 900-7000 ms, anglais 300-3000 ms). Aucun minuteur parallèle, aucune condition de concurrence.

### L'audio toujours actif est structurel

`AudioInputStream` démarre `AVAudioEngine` **une fois par session et ne l'arrête jamais** jusqu'à la fin de la session. L'ancien code arrêtait/redémarrait à chaque frontière de phase ; ce schéma accumulait des bugs sous macOS 26 (`couldn't get default input device, ID = 0`, abandons dus à `format.sampleRate == inputHWFormat.sampleRate`). Désormais, un seul tap diffuse les tampons vers N consommateurs (VAD, STT, détecteur d'interruption, enregistreur de réunion, indicateur de niveau) via `AsyncStream`.

### Diarisation des locuteurs sur l'appareil

Le mode compte rendu de réunion utilise Apple Accelerate vDSP pour calculer un **embedding spectral log-magnitude à 24 dimensions normalisé L2** (FFT 1024, fenêtre de Hann, pas 256) par énoncé. Similarité cosinus > 0,82 = même locuteur qu'avant, sinon un nouvel ID est attribué. Aucun téléchargement de modèle, aucun appel d'API. Les locuteurs persistent d'une réunion à l'autre — réétiquetez « Locuteur 1 » → « 지원 » une fois et cela tient.

### Le LLM est BYOK

`AssistantClient` est un unique protocole avec huit implémentations. Les fournisseurs CLI (`CLIAssistantClient` pour `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) lancent un sous-processus dans `~/.talk_mode_mac/work/` avec un `currentDirectoryURL` isolé, transmettent stdout phrase par phrase vers `TTSQueue` et ne voient jamais de clé d'API de TalkMode lui-même. Vous apportez l'abonnement que vous payez déjà.

### Diagnostics avec confidentialité par défaut

La télémétrie PostHog facultative ne transmet que des **événements catégorisés**, pas le texte sous-jacent :

- `turn / llm / tts / minutes / alias` → réduits à `[category] len=N` avant l'envoi
- `skill` → conserve `skill_id`, abandonne `args`
- `fsm / endpointing / session / error / update` → métadonnées uniquement, aucune transcription

Vérifiez dans `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (visible dans les strings du binaire si vous ne me croyez pas).

### Markdown supprimé pour le TTS, rendu pour le chat

Les LLM adorent `**bold**` et `### headings`. AVSpeechSynthesizer les lit comme « astérisque astérisque gras astérisque astérisque ». `MarkdownStripper.strip(_:)` nettoie le texte juste avant son entrée dans `TTSQueue` (la bulle de chat conserve l'original via `AttributedString(markdown:)`).

### Découpage modulaire SwiftPM

Deux targets réutilisables cohabitent avec l'application principale :

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — fonction `timeout(for:localeID:)` en Foundation pur avec 14 tests unitaires. Multiplicateur `sec/char × 4` par langue avec un plancher ; ne peut pas subir de régression silencieuse par un commit sans rapport.
- **`Endpointing`** (`Sources/Endpointing/`) — héberge `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Aucune dépendance à AVFoundation / Vision. 7 tests unitaires couvrant le passage de relais au détournement du regard, le rejet avec micro actif, l'effacement des verrous.

`swift test --filter EndpointingTests` et `swift test --filter SpeechWatchdogTests` s'exécutent chacun sur un module minuscule — itération rapide.

### Machine à états

Chaque transition de phase (`idle → listening → thinking → speaking → listening …`) passe par un unique `PhaseStateMachine.transition(to:reason:)`. Les transitions illégales sont rejetées avec un motif consigné. Cela apparaît dans la chronologie de l'onglet Diagnostics, donc lorsque quelque chose bloque, vous pouvez voir *quelle* arête a refusé de se déclencher.

---

## Communauté

- **Discussions** — questions, idées, demandes de fonctionnalités → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — rapports de bugs → https://github.com/baryonlabs/talkmode-app/issues
- **E-mail** — support@baryon.ai

## Licence

L'application compilée est libre d'utilisation, personnelle ou commerciale — les ZIP des versions contiennent un unique paquet `.app` signé.

Le code source de ce dépôt est sous licence **GNU Affero General Public License v3.0** — voir [LICENSE](../LICENSE). Vous pouvez l'utiliser, l'étudier, le modifier et le redistribuer, mais toute version modifiée — y compris une version proposée comme service réseau — doit rester ouverte sous la même licence AGPL-3.0. Baryon Labs détient les droits d'auteur ; si vous avez besoin de conditions hors AGPL-3.0 (par exemple une licence commerciale), demandez via **Discussions**.

Fait à Séoul par [Baryon Labs](https://baryon.ai).

<div align="center">

# TalkMode

**Un Mac mini convertido en un asistente de verdad — voz coreana instantánea, en el dispositivo, según tus reglas.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | Español | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Repositorio público de TalkMode — código fuente, **Releases**, **Issues** y **Discussions**.
> Consulta **[SECURITY.md](../SECURITY.md)** para saber exactamente cómo la app gestiona tus datos.

---

## Qué es TalkMode

TalkMode convierte un Mac mini (o cualquier Mac con Apple silicon) en un **asistente de voz coreano en tiempo real** que se comporta como un compañero de trabajo, no como un chatbot.

- **Cambio de turno por debajo del segundo** con un detector de fin de habla adaptativo ajustado al coreano (mirada + voz + transcripción)
- **Habla para interrumpir, o aparta la mirada para concluir** — señales multimodales, no solo temporizadores de silencio
- **4 modos**: conversación · acta de reunión · lluvia de ideas (centrada en el refuerzo) · acompañamiento psicológico (centrada en la escucha)
- **Diarización de hablantes en el dispositivo** para actas de reunión (Apple Accelerate vDSP)
- **Skills**: leer el calendario, redactar correos, leer SMS, consultar CPU/RAM, guardar recuerdos, aprender alias
- **8 proveedores de LLM**: CLIs de Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 idiomas de interfaz**, más de 50 configuraciones regionales de STT
- **Personas**: archivos de Alma + Contrato, por idioma, además de un conjunto curado a partir de Nemotron-Personas-Korea de NVIDIA
- **Avatares personalizados** mediante DiceBear (10 estilos), ImagePlayground (macOS 15.1+) o tu propia imagen
- **Privacidad por defecto**: nada sale de tu Mac salvo (a) el proveedor de LLM que elijas y (b) diagnósticos anonimizados con todo el texto libre reducido a valores de longitud

---

## Capturas de pantalla

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Pestaña de conversación — principal" /></a><br/>
      <sub><b>Pestaña de conversación</b> — avatar del asistente, vista previa opcional de la cámara para la mirada, superposición del nivel del micrófono y chat en vivo. El chip naranja "최근" muestra el estado de ánimo activo.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Pestaña de conversación — conversación en curso" /></a><br/>
      <sub><b>Conversación en vivo</b> — markdown renderizado en burbujas, STT con puntuación automática, la insignia "출발 알림" aparece cuando una skill está preparada.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Ajustes — persona del asistente" /></a><br/>
      <sub><b>Ajustes — Persona</b> — idioma de interfaz / STT, estilo y género del avatar, generación con ImagePlayground y el contrato vivo <code>soul.md</code> que enmarca cada respuesta.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnóstico — línea de tiempo" /></a><br/>
      <sub><b>Diagnóstico</b> — fase, yaw/pitch, mirada, lecturas de STT/rostro/CPU y una línea de tiempo continua de cada decisión de fin de habla. Desactiva la línea de tiempo para ahorrar unos puntos porcentuales de CPU.</sub>
    </td>
  </tr>
</table>

---

## Idiomas compatibles

TalkMode separa el **idioma de la interfaz** (en el que están los menús, botones y mensajes de error) del **idioma del habla** (en el que el asistente transcribe y responde). Se pueden configurar de forma independiente — lee la interfaz en alemán y habla con el asistente en coreano.

### Idiomas de interfaz (20)

Se configura en **Ajustes → 언어 → Idioma de interfaz**. Todos los idiomas están totalmente traducidos — todos los menús, botones, ajustes, descripciones de skills y etiquetas de diagnóstico.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Idiomas de habla / conversación

Lo que admita el framework Speech de tu Mac — normalmente **50-60 configuraciones regionales** en macOS Sonoma+. Se configura en **Ajustes → 언어 → Idioma de reconocimiento de voz**; el selector lista cada configuración regional devuelta por `SFSpeechRecognizer.supportedLocales()` con las cuatro configuraciones CJK + inglés fijadas arriba.

Siempre disponibles en una instalación estándar de macOS Sonoma+ (una lista parcial — tu Mac puede tener más):

| Región | Configuraciones regionales |
|---|---|
| **Asia Oriental** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Inglés** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Europa Occidental** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Europa Central / Oriental** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Griego / Hebreo** | Ελληνικά · עברית |
| **Oriente Medio y Sur de Asia** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Sudeste Asiático** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Otros** | Türkçe · Русский · Català · Қазақ |

> El conjunto exacto depende de la versión del sistema operativo y de los idiomas de dictado que hayas descargado en **Ajustes del Sistema → Teclado → Dictado**. TalkMode lee la lista en vivo al arrancar — abre el selector en tu Mac para ver el inventario definitivo.

### Voces de TTS

La *salida* de voz usa `AVSpeechSynthesizer` — el mismo motor que Siri / el dictado de macOS. Las voces se descargan en **Ajustes del Sistema → Accesibilidad → Contenido hablado → Voz del sistema → Gestionar voces**. Coreano: Yuna / Sora; inglés: Samantha / Alex / Daniel / Karen / Moira; japonés: Kyoko / O-Ren; chino: Mei-Jia / Tian-Tian; etc. Las voces premium (Yuna Premium, etc.) tienen mayor calidad pero requieren red para el fragmento inicial.

---

> 🆕 **Latest features and install guide are in esta traducción.** This translation covers the core docs; the visual install walkthrough, free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Instalación

### Homebrew (recomendado)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Descarga directa

[Última versión](https://talkmode.baryon.ai/download/TalkMode-0.4.26.zip) → descomprimir → arrastrar a `Applications` → en el primer lanzamiento macOS puede decir "de un desarrollador no identificado", haz clic derecho → Abrir una vez.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.26.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Actualización automática

Sparkle 2 está integrado. Una vez instalada (de cualquiera de las dos formas), TalkMode busca actualizaciones en segundo plano — abre `TalkMode → Check for Updates…` o `Settings → Update` para controlarlo.

### Requisitos

- macOS **Sonoma (14.0)** o posterior
- Apple silicon (M1 / M2 / M3 / M4)
- Un proveedor de LLM — como mínimo el CLI de Claude, el CLI de Codex o una clave de OpenAI

---

## Permisos

Los permisos se solicitan **solo la primera vez que usas la función**:

| Función | Permiso |
|---|---|
| Escucha siempre activa | Micrófono, Reconocimiento de voz |
| Seguimiento de la mirada (opcional) | Cámara |
| Option derecha para silenciar el TTS | Monitorización de entrada |
| Skills de calendario | Calendarios (Acceso total) |
| Redactor de correo | Apple Events |
| Skill `messages.list_recent` | Acceso completo al disco (concédelo manualmente en Ajustes del Sistema) |

No se sube nada — el STT se ejecuta en el dispositivo (o en el servidor STT de Apple según tu configuración regional), los avatares son PNG locales y el audio de las actas de reunión permanece en `~/.talk_mode_mac/recordings/`.

---

## Seguridad y privacidad

Qué guarda TalkMode en tu Mac, qué sale de él y hacia dónde, qué se almacena en disco y cómo se gestionan las claves de API y los permisos — junto con una revisión de seguridad a nivel de código y sus conclusiones (ninguna vulnerabilidad explotable de forma remota; limitaciones actuales divulgadas con transparencia) — está documentado en **[SECURITY.md](../SECURITY.md)**.

---

## Construido con

TalkMode es una app de macOS basada en SwiftPM. Dos paquetes Swift de terceros, el resto son frameworks de Apple.

### Paquetes Swift

| Paquete | Versión | Qué hace aquí | Por qué |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Actualización automática dentro de la app mediante un appcast firmado | Estándar de la plataforma Apple; usado por 1Password, Tower, OBS. Actualizaciones firmadas con EdDSA, descarga en segundo plano, elemento de menú "Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Diagnósticos anónimos opcionales (registros estilo OpenTelemetry) | Nos permite ver *qué* transiciones de fase se atascan en producción sin ver nunca el texto del usuario — todos los campos de formato libre se reducen a valores de longitud antes del envío. |

### Frameworks de Apple

| Framework | Usado para |
|---|---|
| **AVFoundation** | Entrada de un solo tap con `AVAudioEngine`, TTS con `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), cámara con `AVCaptureSession` |
| **Speech** | STT en streaming con `SpeechAnalyzer` (macOS 26) o `SFSpeechRecognizer` con `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` para la pose de la cabeza → estimación de la mirada (limitado a ~10 fps) |
| **Accelerate (vDSP)** | FFT de 1024 puntos + ventana de Hann + embedding espectral de log-magnitud normalizado L2 para la diarización de hablantes en el dispositivo |
| **EventKit** | Skills de lectura / creación / actualización / eliminación de calendario (ámbito de acceso total) |
| **ImagePlayground** | Generación de avatares en macOS 15.1+ (recurre a PNG de DiceBear vía URLSession en caso contrario) |
| **CoreImage / CoreVideo** | Conversión de fotogramas de cámara para la entrada de Vision |
| **AppKit + SwiftUI** | Ventana de ajustes, diseño multipestaña, vista de registro dentro de la app |
| **Combine** | Propagación de estado con `@Published` desde `ConversationEngine` a toda la interfaz |
| **OSLog** | Diagnósticos de registro unificado (`subsystem=app.talkmode`) |
| **SQLite3** | Almacén local de alias + memoria de skills |
| **UniformTypeIdentifiers** | Selector de archivos de avatar |

### Recursos de terceros (no código)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 personas curadas por modo (이수민·정아람·박도윤·강예린). Los usuarios pueden sobrescribirlas con `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 estilos de avatar obtenidos como PNG, almacenados en caché localmente.

---

## Trasfondo técnico

Algunas decisiones de diseño que no son evidentes en las capturas de pantalla:

### Detección de fin de habla multimodal — por qué tu turno termina rápido pero no demasiado rápido

Los asistentes de voz CJK estándar o te cortan en el primer "음…" o esperan 3 segundos después de que realmente terminas. El `AdaptiveTurnDetector` de TalkMode lee cuatro señales a la vez:

1. **Actividad de voz** (EnergyVAD en el micrófono) — las muestras de silencio acumulan un presupuesto
2. **Transcripción en streaming** (SpeechAnalyzer / SFSpeechRecognizer) — las terminaciones conectivas coreanas 연결 어미 (`-고`, `-는데`) suman 1,2 s; las terminaciones finales 종결 어미 (`-습니다`, `-요`) restan 400 ms; los marcadores de duda (`음…`, `어…`) suman 1,5 s
3. **Velocidad de habla** (caracteres / segundo) — quienes hablan rápido obtienen un presupuesto de pausa menor
4. **Estado de la mirada** (yaw / pitch de la cabeza vía Vision) — mirar la pantalla multiplica la pausa por 0,3-0,65 (esperando), apartar la mirada tras una frase completa la multiplica por 1,4 *y además* prepara un disparo rápido inmediato (has terminado)

Las cuatro alimentan una sola función `predictedSilenceMs()`, limitada al suelo por idioma (CJK 900-7000 ms, inglés 300-3000 ms). Sin temporizadores paralelos, sin condiciones de carrera.

### El audio siempre activo es estructural

`AudioInputStream` inicia `AVAudioEngine` **una vez por sesión y nunca lo detiene** hasta que la sesión termina. El código anterior detenía/reiniciaba en cada límite de fase; ese patrón acumulaba errores en macOS 26 (`couldn't get default input device, ID = 0`, abortos por `format.sampleRate == inputHWFormat.sampleRate`). Ahora un solo tap difunde los búferes a N consumidores (VAD, STT, detector de interrupción, grabadora de reuniones, medidor de nivel) vía `AsyncStream`.

### Diarización de hablantes en el dispositivo

El modo de actas de reunión usa Apple Accelerate vDSP para calcular un **embedding espectral de log-magnitud de 24 dimensiones normalizado L2** (FFT 1024, ventana de Hann, salto 256) por enunciado. Similitud coseno > 0,82 = el mismo hablante que antes, en caso contrario se asigna un ID nuevo. Sin descarga de modelos, sin llamadas a API. Los hablantes persisten entre reuniones — reetiqueta "Hablante 1" → "지원" una vez y se mantiene.

### El LLM es BYOK

`AssistantClient` es un único protocolo con ocho implementaciones. Los proveedores de CLI (`CLIAssistantClient` para `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) lanzan un subproceso en `~/.talk_mode_mac/work/` con un `currentDirectoryURL` aislado, transmiten stdout frase por frase a `TTSQueue` y nunca ven una clave de API del propio TalkMode. Aportas la suscripción que ya pagas.

### Diagnósticos con privacidad por defecto

La telemetría opcional de PostHog solo reenvía **eventos categorizados**, no el texto subyacente:

- `turn / llm / tts / minutes / alias` → reducidos a `[category] len=N` antes del envío
- `skill` → conserva `skill_id`, descarta `args`
- `fsm / endpointing / session / error / update` → solo metadatos, sin transcripción

Verifícalo en `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (visible en las strings del binario si no me crees).

### Markdown eliminado para TTS, renderizado para el chat

A los LLM les encanta `**bold**` y `### headings`. AVSpeechSynthesizer los lee como "asterisco asterisco negrita asterisco asterisco". `MarkdownStripper.strip(_:)` limpia el texto justo antes de que entre en `TTSQueue` (la burbuja del chat conserva el original mediante `AttributedString(markdown:)`).

### División modular de SwiftPM

Dos targets reutilizables conviven junto a la app principal:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — función `timeout(for:localeID:)` de Foundation puro con 14 pruebas unitarias. Multiplicador `sec/char × 4` por idioma con un suelo; no puede sufrir una regresión silenciosa por un commit no relacionado.
- **`Endpointing`** (`Sources/Endpointing/`) — alberga `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Sin dependencia de AVFoundation / Vision. 7 pruebas unitarias que cubren el traspaso al apartar la mirada, el rechazo con micrófono activo y la limpieza de latches.

`swift test --filter EndpointingTests` y `swift test --filter SpeechWatchdogTests` se ejecutan cada uno contra un módulo diminuto — iteración rápida.

### Máquina de estados

Cada transición de fase (`idle → listening → thinking → speaking → listening …`) pasa por un solo `PhaseStateMachine.transition(to:reason:)`. Las transiciones ilegales se rechazan con un motivo registrado. Aparece en la línea de tiempo de la pestaña de Diagnóstico, así que cuando algo se atasca, puedes ver *qué* arista se negó a activarse.

---

## Comunidad

- **Discussions** — preguntas, ideas, solicitudes de funciones → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — informes de errores → https://github.com/baryonlabs/talkmode-app/issues
- **Correo** — support@baryon.ai

## Licencia

La app compilada es de uso gratuito, personal o comercial — los ZIP de las versiones contienen un único paquete `.app` firmado.

El código fuente de este repositorio está licenciado bajo la **GNU Affero General Public License v3.0** — consulta [LICENSE](../LICENSE). Puedes usarlo, estudiarlo, modificarlo y redistribuirlo, pero cualquier versión modificada — incluida una ofrecida como servicio de red — debe permanecer abierta bajo la misma licencia AGPL-3.0. Baryon Labs posee los derechos de autor; si necesitas términos fuera de AGPL-3.0 (por ejemplo, una licencia comercial), pregunta a través de **Discussions**.

Hecho en Seúl por [Baryon Labs](https://baryon.ai).

<div align="center">

# TalkMode

**Um Mac mini transformado num verdadeiro assistente — voz coreana instantânea, no dispositivo, segundo as suas regras.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | Português | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Repositório público do TalkMode — código-fonte, **Releases**, **Issues** e **Discussions**.
> Consulte **[SECURITY.md](../SECURITY.md)** para saber exatamente como a aplicação lida com os seus dados.

---

## O que é o TalkMode

O TalkMode transforma um Mac mini (ou qualquer Mac com Apple silicon) num **assistente de voz coreano em tempo real** que se comporta como um colega de trabalho, não como um chatbot.

- **Troca de turno em menos de um segundo** com um detetor de fim de fala adaptativo afinado para coreano (olhar + voz + transcrição)
- **Fale para interromper, ou desvie o olhar para concluir** — sinais multimodais, não apenas temporizadores de silêncio
- **4 modos**: conversa · ata de reunião · brainstorming (focado no incentivo) · acompanhamento psicológico (focado na escuta)
- **Diarização de falantes no dispositivo** para atas de reunião (Apple Accelerate vDSP)
- **Skills**: ler o calendário, redigir e-mails, ler SMS, consultar CPU/RAM, guardar memórias, aprender alias
- **8 fornecedores de LLM**: CLIs de Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 idiomas de interface**, mais de 50 configurações regionais de STT
- **Personas**: ficheiros de Alma + Contrato, por idioma, além de um conjunto curado a partir do Nemotron-Personas-Korea da NVIDIA
- **Avatares personalizados** via DiceBear (10 estilos), ImagePlayground (macOS 15.1+) ou a sua própria imagem
- **Privacidade por predefinição**: nada sai do seu Mac exceto (a) o fornecedor de LLM que escolheu e (b) diagnósticos anonimizados com todo o texto livre reduzido a valores de comprimento

---

## Capturas de ecrã

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Separador de conversa — principal" /></a><br/>
      <sub><b>Separador de conversa</b> — avatar do assistente, pré-visualização opcional da câmara para o olhar, sobreposição do nível do microfone e chat ao vivo. O selo laranja "최근" mostra o estado de espírito ativo.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Separador de conversa — conversa em curso" /></a><br/>
      <sub><b>Conversa ao vivo</b> — markdown renderizado em balões, STT com pontuação automática, o emblema "출발 알림" aparece quando uma skill está preparada.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Definições — personalidade do assistente" /></a><br/>
      <sub><b>Definições — Persona</b> — idioma da interface / STT, estilo e género do avatar, geração com ImagePlayground e o contrato vivo <code>soul.md</code> que enquadra cada resposta.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnóstico — cronologia" /></a><br/>
      <sub><b>Diagnóstico</b> — fase, yaw/pitch, olhar, leituras de STT/rosto/CPU e uma cronologia contínua de cada decisão de fim de fala. Desative a cronologia para poupar alguns pontos percentuais de CPU.</sub>
    </td>
  </tr>
</table>

---

## Idiomas suportados

O TalkMode separa o **idioma da interface** (em que estão os menus, botões e mensagens de erro) do **idioma da fala** (em que o assistente transcreve e responde). Podem ser definidos de forma independente — leia a interface em alemão e fale com o assistente em coreano.

### Idiomas da interface (20)

Define-se em **Definições → 언어 → Idioma da interface**. Todos os idiomas estão totalmente traduzidos — todos os menus, botões, definições, descrições de skills e etiquetas de diagnóstico.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Idiomas de fala / conversa

O que quer que o framework Speech do seu Mac suporte — normalmente **50-60 configurações regionais** no macOS Sonoma+. Define-se em **Definições → 언어 → Idioma de reconhecimento de voz**; o seletor lista cada configuração regional devolvida por `SFSpeechRecognizer.supportedLocales()` com as quatro configurações CJK + inglês fixadas no topo.

Sempre disponíveis numa instalação padrão do macOS Sonoma+ (lista parcial — o seu Mac pode ter mais):

| Região | Configurações regionais |
|---|---|
| **Ásia Oriental** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Inglês** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Europa Ocidental** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Europa Central / Oriental** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Grego / Hebraico** | Ελληνικά · עברית |
| **Médio Oriente e Sul da Ásia** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Sudeste Asiático** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Outros** | Türkçe · Русский · Català · Қазақ |

> O conjunto exato depende da versão do sistema operativo e dos idiomas de ditado que descarregou em **Definições do Sistema → Teclado → Ditado**. O TalkMode lê a lista ao vivo no arranque — abra o seletor no seu Mac para o inventário definitivo.

### Vozes TTS

A *saída* de voz usa `AVSpeechSynthesizer` — o mesmo motor da Siri / ditado do macOS. As vozes descarregam-se em **Definições do Sistema → Acessibilidade → Conteúdo falado → Voz do sistema → Gerir vozes**. Coreano: Yuna / Sora; inglês: Samantha / Alex / Daniel / Karen / Moira; japonês: Kyoko / O-Ren; chinês: Mei-Jia / Tian-Tian; etc. As vozes premium (Yuna Premium, etc.) são de maior qualidade, mas exigem rede para o segmento inicial.

---

> 🆕 **Latest features and install guide are in esta tradução.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Instalação

### Homebrew (recomendado)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Transferência direta

[Versão mais recente](https://talkmode.baryon.ai/download/TalkMode-0.4.37.zip) → descompactar → arrastar para `Applications` → no primeiro arranque o macOS pode dizer "de um programador não identificado", clique com o botão direito → Abrir uma vez.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.37.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Atualização automática

O Sparkle 2 está integrado. Uma vez instalado (de qualquer das formas), o TalkMode verifica atualizações em segundo plano — abra `TalkMode → Check for Updates…` ou `Settings → Update` para o controlar.

### Requisitos

- macOS **Sonoma (14.0)** ou posterior
- Apple silicon (M1 / M2 / M3 / M4)
- Um fornecedor de LLM — no mínimo a CLI do Claude, a CLI do Codex ou uma chave da OpenAI

---

## Permissões

As permissões são solicitadas **apenas na primeira vez que usa a funcionalidade**:

| Funcionalidade | Permissão |
|---|---|
| Escuta sempre ativa | Microfone, Reconhecimento de voz |
| Rastreio do olhar (opcional) | Câmara |
| Tecla Option direita para silenciar o TTS | Monitorização de entrada |
| Skills de calendário | Calendários (Acesso total) |
| Compositor de e-mail | Apple Events |
| Skill `messages.list_recent` | Acesso total ao disco (concedido manualmente nas Definições do Sistema) |

Nada é carregado — o STT é executado no dispositivo (ou no servidor STT da Apple, consoante a sua configuração regional), os avatares são PNG locais e o áudio das atas de reunião permanece em `~/.talk_mode_mac/recordings/`.

---

## Segurança e privacidade

O que o TalkMode mantém no seu Mac, o que sai dele e para onde, o que é armazenado em disco e como são geridas as chaves de API e as permissões — juntamente com uma revisão de segurança ao nível do código e as suas conclusões (nenhuma vulnerabilidade explorável remotamente; limitações atuais divulgadas de forma transparente) — está documentado em **[SECURITY.md](../SECURITY.md)**.

---

## Construído com

O TalkMode é uma aplicação macOS baseada em SwiftPM. Dois pacotes Swift de terceiros, o resto são frameworks da Apple.

### Pacotes Swift

| Pacote | Versão | O que faz aqui | Porquê |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Atualização automática na aplicação via um appcast assinado | Padrão da plataforma Apple; usado pelo 1Password, Tower, OBS. Atualizações assinadas com EdDSA, transferência em segundo plano, item de menu "Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Diagnósticos anónimos opcionais (registos ao estilo OpenTelemetry) | Permite-nos ver *quais* transições de fase ficam presas no terreno sem nunca ver o texto do utilizador — todos os campos de texto livre são reduzidos a valores de comprimento antes do envio. |

### Frameworks da Apple

| Framework | Usado para |
|---|---|
| **AVFoundation** | Entrada de tap único com `AVAudioEngine`, TTS com `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), câmara com `AVCaptureSession` |
| **Speech** | STT em streaming com `SpeechAnalyzer` (macOS 26) ou `SFSpeechRecognizer` com `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` para a pose da cabeça → estimativa do olhar (limitado a ~10 fps) |
| **Accelerate (vDSP)** | FFT de 1024 pontos + janela de Hann + embedding espetral de log-magnitude normalizado L2 para a diarização de falantes no dispositivo |
| **EventKit** | Skills de leitura / criação / atualização / eliminação de calendário (âmbito de acesso total) |
| **ImagePlayground** | Geração de avatares no macOS 15.1+ (recorre a um PNG do DiceBear via URLSession caso contrário) |
| **CoreImage / CoreVideo** | Conversão de fotogramas da câmara para a entrada de Vision |
| **AppKit + SwiftUI** | Janela de definições, esquema multi-separador, vista de registo na aplicação |
| **Combine** | Propagação de estado com `@Published` de `ConversationEngine` para toda a interface |
| **OSLog** | Diagnósticos do registo unificado (`subsystem=app.talkmode`) |
| **SQLite3** | Armazém local de alias + memória de skills |
| **UniformTypeIdentifiers** | Seletor de ficheiros de avatar |

### Recursos de terceiros (não código)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 personas curadas por modo (이수민·정아람·박도윤·강예린). Os utilizadores podem substituí-las com `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 estilos de avatar obtidos como PNG, guardados em cache localmente.

---

## Contexto técnico

Algumas opções de design que não são óbvias a partir das capturas de ecrã:

### Deteção de fim de fala multimodal — porque o seu turno termina rápido mas não rápido demais

Os assistentes de voz CJK padrão ou o interrompem no primeiro "음…" ou esperam 3 segundos depois de realmente ter terminado. O `AdaptiveTurnDetector` do TalkMode lê quatro sinais ao mesmo tempo:

1. **Atividade de voz** (EnergyVAD no microfone) — as amostras de silêncio acumulam um orçamento
2. **Transcrição em streaming** (SpeechAnalyzer / SFSpeechRecognizer) — as terminações de ligação coreanas 연결 어미 (`-고`, `-는데`) adicionam 1,2 s; as terminações finais 종결 어미 (`-습니다`, `-요`) subtraem 400 ms; os marcadores de hesitação (`음…`, `어…`) adicionam 1,5 s
3. **Velocidade da fala** (caracteres / segundo) — quem fala depressa obtém um orçamento de pausa menor
4. **Estado do olhar** (yaw / pitch da cabeça via Vision) — olhar para o ecrã multiplica a pausa por 0,3-0,65 (a aguardar), desviar o olhar após uma frase completa multiplica-a por 1,4 *e* arma um disparo rápido imediato (terminou)

Os quatro alimentam uma única função `predictedSilenceMs()`, limitada ao piso por idioma (CJK 900-7000 ms, inglês 300-3000 ms). Sem temporizadores paralelos, sem condições de corrida.

### O áudio sempre ativo é estrutural

O `AudioInputStream` inicia o `AVAudioEngine` **uma vez por sessão e nunca o para** até a sessão terminar. O código anterior parava/reiniciava em cada fronteira de fase; esse padrão acumulava erros no macOS 26 (`couldn't get default input device, ID = 0`, abortos por `format.sampleRate == inputHWFormat.sampleRate`). Agora um único tap difunde os buffers para N consumidores (VAD, STT, detetor de interrupção, gravador de reuniões, medidor de nível) via `AsyncStream`.

### Diarização de falantes no dispositivo

O modo de Atas de reunião usa o Apple Accelerate vDSP para calcular um **embedding espetral de log-magnitude de 24 dimensões normalizado L2** (FFT 1024, janela de Hann, salto 256) por enunciado. Similaridade do cosseno > 0,82 = o mesmo falante de antes, caso contrário é atribuído um novo ID. Sem transferência de modelos, sem chamada de API. Os falantes persistem entre reuniões — renomeie "Falante 1" → "지원" uma vez e mantém-se.

### O LLM é BYOK

O `AssistantClient` é um único protocolo com oito implementações. Os fornecedores de CLI (`CLIAssistantClient` para `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) lançam um subprocesso em `~/.talk_mode_mac/work/` com um `currentDirectoryURL` isolado, transmitem stdout frase a frase para a `TTSQueue` e nunca veem uma chave de API do próprio TalkMode. Traz a subscrição que já paga.

### Diagnósticos com privacidade por predefinição

A telemetria opcional do PostHog apenas reencaminha **eventos categorizados**, não o texto subjacente:

- `turn / llm / tts / minutes / alias` → reduzidos a `[category] len=N` antes do envio
- `skill` → mantém `skill_id`, descarta `args`
- `fsm / endpointing / session / error / update` → apenas metadados, sem transcrição

Verifique em `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (visível nas strings do binário se não confiar em mim).

### Markdown removido para o TTS, renderizado para o chat

Os LLM adoram `**bold**` e `### headings`. O AVSpeechSynthesizer lê-os como "asterisco asterisco negrito asterisco asterisco". O `MarkdownStripper.strip(_:)` limpa o texto mesmo antes de entrar na `TTSQueue` (o balão do chat mantém o original via `AttributedString(markdown:)`).

### Divisão modular de SwiftPM

Dois targets reutilizáveis coexistem ao lado da aplicação principal:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — função `timeout(for:localeID:)` em Foundation puro com 14 testes unitários. Multiplicador `sec/char × 4` por idioma com um piso; não pode sofrer regressão silenciosa por um commit não relacionado.
- **`Endpointing`** (`Sources/Endpointing/`) — alberga `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Sem dependência de AVFoundation / Vision. 7 testes unitários que cobrem a transferência ao desviar o olhar, a rejeição com microfone ativo, a limpeza de latches.

`swift test --filter EndpointingTests` e `swift test --filter SpeechWatchdogTests` correm cada um contra um módulo minúsculo — iteração rápida.

### Máquina de estados

Cada transição de fase (`idle → listening → thinking → speaking → listening …`) passa por um único `PhaseStateMachine.transition(to:reason:)`. As transições ilegais são rejeitadas com um motivo registado. Surge na cronologia do separador de Diagnóstico, por isso, quando algo fica preso, pode ver *que* aresta se recusou a disparar.

---

## Comunidade

- **Discussions** — perguntas, ideias, pedidos de funcionalidades → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — relatórios de erros → https://github.com/baryonlabs/talkmode-app/issues
- **E-mail** — support@baryon.ai

## Licença

A aplicação compilada é de utilização gratuita, pessoal ou comercial — os ZIP das versões contêm um único pacote `.app` assinado.

O código-fonte deste repositório está licenciado sob a **GNU Affero General Public License v3.0** — ver [LICENSE](../LICENSE). Pode usá-lo, estudá-lo, modificá-lo e redistribuí-lo, mas qualquer versão modificada — incluindo uma oferecida como serviço de rede — deve permanecer aberta sob a mesma licença AGPL-3.0. A Baryon Labs detém os direitos de autor; se precisar de termos fora da AGPL-3.0 (por exemplo, uma licença comercial), pergunte através das **Discussions**.

Feito em Seul pela [Baryon Labs](https://baryon.ai).

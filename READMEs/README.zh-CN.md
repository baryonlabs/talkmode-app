<div align="center">

# TalkMode

**把 Mac mini 变成真正的助手 — 即时语音、全程 on-device、按你的规则来。**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | 简体中文 | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> TalkMode 的公开仓库 — 源码、**Releases**、**Issues** 和 **Discussions**。
> 关于应用如何处理你的数据的确切方式，请参阅 **[SECURITY.md](../SECURITY.md)**。

---

## TalkMode 是什么

TalkMode 把 Mac mini（或任意 Apple silicon Mac）变成一个**实时韩语语音助手**，它的行为像一位同事，而不是聊天机器人。

- 借助为韩语调优的自适应端点检测器（视线 + 语音 + 转录），实现**亚秒级的轮次切换**
- **说话即可打断，移开视线即可收尾** — 多模态线索，而不仅仅是静默计时器
- **4 种模式**：对话 · 会议纪要 · 头脑风暴（侧重附和）· 心理咨询（侧重倾听）
- 为会议纪要提供 **on-device 说话人分离**（Apple Accelerate vDSP）
- **技能**：读取日历、起草邮件、读取短信、查询 CPU/RAM、保存记忆、学习别名
- **8 个 LLM 提供方**：Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLI + OpenAI + Mock
- **20 种界面语言**，50+ 种 STT 区域
- **角色**：按语言区分的 Soul + Contract 文件，外加一套精选自 NVIDIA 的 Nemotron-Personas-Korea
- 通过 DiceBear（10 种风格）、ImagePlayground（macOS 15.1+）或你自己的图片实现**自定义头像**
- **默认隐私优先**：除 (a) 你选择的 LLM 提供方和 (b) 已将所有自由文本剥离为长度值的匿名诊断信息外，没有任何内容离开你的 Mac

---

## 截图

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="对话标签页 — 主界面" /></a><br/>
      <sub><b>对话标签页</b> — 助手头像、用于视线追踪的可选摄像头预览、麦克风电平叠加层以及实时聊天。橙色的"最近"标签显示当前的情绪。</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="对话标签页 — 对话进行中" /></a><br/>
      <sub><b>实时对话</b> — 气泡中渲染 Markdown，STT 自动添加标点，当技能就绪时会显示"出发提醒"徽章。</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="设置 — 助手人格" /></a><br/>
      <sub><b>设置 — 角色</b> — 界面 / STT 语言、头像风格与性别、ImagePlayground 生成，以及为每条回复定调的实时 <code>soul.md</code> 契约。</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="诊断 — 时间线" /></a><br/>
      <sub><b>诊断</b> — 阶段、yaw/pitch、视线、STT/人脸/CPU 读数，以及每次端点检测决策的滚动时间线。关闭时间线可节省几个百分点的 CPU。</sub>
    </td>
  </tr>
</table>

---

## 支持的语言

TalkMode 将**界面语言**（菜单、按钮和错误消息所用的语言）与**语音语言**（助手转录和回复所用的语言）分开。两者可以独立设置 — 用德语界面，同时用韩语和助手交谈。

### 界面语言（20 种）

在**设置 → 语言 → 界面语言**中设置。每种语言都已完整翻译 — 所有菜单、按钮、设置、技能描述和诊断标签。

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### 语音 / 对话语言

取决于你 Mac 的 Speech 框架所支持的范围 — 在 macOS Sonoma+ 上通常为 **50-60 种区域**。在**设置 → 语言 → 语音识别语言**中设置；选择器会列出 `SFSpeechRecognizer.supportedLocales()` 返回的所有区域，并将 4 种 CJK + 英语区域置顶。

在标准的 macOS Sonoma+ 安装上始终可用（部分列表 — 你的 Mac 上可能更多）：

| 区域 | 语言区域 |
|---|---|
| **东亚** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **英语** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **西欧** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **中欧 / 东欧** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **希腊语 / 希伯来语** | Ελληνικά · עברית |
| **中东与南亚** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **东南亚** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **其他** | Türkçe · Русский · Català · Қазақ |

> 确切的集合取决于操作系统版本以及你在**系统设置 → 键盘 → 听写**下下载的听写语言。TalkMode 在启动时读取实时列表 — 请在你的 Mac 上打开选择器以获取权威清单。

### TTS 语音

语音*输出*使用 `AVSpeechSynthesizer` — 与 macOS Siri / 听写相同的引擎。语音在**系统设置 → 辅助功能 → 朗读内容 → 系统语音 → 管理语音**下下载。韩语：Yuna / Sora；英语：Samantha / Alex / Daniel / Karen / Moira；日语：Kyoko / O-Ren；中文：Mei-Jia / Tian-Tian；等等。高级语音（Yuna Premium 等）质量更高，但首个音频块需要联网。

---

> 🆕 **Latest features and install guide are in this translation.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## 安装

### Homebrew（推荐）

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### 直接下载

[最新版本](https://talkmode.baryon.ai/download/TalkMode-0.4.33.zip) → 解压 → 拖入 `Applications` → 首次启动时 macOS 可能会提示"来自身份不明的开发者"，右键点击 → 选择一次"打开"。

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.33.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### 自动更新

内置 Sparkle 2。安装后（无论用哪种方式），TalkMode 会在后台检查更新 — 可通过 `TalkMode → 检查更新…` 或 `设置 → 更新`来控制。

### 系统要求

- macOS **Sonoma (14.0)** 或更高版本
- Apple silicon (M1 / M2 / M3 / M4)
- 一个 LLM 提供方 — 至少是 Claude CLI、Codex CLI 或一个 OpenAI 密钥

---

## 权限

权限**只在你首次使用相应功能时**才会被请求：

| 功能 | 权限 |
|---|---|
| 常时聆听 | 麦克风、语音识别 |
| 视线追踪（可选） | 摄像头 |
| 用右 Option 键静音 TTS | 输入监控 |
| 日历技能 | 日历（完全访问权限） |
| 邮件撰写器 | Apple Events |
| `messages.list_recent` 技能 | 完全磁盘访问权限（在系统设置中手动授予） |

没有任何内容被上传 — STT 在 on-device 运行（或根据你的区域使用 Apple 的 STT 服务器），头像是本地 PNG，会议纪要的音频保留在 `~/.talk_mode_mac/recordings/` 中。

---

## 安全与隐私

TalkMode 在你 Mac 上保留什么、什么内容会发往何处、什么内容存储在磁盘上、API 密钥和权限如何处理 — 连同代码级别的安全审查及其结论（不存在可远程利用的漏洞；当前的局限性已透明披露）— 都记录在 **[SECURITY.md](../SECURITY.md)** 中。

---

## 技术栈

TalkMode 是一个基于 SwiftPM 的 macOS 应用。除两个第三方 Swift 包外，其余都是 Apple 框架。

### Swift 包

| 包 | 版本 | 在此处的作用 | 原因 |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | 通过签名的 appcast 实现应用内自动更新 | Apple 平台的标准；被 1Password、Tower、OBS 使用。EdDSA 签名更新、后台下载、"检查更新…"菜单项。 |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | 选择加入的匿名诊断（OpenTelemetry 风格的日志） | 让我们在永远看不到用户文本的前提下，了解实际环境中*哪些*阶段转换出现停滞 — 所有自由格式字段在发送前都会缩减为长度值。 |

### Apple 框架

| 框架 | 用途 |
|---|---|
| **AVFoundation** | `AVAudioEngine` 单点采集输入、`AVSpeechSynthesizer` TTS（Yuna / Premium / Personal Voice）、`AVCaptureSession` 摄像头 |
| **Speech** | `SpeechAnalyzer`（macOS 26）或 `SFSpeechRecognizer` 流式 STT，启用 `addsPunctuation` |
| **Vision** | 用于头部姿态 → 视线估计的 `VNDetectFaceLandmarksRequest`（限流至约 10 fps） |
| **Accelerate (vDSP)** | 用于 on-device 说话人分离的 1024 点 FFT + Hann 窗 + L2 归一化对数幅度谱嵌入 |
| **EventKit** | 日历读取 / 创建 / 更新 / 删除技能（完全访问范围） |
| **ImagePlayground** | macOS 15.1+ 头像生成（否则回退到通过 URLSession 获取的 DiceBear PNG） |
| **CoreImage / CoreVideo** | 用于 Vision 输入的摄像头帧转换 |
| **AppKit + SwiftUI** | 设置窗口、多标签布局、应用内日志视图 |
| **Combine** | 从 `ConversationEngine` 向所有 UI 传播 `@Published` 状态 |
| **OSLog** | 统一日志诊断（`subsystem=app.talkmode`） |
| **SQLite3** | 本地别名存储 + 技能记忆 |
| **UniformTypeIdentifiers** | 头像文件选择器 |

### 第三方（非代码）资源

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)**（CC BY 4.0）— 每种模式 4 个精选角色（이수민·정아람·박도윤·강예린）。用户可通过 `nemotron-extras.json` 覆盖。
- **[DiceBear](https://www.dicebear.com)** — 以 PNG 形式获取并本地缓存的 10 种头像风格。

---

## 技术背景

一些从截图中看不出来的设计选择：

### 多模态端点检测 — 为什么你的轮次结束得快但不会太快

标准的 CJK 语音助手要么在你第一声"嗯…"时就打断你，要么在你真正说完后再等 3 秒。TalkMode 的 `AdaptiveTurnDetector` 同时读取四个信号：

1. **语音活动**（麦克风上的 EnergyVAD）— 静默样本累积出一个预算
2. **流式转录**（SpeechAnalyzer / SFSpeechRecognizer）— 韩语连接词尾（`-고`、`-는데`）增加 1.2 秒；终结词尾（`-습니다`、`-요`）减少 400 毫秒；犹豫标记（`음…`、`어…`）增加 1.5 秒
3. **语速**（字符 / 秒）— 说话快的人获得更小的停顿预算
4. **视线状态**（通过 Vision 得到的头部 yaw / pitch）— 看着屏幕会把停顿乘以 0.3-0.65（等待中），在完整句子之后移开视线则乘以 1.4 *并且*装备一次即时快速触发（你说完了）

四者全部汇入一个 `predictedSilenceMs()` 函数，并被钳制到各语言的下限（CJK 900-7000 毫秒，英语 300-3000 毫秒）。没有并行计时器，没有竞态条件。

### 常时音频是关键所在

`AudioInputStream` **每个会话只启动一次 `AVAudioEngine`，并且在会话结束前从不停止它**。早期代码在每个阶段边界停止/重启；这种模式在 macOS 26 上积累了大量 bug（`couldn't get default input device, ID = 0`、`format.sampleRate == inputHWFormat.sampleRate` 中止）。现在一个采集点通过 `AsyncStream` 将缓冲区广播给 N 个消费者（VAD、STT、打断检测器、会议录制器、电平表）。

### on-device 说话人分离

会议纪要模式使用 Apple Accelerate vDSP 为每段话语计算一个**24 维 L2 归一化对数幅度谱嵌入**（FFT 1024、Hann 窗、hop 256）。余弦相似度 > 0.82 即与之前是同一说话人，否则分配一个新 ID。无需下载模型，无需 API 调用。说话人跨会议保持 — 把"说话人 1"重新标注为"지원"一次，它就会一直保持。

### LLM 是 BYOK

`AssistantClient` 是一个协议，带有八个实现。CLI 提供方（用于 `claude`、`codex`、`gemini`、`cursor-agent`、`kimi`、`opencode` 的 `CLIAssistantClient`）会以沙盒化的 `currentDirectoryURL` 在 `~/.talk_mode_mac/work/` 中启动一个子进程，将 stdout 逐句流式传入 `TTSQueue`，并且永远不会从 TalkMode 本身看到 API 密钥。你带上自己已经在付费的订阅即可。

### 默认隐私优先的诊断

选择加入的 PostHog 遥测只转发**已分类的事件**，而非底层文本：

- `turn / llm / tts / minutes / alias` → 发送前缩减为 `[category] len=N`
- `skill` → 保留 `skill_id`，丢弃 `args`
- `fsm / endpointing / session / error / update` → 仅元数据，无转录文本

可在 `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` 中核实（如果你不信我，在二进制文件的 strings 中也能看到）。

### Markdown 为 TTS 剥离，为聊天渲染

LLM 喜欢 `**bold**` 和 `### headings`。AVSpeechSynthesizer 会把它们读成"星号 星号 加粗 星号 星号"。`MarkdownStripper.strip(_:)` 会在文本进入 `TTSQueue` 之前对其进行清理（聊天气泡通过 `AttributedString(markdown:)` 保留原文）。

### 模块化 SwiftPM 拆分

主应用旁边还有两个可复用的目标：

- **`SpeechWatchdog`**（`Sources/SpeechWatchdog/`）— 纯 Foundation 的 `timeout(for:localeID:)` 函数，带 14 个单元测试。带下限的、按语言的 `sec/char × 4` 乘数；不会被无关的提交悄悄回退。
- **`Endpointing`**（`Sources/Endpointing/`）— 拥有 `AdaptiveTurnDetector`、`VoiceActivity`、`GazeState`。不依赖 AVFoundation / Vision。7 个单元测试，覆盖移开视线交接、麦克风激活拒绝、闩锁清除。

`swift test --filter EndpointingTests` 和 `swift test --filter SpeechWatchdogTests` 各自针对一个小模块运行 — 迭代迅速。

### 状态机

每一次阶段转换（`idle → listening → thinking → speaking → listening …`）都经过同一个 `PhaseStateMachine.transition(to:reason:)`。非法转换会被拒绝并记录原因。它会显示在诊断标签页的时间线中，因此当某处卡住时，你能看到*哪条*边拒绝了触发。

---

## 社区

- **Discussions** — 问题、想法、功能请求 → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — bug 报告 → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## 许可证

编译后的应用可免费使用，无论个人还是商用 — 发布的 ZIP 包含单个已签名的 `.app` 包。

本仓库中的源码采用 **GNU Affero General Public License v3.0** 许可 — 参见 [LICENSE](../LICENSE)。你可以使用、研究、修改和再分发它，但任何修改版本 — 包括作为网络服务提供的版本 — 都必须以相同的 AGPL-3.0 许可保持开放。版权归 Baryon Labs 所有；如果你需要 AGPL-3.0 之外的条款（例如商业许可），请通过 **Discussions** 询问。

由 [Baryon Labs](https://baryon.ai) 在首尔制作。

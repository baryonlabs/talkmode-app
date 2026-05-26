<div align="center">

# TalkMode

**Mac mini を本物のアシスタントに — 即応する音声、すべて on-device、あなたのルールで。**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | 日本語 | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> TalkMode の公開リポジトリ — ソース、**リリース**、**Issue**、**Discussions**。
> アプリがあなたのデータをどう扱うかの正確な詳細は **[SECURITY.md](../SECURITY.md)** を参照してください。

---

## TalkMode とは

TalkMode は Mac mini（または任意の Apple silicon Mac）を、チャットボットではなく同僚のように振る舞う**リアルタイム韓国語音声アシスタント**に変えます。

- 韓国語向けに調整された適応型エンドポインター（視線 + 音声 + 文字起こし）による**1秒未満のターン交代**
- **割り込みたいなら話しかけ、切り上げたいなら視線をそらす** — 単なる無音タイマーではなくマルチモーダルな手がかり
- **4つのモード**: 会話 · 議事録 · ブレインストーミング（相づち重視）· カウンセリング（傾聴重視）
- 議事録のための **on-device 話者ダイアライゼーション**（Apple Accelerate vDSP）
- **スキル**: カレンダーの読み取り、メールの下書き、SMS の読み取り、CPU/RAM の照会、メモリの保存、エイリアスの学習
- **8つの LLM プロバイダー**: Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLI + OpenAI + Mock
- **20の UI 言語**、50以上の STT ロケール
- **ペルソナ**: 言語ごとの Soul + Contract ファイル、加えて NVIDIA の Nemotron-Personas-Korea から厳選したセット
- DiceBear（10スタイル）、ImagePlayground（macOS 15.1+）、または自分の画像による**カスタムアバター**
- **デフォルトでプライバシー優先**: (a) 選択した LLM プロバイダーと (b) すべての自由テキストを長さの値に置き換えた匿名診断情報を除き、Mac から外に出るものはありません

---

## スクリーンショット

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="会話タブ — メイン" /></a><br/>
      <sub><b>会話タブ</b> — アシスタントのアバター、視線用のオプションのカメラプレビュー、マイクレベルのオーバーレイ、ライブチャット。オレンジ色の「最近」チップは現在のムードを表示します。</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="会話タブ — 会話進行中" /></a><br/>
      <sub><b>ライブ会話</b> — バブル内に Markdown レンダリング、STT 自動句読点、スキルが準備されると「出発通知」バッジが表示されます。</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="設定 — アシスタントの人格" /></a><br/>
      <sub><b>設定 — ペルソナ</b> — UI / STT 言語、アバターのスタイルと性別、ImagePlayground 生成、そしてすべての返答を方向づけるライブの <code>soul.md</code> 契約。</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="診断 — タイムライン" /></a><br/>
      <sub><b>診断</b> — フェーズ、yaw/pitch、視線、STT/顔/CPU の表示、そしてすべてのエンドポインティング判断のローリングタイムライン。タイムラインをオフにすると CPU を数 % 節約できます。</sub>
    </td>
  </tr>
</table>

---

## 対応言語

TalkMode は **UI 言語**（メニュー、ボタン、エラーメッセージの言語）と**音声言語**（アシスタントが文字起こしし、返答する言語）を分離しています。両者は独立して設定でき、ドイツ語の UI を見ながら韓国語でアシスタントと話すことができます。

### UI 言語（20）

**設定 → 言語 → UI 言語**で設定します。すべての言語が完全に翻訳されています — メニュー、ボタン、設定、スキルの説明、診断ラベルのすべて。

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### 音声 / 会話言語

Mac の Speech フレームワークが対応するものすべて — macOS Sonoma+ では通常 **50〜60ロケール**です。**設定 → 言語 → 音声認識言語**で設定し、ピッカーは `SFSpeechRecognizer.supportedLocales()` が返すすべてのロケールを一覧表示し、4つの CJK + 英語ロケールを最上部に固定します。

標準の macOS Sonoma+ インストールで常に利用可能（一部のリスト — お使いの Mac にはさらに多いかもしれません）:

| 地域 | ロケール |
|---|---|
| **東アジア** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **英語** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **西ヨーロッパ** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **中央 / 東ヨーロッパ** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **ギリシャ語 / ヘブライ語** | Ελληνικά · עברית |
| **中東 & 南アジア** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **東南アジア** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **その他** | Türkçe · Русский · Català · Қазақ |

> 正確なセットは OS のバージョンと、**システム設定 → キーボード → 音声入力**でダウンロードした音声入力言語によって異なります。TalkMode は起動時にライブのリストを読み込みます — 正確な一覧はお使いの Mac でピッカーを開いて確認してください。

### TTS 音声

音声*出力*は `AVSpeechSynthesizer` を使用します — macOS Siri / 音声入力と同じエンジンです。音声は**システム設定 → アクセシビリティ → 読み上げコンテンツ → システムの声 → 声を管理**でダウンロードします。韓国語: Yuna / Sora; 英語: Samantha / Alex / Daniel / Karen / Moira; 日本語: Kyoko / O-Ren; 中国語: Mei-Jia / Tian-Tian など。プレミアム音声（Yuna Premium など）はより高品質ですが、最初のチャンクにはネットワークが必要です。

---

> 🆕 **Latest features and install guide are in this translation.** This translation covers the core docs; the visual install walkthrough, free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## インストール

### Homebrew（推奨）

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### 直接ダウンロード

[最新リリース](https://talkmode.baryon.ai/download/TalkMode-0.4.31.zip) → 解凍 → `Applications` にドラッグ → 初回起動時に macOS が「不明な開発者」と表示する場合があるので、右クリック → 一度「開く」を選択。

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.31.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### 自動アップデート

Sparkle 2 が組み込まれています。インストール後（どちらの方法でも）、TalkMode はバックグラウンドでアップデートを確認します — `TalkMode → アップデートを確認…` または `設定 → アップデート`で制御できます。

### 要件

- macOS **Sonoma (14.0)** 以降
- Apple silicon (M1 / M2 / M3 / M4)
- LLM プロバイダー — 少なくとも Claude CLI、Codex CLI、または OpenAI キー

---

## 権限

権限は**その機能を初めて使うときのみ**要求されます:

| 機能 | 権限 |
|---|---|
| 常時リスニング | マイク、音声認識 |
| 視線トラッキング（オプション） | カメラ |
| 右 Option で TTS を消音 | 入力監視 |
| カレンダースキル | カレンダー（フルアクセス） |
| メール作成 | Apple Events |
| `messages.list_recent` スキル | フルディスクアクセス（システム設定で手動で付与） |

アップロードされるものはありません — STT は on-device（またはロケールによっては Apple の STT サーバー）で実行され、アバターはローカルの PNG、議事録の音声は `~/.talk_mode_mac/recordings/` に残ります。

---

## セキュリティ & プライバシー

TalkMode が Mac 上に保持するもの、何がどこへ出ていくか、ディスクに保存されるもの、API キーと権限がどう扱われるか — コードレベルのセキュリティレビューとその結果（リモートから悪用可能な脆弱性なし; 現在の制限事項は透明に開示）とともに — はすべて **[SECURITY.md](../SECURITY.md)** に文書化されています。

---

## 使用技術

TalkMode は SwiftPM ベースの macOS アプリです。サードパーティの Swift パッケージ2つを除き、残りは Apple のフレームワークです。

### Swift パッケージ

| パッケージ | バージョン | ここでの役割 | 理由 |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | 署名付き appcast によるアプリ内自動アップデート | Apple プラットフォームの標準; 1Password、Tower、OBS で使用。EdDSA 署名付きアップデート、バックグラウンドダウンロード、「アップデートを確認…」メニュー項目。 |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | オプトインの匿名診断（OpenTelemetry スタイルのログ） | ユーザーのテキストを一切見ることなく、実環境で*どの*フェーズ遷移が停滞しているかを把握できます — すべての自由形式フィールドは送信前に長さの値に縮小されます。 |

### Apple フレームワーク

| フレームワーク | 用途 |
|---|---|
| **AVFoundation** | `AVAudioEngine` シングルタップ入力、`AVSpeechSynthesizer` TTS（Yuna / Premium / Personal Voice）、`AVCaptureSession` カメラ |
| **Speech** | `SpeechAnalyzer`（macOS 26）または `SFSpeechRecognizer` ストリーミング STT、`addsPunctuation` 適用 |
| **Vision** | 頭の姿勢 → 視線推定のための `VNDetectFaceLandmarksRequest`（約 10 fps にスロットル） |
| **Accelerate (vDSP)** | on-device 話者ダイアライゼーションのための 1024 ポイント FFT + Hann ウィンドウ + L2 正規化ログ振幅スペクトル埋め込み |
| **EventKit** | カレンダーの読み取り / 作成 / 更新 / 削除スキル（フルアクセス範囲） |
| **ImagePlayground** | macOS 15.1+ のアバター生成（それ以外は URLSession 経由の DiceBear PNG にフォールバック） |
| **CoreImage / CoreVideo** | Vision 入力のためのカメラフレーム変換 |
| **AppKit + SwiftUI** | 設定ウィンドウ、マルチタブレイアウト、アプリ内ログビュー |
| **Combine** | `ConversationEngine` からすべての UI への `@Published` 状態の伝播 |
| **OSLog** | 統合ログ診断（`subsystem=app.talkmode`） |
| **SQLite3** | ローカルのエイリアスストア + スキルメモリ |
| **UniformTypeIdentifiers** | アバターファイルピッカー |

### サードパーティ（非コード）アセット

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)**（CC BY 4.0）— モードごとに厳選されたペルソナ4種（이수민·정아람·박도윤·강예린）。ユーザーは `nemotron-extras.json` で上書きできます。
- **[DiceBear](https://www.dicebear.com)** — PNG として取得しローカルにキャッシュされる10種のアバタースタイル。

---

## 技術的背景

スクリーンショットからは明らかではない、いくつかの設計上の選択:

### マルチモーダルエンドポインティング — ターンが速く、しかし速すぎずに終わる理由

標準的な CJK 音声アシスタントは、最初の「えー…」で話を遮るか、実際に話し終えてから3秒待ちます。TalkMode の `AdaptiveTurnDetector` は4つの信号を同時に読み取ります:

1. **音声活動**（マイクの EnergyVAD）— 無音サンプルが予算を蓄積
2. **ストリーミング文字起こし**（SpeechAnalyzer / SFSpeechRecognizer）— 韓国語の連結語尾（`-고`、`-는데`）は 1.2 秒追加; 終結語尾（`-습니다`、`-요`）は 400 ms 減算; ためらいの表現（`음…`、`어…`）は 1.5 秒追加
3. **発話速度**（文字 / 秒）— 早口の人ほど無音予算が小さくなる
4. **視線状態**（Vision による頭の yaw / pitch）— 画面を見ていると無音に 0.3〜0.65 を乗算（待機中）、完全な文の後に視線をそらすと 1.4 を乗算し、*同時に*即座の高速発火を準備（話し終わった）

4つすべてが1つの `predictedSilenceMs()` 関数に入り、言語ごとの下限（CJK 900〜7000 ms、英語 300〜3000 ms）にクランプされます。並列タイマーなし、競合状態なし。

### 常時オーディオが要

`AudioInputStream` は `AVAudioEngine` を**セッションごとに一度起動し、セッションが終わるまで決して停止しません**。以前のコードはフェーズの境界ごとに停止/再起動していましたが、そのパターンは macOS 26 でバグを蓄積させました（`couldn't get default input device, ID = 0`、`format.sampleRate == inputHWFormat.sampleRate` の中断）。今では1つのタップが `AsyncStream` を介して N 個のコンシューマー（VAD、STT、割り込み検出器、会議レコーダー、レベルメーター）にバッファをブロードキャストします。

### on-device 話者ダイアライゼーション

議事録モードは Apple Accelerate vDSP を使って、発話ごとに**24次元の L2 正規化ログ振幅スペクトル埋め込み**（FFT 1024、Hann ウィンドウ、hop 256）を計算します。コサイン類似度 > 0.82 なら以前と同じ話者、そうでなければ新しい ID を割り当てます。モデルのダウンロードなし、API 呼び出しなし。話者は会議をまたいで保持されます — 「話者 1」→「지원」と一度ラベルを付け直せば、そのまま維持されます。

### LLM は BYOK

`AssistantClient` は8つの実装を持つ1つのプロトコルです。CLI プロバイダー（`claude`、`codex`、`gemini`、`cursor-agent`、`kimi`、`opencode` 用の `CLIAssistantClient`）はサンドボックス化された `currentDirectoryURL` で `~/.talk_mode_mac/work/` にサブプロセスを起動し、stdout を文ごとに `TTSQueue` にストリーミングし、TalkMode 自体が API キーを見ることはありません。すでに支払っているサブスクリプションをそのまま持ち込みます。

### デフォルトでプライバシー優先の診断

オプトインの PostHog テレメトリは、基盤となるテキストではなく**分類されたイベント**のみを転送します:

- `turn / llm / tts / minutes / alias` → 送信前に `[category] len=N` に縮小
- `skill` → `skill_id` は保持、`args` は削除
- `fsm / endpointing / session / error / update` → メタデータのみ、文字起こしなし

`Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` で確認できます（私を信用できなければバイナリの strings でも見られます）。

### Markdown は TTS 用に除去、チャット用にレンダリング

LLM は `**bold**` や `### headings` を好みます。AVSpeechSynthesizer はそれらを「アスタリスク アスタリスク 太字 アスタリスク アスタリスク」と読み上げます。`MarkdownStripper.strip(_:)` はテキストが `TTSQueue` に入る直前にクリーンアップします（チャットバブルは `AttributedString(markdown:)` で元のものを保持）。

### モジュール式 SwiftPM 分割

メインアプリと並んで、再利用可能な2つのターゲットがあります:

- **`SpeechWatchdog`**（`Sources/SpeechWatchdog/`）— 14のユニットテストを持つ純粋な Foundation の `timeout(for:localeID:)` 関数。下限を持つ言語ごとの `sec/char × 4` 乗数; 無関係なコミットによって静かに退行させられることはありません。
- **`Endpointing`**（`Sources/Endpointing/`）— `AdaptiveTurnDetector`、`VoiceActivity`、`GazeState` を所有します。AVFoundation / Vision への依存なし。視線そらしの引き継ぎ、マイク有効時の拒否、ラッチクリアをカバーする7つのユニットテスト。

`swift test --filter EndpointingTests` と `swift test --filter SpeechWatchdogTests` はそれぞれ小さなモジュールに対して実行されます — 高速なイテレーション。

### ステートマシン

すべてのフェーズ遷移（`idle → listening → thinking → speaking → listening …`）は1つの `PhaseStateMachine.transition(to:reason:)` を通ります。不正な遷移はログに記録された理由とともに拒否されます。診断タブのタイムラインに表示されるので、何かが詰まったときに*どの*エッジが発火を拒否したかを見ることができます。

---

## コミュニティ

- **Discussions** — 質問、アイデア、機能リクエスト → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — バグ報告 → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## ライセンス

コンパイル済みのアプリは個人用でも商用でも無料で使用できます — リリース ZIP には署名済みの単一の `.app` バンドルが含まれます。

このリポジトリのソースは **GNU Affero General Public License v3.0** の下でライセンスされています — [LICENSE](../LICENSE) を参照してください。使用、研究、改変、再配布が可能ですが、改変版 — ネットワークサービスとして提供されるものを含む — は同じ AGPL-3.0 ライセンスの下でオープンなままでなければなりません。著作権は Baryon Labs が保有します; AGPL-3.0 以外の条件（例: 商用ライセンス）が必要な場合は **Discussions** から問い合わせてください。

ソウルにて [Baryon Labs](https://baryon.ai) が制作。

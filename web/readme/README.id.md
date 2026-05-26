<div align="center">

# TalkMode

**Mac mini berubah menjadi asisten sungguhan — suara Korea seketika, on-device, sesuai aturan Anda.**
**Jadikan Mac mini sebagai asisten sungguhan. Jawaban suara seketika, semua on-device, sesuai aturan yang Anda tetapkan.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | Bahasa Indonesia | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Repositori publik untuk TalkMode — kode sumber, **Releases**, **Issues**, dan **Discussions**.
> Lihat **[SECURITY.md](../SECURITY.md)** untuk mengetahui persis bagaimana aplikasi menangani data Anda.

---

## Apa itu TalkMode

TalkMode mengubah Mac mini (atau Mac Apple-silicon mana pun) menjadi **asisten suara Korea real-time** yang berperilaku seperti rekan kerja, bukan chatbot.

- **Pergantian giliran di bawah satu detik** dengan endpointer adaptif yang disetel untuk bahasa Korea (tatapan + suara + transkrip)
- **Bicara untuk menyela, atau alihkan pandangan untuk mengakhiri** — isyarat multimodal, bukan sekadar pengatur waktu keheningan
- **4 mode**: percakapan · notula rapat · curah gagasan (berpusat pada respons mendukung) · konseling psikologis (berpusat pada mendengarkan)
- **Diarisasi pembicara on-device** untuk notula rapat (Apple Accelerate vDSP)
- **Keterampilan**: membaca kalender, menyusun email, membaca SMS, menanyakan penggunaan CPU/RAM, menyimpan memori, mempelajari alias
- **8 penyedia LLM**: CLI Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 bahasa UI**, 50+ lokal STT
- **Persona**: berkas Soul + Contract, per bahasa, plus kumpulan terkurasi dari NVIDIA Nemotron-Personas-Korea
- **Avatar khusus** melalui DiceBear (10 gaya), ImagePlayground (macOS 15.1+), atau gambar Anda sendiri
- **Privasi sebagai bawaan**: tidak ada yang keluar dari Mac Anda kecuali (a) penyedia LLM yang Anda pilih dan (b) diagnostik anonim dengan seluruh teks bebas diringkas menjadi nilai panjang

---

## Tangkapan layar

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Tab percakapan — utama" /></a><br/>
      <sub><b>Tab percakapan</b> — avatar asisten, pratinjau kamera opsional untuk tatapan, overlay tingkat mikrofon, dan obrolan langsung. Chip oranye "terbaru" menunjukkan suasana hati yang aktif.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Tab percakapan — percakapan berlangsung" /></a><br/>
      <sub><b>Percakapan langsung</b> — markdown dirender dalam gelembung, STT memberi tanda baca otomatis, lencana "notifikasi keberangkatan" muncul saat sebuah keterampilan disiapkan.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Pengaturan — kepribadian asisten" /></a><br/>
      <sub><b>Pengaturan — Persona</b> — bahasa UI / STT, gaya dan jenis kelamin avatar, pembuatan via ImagePlayground, serta kontrak <code>soul.md</code> langsung yang membingkai setiap balasan.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Diagnostik — linimasa" /></a><br/>
      <sub><b>Diagnostik</b> — fase, yaw/pitch, tatapan, pembacaan STT/wajah/CPU, dan linimasa berjalan dari setiap keputusan endpointing. Matikan linimasa untuk menghemat beberapa persen CPU.</sub>
    </td>
  </tr>
</table>

---

## Bahasa yang didukung

TalkMode memisahkan **bahasa UI** (bahasa menu, tombol, dan pesan kesalahan) dari **bahasa ucapan** (bahasa yang ditranskripsikan dan dibalas oleh asisten). Keduanya dapat diatur secara mandiri — baca UI dalam bahasa Jerman, bicara dengan asisten dalam bahasa Korea.

### Bahasa UI (20)

Diatur di **Pengaturan → Bahasa → Bahasa UI**. Setiap bahasa diterjemahkan sepenuhnya — semua menu, tombol, pengaturan, deskripsi keterampilan, dan label diagnostik.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Bahasa ucapan / percakapan

Apa pun yang didukung framework Speech Mac Anda — biasanya **50-60 lokal** pada macOS Sonoma+. Diatur di **Pengaturan → Bahasa → Bahasa pengenalan ucapan**; pemilih mencantumkan setiap lokal yang dikembalikan `SFSpeechRecognizer.supportedLocales()` dengan empat lokal CJK + Inggris disematkan di atas.

Selalu tersedia pada instalasi macOS Sonoma+ standar (daftar sebagian — Mac Anda mungkin memiliki lebih banyak):

| Wilayah | Lokal |
|---|---|
| **Asia Timur** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Inggris** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Eropa Barat** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Eropa Tengah / Timur** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Yunani / Ibrani** | Ελληνικά · עברית |
| **Timur Tengah & Asia Selatan** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Asia Tenggara** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Lainnya** | Türkçe · Русский · Català · Қазақ |

> Kumpulan persisnya bergantung pada versi OS dan bahasa dikte yang telah Anda unduh di **Pengaturan Sistem → Keyboard → Dikte**. TalkMode membaca daftar langsung saat peluncuran — buka pemilih di Mac Anda untuk inventaris yang otoritatif.

### Suara TTS

*Keluaran* ucapan menggunakan `AVSpeechSynthesizer` — mesin yang sama dengan Siri / dikte macOS. Suara diunduh di **Pengaturan Sistem → Aksesibilitas → Konten Lisan → Suara Sistem → Kelola Suara**. Korea: Yuna / Sora; Inggris: Samantha / Alex / Daniel / Karen / Moira; Jepang: Kyoko / O-Ren; Tionghoa: Mei-Jia / Tian-Tian; dll. Suara premium (Yuna Premium, dll.) berkualitas lebih tinggi tetapi membutuhkan jaringan untuk potongan awal.

---

> 🆕 **Latest features and install guide are in terjemahan ini.** This translation covers the core docs; the visual install walkthrough, free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Pemasangan

### Homebrew (disarankan)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Unduhan langsung

[Rilis terbaru](https://talkmode.baryon.ai/download/TalkMode-0.4.38.zip) → ekstrak → seret ke `Applications` → pada peluncuran pertama macOS mungkin berkata "dari pengembang tak dikenal", klik kanan → Open sekali.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.38.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Pembaruan otomatis

Sparkle 2 sudah terpasang di dalamnya. Setelah dipasang (dengan cara mana pun), TalkMode memeriksa pembaruan di latar belakang — buka `TalkMode → Check for Updates…` atau `Pengaturan → Pembaruan` untuk mengaturnya.

### Persyaratan

- macOS **Sonoma (14.0)** atau lebih baru
- Apple silicon (M1 / M2 / M3 / M4)
- Sebuah penyedia LLM — minimal Claude CLI, Codex CLI, atau kunci OpenAI

---

## Izin

Izin diminta **hanya saat pertama kali Anda menggunakan fitur tersebut**:

| Fitur | Izin |
|---|---|
| Pendengaran selalu aktif | Mikrofon, Pengenalan Ucapan |
| Pelacakan tatapan (opsional) | Kamera |
| Tombol Option kanan untuk membisukan TTS | Pemantauan Masukan |
| Keterampilan kalender | Kalender (Akses Penuh) |
| Penyusun email | Apple Events |
| Keterampilan `messages.list_recent` | Akses Disk Penuh (berikan secara manual di Pengaturan Sistem) |

Tidak ada yang diunggah — STT berjalan on-device (atau di server STT Apple tergantung lokal Anda), avatar berupa PNG lokal, dan audio notula rapat tetap di `~/.talk_mode_mac/recordings/`.

---

## Keamanan & Privasi

Apa yang TalkMode simpan di Mac Anda, apa yang keluar dan ke mana, apa yang disimpan di disk, serta bagaimana kunci API dan izin ditangani — bersama dengan tinjauan keamanan tingkat kode beserta temuannya (tidak ada kerentanan yang dapat dieksploitasi dari jarak jauh; keterbatasan saat ini diungkapkan secara transparan) — terdokumentasi dalam **[SECURITY.md](../SECURITY.md)**.

---

## Dibangun dengan

TalkMode adalah aplikasi macOS berbasis SwiftPM. Dua paket Swift pihak ketiga, sisanya adalah framework Apple.

### Paket Swift

| Paket | Versi | Fungsinya di sini | Mengapa |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Pembaruan otomatis dalam aplikasi via appcast bertanda tangan | Standar platform Apple; digunakan oleh 1Password, Tower, OBS. Pembaruan bertanda tangan EdDSA, unduhan latar belakang, item menu "Check for Updates…". |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Diagnostik anonim yang dapat diikutsertakan (log gaya OpenTelemetry) | Membiarkan kami melihat transisi fase *mana* yang macet di lapangan tanpa pernah melihat teks pengguna — semua bidang teks bebas direduksi menjadi nilai panjang sebelum dikirim. |

### Framework Apple

| Framework | Digunakan untuk |
|---|---|
| **AVFoundation** | Masukan tap-tunggal `AVAudioEngine`, TTS `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), kamera `AVCaptureSession` |
| **Speech** | STT streaming `SpeechAnalyzer` (macOS 26) atau `SFSpeechRecognizer` dengan `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` untuk pose kepala → estimasi tatapan (dibatasi ~10 fps) |
| **Accelerate (vDSP)** | FFT 1024-titik + jendela Hann + embedding spektral log-magnitude ternormalisasi L2 untuk diarisasi pembicara on-device |
| **EventKit** | Keterampilan membaca / membuat / memperbarui / menghapus kalender (cakupan akses penuh) |
| **ImagePlayground** | Pembuatan avatar macOS 15.1+ (jika tidak, kembali ke DiceBear PNG via URLSession) |
| **CoreImage / CoreVideo** | Konversi bingkai kamera untuk masukan Vision |
| **AppKit + SwiftUI** | Jendela pengaturan, tata letak multi-tab, tampilan log dalam aplikasi |
| **Combine** | Propagasi keadaan `@Published` dari `ConversationEngine` ke seluruh UI |
| **OSLog** | Diagnostik unified-log (`subsystem=app.talkmode`) |
| **SQLite3** | Penyimpanan alias lokal + memori keterampilan |
| **UniformTypeIdentifiers** | Pemilih berkas avatar |

### Aset pihak ketiga (non-kode)

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 persona terkurasi per mode (이수민·정아람·박도윤·강예린). Pengguna dapat menggantinya dengan `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 gaya avatar diambil sebagai PNG, di-cache secara lokal.

---

## Latar belakang teknis

Beberapa pilihan desain yang tidak terlihat jelas dari tangkapan layar:

### Endpointing multimodal — mengapa giliran Anda berakhir cepat tetapi tidak terlalu cepat

Asisten suara CJK standar entah memotong Anda pada "ehm…" pertama atau menunggu 3 detik setelah Anda benar-benar selesai. `AdaptiveTurnDetector` milik TalkMode membaca empat sinyal sekaligus:

1. **Aktivitas suara** (EnergyVAD pada mikrofon) — sampel keheningan mengakumulasi anggaran
2. **Transkrip streaming** (SpeechAnalyzer / SFSpeechRecognizer) — sufiks penghubung Korea (`-고`, `-는데`) menambah 1,2 d; sufiks penutup (`-습니다`, `-요`) mengurangi 400 md; penanda keraguan (`음…`, `어…`) menambah 1,5 d
3. **Laju bicara** (karakter / detik) — penutur cepat mendapat anggaran jeda lebih kecil
4. **Keadaan tatapan** (yaw / pitch kepala via Vision) — menatap layar mengalikan jeda dengan 0,3-0,65 (menunggu), mengalihkan pandangan setelah kalimat lengkap mengalikan dengan 1,4 *dan* mempersenjatai pemicu cepat seketika (Anda sudah selesai)

Keempatnya disalurkan ke satu fungsi `predictedSilenceMs()`, dibatasi pada nilai dasar per bahasa (CJK 900-7000 md, Inggris 300-3000 md). Tidak ada pengatur waktu paralel, tidak ada race condition.

### Audio selalu aktif adalah penopang utama

`AudioInputStream` memulai `AVAudioEngine` **sekali per sesi dan tidak pernah menghentikannya** sampai sesi berakhir. Kode terdahulu menghentikan/memulai ulang pada setiap batas fase; pola itu mengakumulasi bug pada macOS 26 (`couldn't get default input device, ID = 0`, abort `format.sampleRate == inputHWFormat.sampleRate`). Kini satu tap menyiarkan buffer ke N konsumen (VAD, STT, detektor barge-in, perekam rapat, pengukur tingkat) via `AsyncStream`.

### Diarisasi pembicara on-device

Mode Notula Rapat menggunakan Apple Accelerate vDSP untuk menghitung **embedding spektral log-magnitude ternormalisasi L2 berdimensi 24** (FFT 1024, jendela Hann, hop 256) per ucapan. Kemiripan kosinus > 0,82 = pembicara yang sama seperti sebelumnya, jika tidak akan diberi ID baru. Tanpa unduhan model, tanpa panggilan API. Pembicara bertahan lintas rapat — beri label ulang "Speaker 1" → "지원" sekali, label itu menempel.

### LLM bersifat BYOK

`AssistantClient` adalah satu protokol dengan delapan implementasi. Penyedia CLI (`CLIAssistantClient` untuk `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) meluncurkan subproses di `~/.talk_mode_mac/work/` dengan `currentDirectoryURL` yang ter-sandbox, mengalirkan stdout kalimat demi kalimat ke `TTSQueue`, dan tidak pernah melihat kunci API dari TalkMode itu sendiri. Anda membawa langganan apa pun yang sudah Anda bayar.

### Diagnostik dengan privasi sebagai bawaan

Telemetri PostHog yang dapat diikutsertakan hanya meneruskan **peristiwa terkategori**, bukan teks yang mendasarinya:

- `turn / llm / tts / minutes / alias` → direduksi menjadi `[category] len=N` sebelum dikirim
- `skill` → menyimpan `skill_id`, membuang `args`
- `fsm / endpointing / session / error / update` → hanya metadata, tanpa transkrip

Verifikasi di `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (terlihat dalam strings biner jika Anda tidak memercayai saya).

### Markdown dihapus untuk TTS, dirender untuk obrolan

LLM gemar `**tebal**` dan `### judul`. AVSpeechSynthesizer membacanya sebagai "bintang bintang tebal bintang bintang". `MarkdownStripper.strip(_:)` membersihkan teks tepat sebelum masuk `TTSQueue` (gelembung obrolan mempertahankan aslinya via `AttributedString(markdown:)`).

### Pemisahan SwiftPM modular

Dua target yang dapat digunakan kembali hidup berdampingan dengan aplikasi utama:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — fungsi `timeout(for:localeID:)` murni-Foundation dengan 14 uji unit. Pengali `dtk/karakter × 4` per bahasa dengan nilai dasar; tidak dapat diturunkan diam-diam oleh commit yang tidak terkait.
- **`Endpointing`** (`Sources/Endpointing/`) — memiliki `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Tanpa ketergantungan AVFoundation / Vision. 7 uji unit yang mencakup serah-terima alih-pandangan, penolakan mikrofon-aktif, pembersihan latch.

`swift test --filter EndpointingTests` dan `swift test --filter SpeechWatchdogTests` masing-masing berjalan terhadap modul mungil — iterasi cepat.

### Mesin keadaan

Setiap transisi fase (`idle → listening → thinking → speaking → listening …`) melewati satu `PhaseStateMachine.transition(to:reason:)`. Transisi ilegal ditolak dengan alasan tercatat. Muncul di linimasa tab Diagnostik sehingga saat sesuatu macet, Anda dapat melihat *tepi mana* yang menolak memicu.

---

## Komunitas

- **Discussions** — pertanyaan, ide, permintaan fitur → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — laporan bug → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## Lisensi

Aplikasi yang sudah dikompilasi bebas digunakan, pribadi maupun komersial — ZIP rilis berisi satu bundel `.app` bertanda tangan.

Kode sumber dalam repositori ini dilisensikan di bawah **GNU Affero General Public License v3.0** — lihat [LICENSE](../LICENSE). Anda boleh menggunakan, mempelajari, memodifikasi, dan mendistribusikan ulang, tetapi setiap versi yang dimodifikasi — termasuk yang ditawarkan sebagai layanan jaringan — harus tetap terbuka di bawah lisensi AGPL-3.0 yang sama. Baryon Labs memegang hak cipta; jika Anda membutuhkan ketentuan di luar AGPL-3.0 (mis. lisensi komersial), tanyakan via **Discussions**.

Dibuat di Seoul oleh [Baryon Labs](https://baryon.ai).

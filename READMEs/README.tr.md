<div align="center">

# TalkMode

**Mac mini'yi gerçek bir asistana dönüştürün — anında Korece sesli yanıt, cihaz üzerinde, sizin kurallarınızla.**
**맥 미니를 진짜 비서로. 음성 즉답, 모두 on-device, 내가 정한 규칙대로.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | <a href="README.ru.md">Русский</a> | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | Türkçe | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> TalkMode için herkese açık depo — kaynak kodu, **Releases**, **Issues** ve **Discussions**.
> Uygulamanın verilerinizi tam olarak nasıl işlediğini görmek için **[SECURITY.md](../SECURITY.md)** dosyasına bakın.

---

## TalkMode nedir

TalkMode, bir Mac mini'yi (veya herhangi bir Apple silicon Mac'i) bir sohbet botu gibi değil, bir iş arkadaşı gibi davranan **gerçek zamanlı bir Korece sesli asistana** dönüştürür.

- Korece için ayarlanmış uyarlanabilir bir bitiş algılayıcısıyla (bakış + ses + transkript) **saniyenin altında sıra değiştirme**
- **Kesmek için konuşun ya da bitirmek için başka yöne bakın** — yalnızca sessizlik zamanlayıcıları değil, çok modlu ipuçları
- **4 mod**: sohbet · toplantı tutanağı · beyin fırtınası (onaylama odaklı) · psikolojik danışmanlık (dinleme odaklı)
- Toplantı tutanakları için **cihaz üzerinde konuşmacı ayrımı** (Apple Accelerate vDSP)
- **Beceriler**: takvim okuma, e-posta taslağı hazırlama, SMS okuma, CPU/RAM sorgulama, hafızaya kaydetme, takma adları öğrenme
- **8 LLM sağlayıcısı**: Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode CLI'leri + OpenAI + Mock
- **20 arayüz dili**, 50+ STT yerel ayarı
- **Kişilikler**: dile özel Soul + Contract dosyaları, ayrıca NVIDIA'nın Nemotron-Personas-Korea kümesinden özenle seçilmiş bir set
- DiceBear (10 stil), ImagePlayground (macOS 15.1+) veya kendi görselinizle **özel avatarlar**
- **Varsayılan olarak gizlilik**: Mac'inizden (a) seçtiğiniz LLM sağlayıcısı ve (b) tüm serbest metni uzunluk değerlerine indirgenmiş anonimleştirilmiş tanılama bilgileri dışında hiçbir şey ayrılmaz

---

## Ekran görüntüleri

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Sohbet sekmesi — ana" /></a><br/>
      <sub><b>Sohbet sekmesi</b> — asistan avatarı, bakış için isteğe bağlı kamera önizlemesi, mikrofon seviyesi göstergesi ve canlı sohbet. Turuncu "최근" etiketi etkin ruh halini gösterir.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Sohbet sekmesi — sohbet devam ediyor" /></a><br/>
      <sub><b>Canlı sohbet</b> — baloncuklarda işlenmiş markdown, otomatik noktalanmış STT, bir beceri hazırlandığında görünen "출발 알림" rozeti.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Ayarlar — asistan kişiliği" /></a><br/>
      <sub><b>Ayarlar — Kişilik</b> — arayüz / STT dili, avatar stili ve cinsiyeti, ImagePlayground oluşturma ve her yanıtı çerçeveleyen canlı <code>soul.md</code> sözleşmesi.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Tanılama — zaman çizelgesi" /></a><br/>
      <sub><b>Tanılama</b> — aşama, yaw/pitch, bakış, STT/yüz/CPU okumaları ve her bitiş kararının kayan zaman çizelgesi. Birkaç yüzde CPU tasarrufu için zaman çizelgesini kapatın.</sub>
    </td>
  </tr>
</table>

---

## Desteklenen diller

TalkMode, **arayüz dilini** (menülerin, düğmelerin ve hata mesajlarının hangi dilde olduğu) **konuşma dilinden** (asistanın hangi dilde transkript yaptığı ve yanıt verdiği) ayırır. Bunlar bağımsız olarak ayarlanabilir — arayüzü Almanca okuyun, asistanla Korece konuşun.

### Arayüz dilleri (20)

**Settings → 언어 → UI 언어** bölümünden ayarlanır. Her dil tamamen çevrilmiştir — tüm menüler, düğmeler, ayarlar, beceri açıklamaları ve tanılama etiketleri.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Konuşma / sohbet dilleri

Mac'inizin Speech çerçevesinin desteklediği her şey — macOS Sonoma+ üzerinde genellikle **50-60 yerel ayar**. **Settings → 언어 → 음성 인식 언어** bölümünden ayarlanır; seçici, `SFSpeechRecognizer.supportedLocales()` tarafından döndürülen her yerel ayarı listeler ve dört CJK + İngilizce yerel ayarını en üste sabitler.

Standart bir macOS Sonoma+ kurulumunda her zaman mevcut olanlar (kısmi bir liste — Mac'inizde daha fazlası olabilir):

| Bölge | Yerel ayarlar |
|---|---|
| **Doğu Asya** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **İngilizce** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Batı Avrupa** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Orta / Doğu Avrupa** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Yunanca / İbranice** | Ελληνικά · עברית |
| **Orta Doğu ve Güney Asya** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Güneydoğu Asya** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Diğer** | Türkçe · Русский · Català · Қазақ |

> Tam küme, işletim sistemi sürümüne ve **System Settings → Keyboard → Dictation** altında indirdiğiniz dikte dillerine bağlıdır. TalkMode başlangıçta canlı listeyi okur — kesin envanter için Mac'inizde seçiciyi açın.

### TTS sesleri

Konuşma *çıkışı* `AVSpeechSynthesizer` kullanır — macOS Siri / dikte ile aynı motor. Sesler **System Settings → Accessibility → Spoken Content → System Voice → Manage Voices** altından indirilir. Korece: Yuna / Sora; İngilizce: Samantha / Alex / Daniel / Karen / Moira; Japonca: Kyoko / O-Ren; Çince: Mei-Jia / Tian-Tian; vb. Premium sesler (Yuna Premium vb.) daha yüksek kalitelidir ancak ilk parça için ağ gerektirir.

---

## Kurulum

### Homebrew (önerilen)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Doğrudan indirme

[Latest release](https://talkmode.baryon.ai/download/TalkMode-0.4.11.zip) → zip'i açın → `Applications` klasörüne sürükleyin → ilk açılışta macOS "from unknown developer" diyebilir, bir kez sağ tıklayın → Open.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.11.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Otomatik güncelleme

Sparkle 2 yerleşik olarak gelir. Kurulduktan sonra (her iki yöntemle de) TalkMode arka planda güncellemeleri kontrol eder — kontrol etmek için `TalkMode → Check for Updates…` veya `Settings → Update` bölümünü açın.

### Gereksinimler

- macOS **Sonoma (14.0)** veya üzeri
- Apple silicon (M1 / M2 / M3 / M4)
- Bir LLM sağlayıcısı — en azından Claude CLI, Codex CLI veya bir OpenAI anahtarı

---

## İzinler

İzinler **yalnızca özelliği ilk kez kullandığınızda** istenir:

| Özellik | İzin |
|---|---|
| Sürekli dinleme | Microphone, Speech Recognition |
| Bakış takibi (isteğe bağlı) | Camera |
| TTS'i susturmak için Right-Option | Input Monitoring |
| Takvim becerileri | Calendars (Full Access) |
| E-posta düzenleyici | Apple Events |
| `messages.list_recent` becerisi | Full Disk Access (System Settings'ten manuel olarak verilir) |

Hiçbir şey karşıya yüklenmez — STT cihaz üzerinde çalışır (veya yerel ayarınıza bağlı olarak Apple'ın STT sunucusunda), avatarlar yerel PNG'lerdir ve toplantı tutanağı sesi `~/.talk_mode_mac/recordings/` içinde kalır.

---

## Güvenlik ve Gizlilik

TalkMode'un Mac'inizde neleri tuttuğu, nelerin ayrıldığı ve nereye gittiği, diskte nelerin depolandığı ve API anahtarlarının ve izinlerin nasıl ele alındığı — kod düzeyinde bir güvenlik incelemesi ve bulgularıyla birlikte (uzaktan istismar edilebilir bir güvenlik açığı yok; mevcut sınırlamalar şeffaf bir şekilde açıklanmış) — **[SECURITY.md](../SECURITY.md)** dosyasında belgelenmiştir.

---

## Ne ile yapıldı

TalkMode, SwiftPM tabanlı bir macOS uygulamasıdır. İki üçüncü taraf Swift paketi, geri kalanı Apple çerçeveleridir.

### Swift paketleri

| Paket | Sürüm | Burada ne yapıyor | Neden |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | İmzalı appcast aracılığıyla uygulama içi otomatik güncelleme | Apple platformu standardı; 1Password, Tower, OBS tarafından kullanılır. EdDSA imzalı güncellemeler, arka planda indirme, "Check for Updates…" menü öğesi. |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | İsteğe bağlı anonim tanılama (OpenTelemetry tarzı günlükler) | Kullanıcı metnini hiç görmeden gerçek dünyada *hangi* aşama geçişlerinin takıldığını görmemizi sağlar — tüm serbest biçimli alanlar gönderilmeden önce uzunluk değerlerine indirgenir. |

### Apple çerçeveleri

| Çerçeve | Kullanım amacı |
|---|---|
| **AVFoundation** | `AVAudioEngine` tek dokunuşlu giriş, `AVSpeechSynthesizer` TTS (Yuna / Premium / Personal Voice), `AVCaptureSession` kamera |
| **Speech** | `addsPunctuation` ile `SpeechAnalyzer` (macOS 26) veya `SFSpeechRecognizer` akış STT'si |
| **Vision** | Baş duruşu → bakış tahmini için `VNDetectFaceLandmarksRequest` (~10 fps ile sınırlandırılmış) |
| **Accelerate (vDSP)** | Cihaz üzerinde konuşmacı ayrımı için 1024 noktalı FFT + Hann penceresi + L2 normalize edilmiş log-büyüklük spektral gömme |
| **EventKit** | Takvim okuma / oluşturma / güncelleme / silme becerileri (tam erişim kapsamı) |
| **ImagePlayground** | macOS 15.1+ avatar oluşturma (aksi takdirde URLSession üzerinden DiceBear PNG'sine geri döner) |
| **CoreImage / CoreVideo** | Vision girişi için kamera karesi dönüşümü |
| **AppKit + SwiftUI** | Ayarlar penceresi, çok sekmeli düzen, uygulama içi günlük görünümü |
| **Combine** | `ConversationEngine`'den tüm arayüze `@Published` durum yayılımı |
| **OSLog** | Birleşik günlük tanılaması (`subsystem=app.talkmode`) |
| **SQLite3** | Yerel takma ad deposu + beceri hafızası |
| **UniformTypeIdentifiers** | Avatar dosya seçici |

### Üçüncü taraf (kod dışı) varlıklar

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — mod başına özenle seçilmiş 4 kişilik (이수민·정아람·박도윤·강예린). Kullanıcılar `nemotron-extras.json` ile bunları geçersiz kılabilir.
- **[DiceBear](https://www.dicebear.com)** — PNG olarak alınan ve yerel olarak önbelleğe alınan 10 avatar stili.

---

## Teknik arka plan

Ekran görüntülerinden açıkça görülmeyen birkaç tasarım tercihi:

### Çok modlu bitiş algılama — sıranızın neden hızlı ama çok hızlı olmadan bittiği

Standart CJK sesli asistanları ya ilk "음…" sesinde sözünüzü keser ya da gerçekten bitirdikten 3 saniye sonra bekler. TalkMode'un `AdaptiveTurnDetector`'ı dört sinyali aynı anda okur:

1. **Ses etkinliği** (mikrofonda EnergyVAD) — sessizlik örnekleri bir bütçe biriktirir
2. **Akış transkripti** (SpeechAnalyzer / SFSpeechRecognizer) — Korece 연결 어미 (`-고`, `-는데`) 1,2 sn ekler; 종결 어미 (`-습니다`, `-요`) 400 ms çıkarır; tereddüt belirteçleri (`음…`, `어…`) 1,5 sn ekler
3. **Konuşma hızı** (karakter / saniye) — hızlı konuşanlar daha küçük bir duraklama bütçesi alır
4. **Bakış durumu** (Vision aracılığıyla baş yaw / pitch) — ekrana bakmak duraklamayı 0,3-0,65 ile çarpar (bekliyor), tam bir cümleden sonra başka yöne bakmak 1,4 ile çarpar *ve* anında hızlı tetiklemeyi etkinleştirir (bitirdiniz)

Dördü de tek bir `predictedSilenceMs()` fonksiyonuna beslenir ve dile özel tabana sabitlenir (CJK 900-7000 ms, İngilizce 300-3000 ms). Paralel zamanlayıcı yok, yarış koşulu yok.

### Sürekli açık ses kritik öneme sahiptir

`AudioInputStream`, `AVAudioEngine`'i **oturum başına bir kez başlatır ve oturum bitene kadar asla durdurmaz**. Önceki kod her aşama sınırında durdurup yeniden başlatıyordu; bu desen macOS 26 üzerinde hatalar biriktirdi (`couldn't get default input device, ID = 0`, `format.sampleRate == inputHWFormat.sampleRate` iptalleri). Şimdi tek bir dokunuş, arabellekleri `AsyncStream` aracılığıyla N tüketiciye (VAD, STT, kesme algılayıcısı, toplantı kaydedici, seviye ölçer) yayınlar.

### Cihaz üzerinde konuşmacı ayrımı

Toplantı Tutanağı modu, ifade başına **24 boyutlu L2 normalize edilmiş log-büyüklük spektral gömme** (FFT 1024, Hann penceresi, hop 256) hesaplamak için Apple Accelerate vDSP kullanır. Kosinüs benzerliği > 0,82 = öncekiyle aynı konuşmacı, aksi takdirde yeni bir kimlik atanır. Model indirme yok, API çağrısı yok. Konuşmacılar toplantılar arasında kalıcıdır — "Speaker 1" → "지원" olarak bir kez yeniden etiketleyin, kalıcı olur.

### LLM, BYOK'tur

`AssistantClient`, sekiz uygulamaya sahip tek bir protokoldür. CLI sağlayıcıları (`claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode` için `CLIAssistantClient`) sanal alanlanmış bir `currentDirectoryURL` ile `~/.talk_mode_mac/work/` içinde bir alt süreç başlatır, stdout'u cümle cümle `TTSQueue`'ya aktarır ve TalkMode'un kendisinden hiçbir zaman bir API anahtarı görmez. Zaten ödediğiniz herhangi bir aboneliği getirirsiniz.

### Varsayılan olarak gizlilik içeren tanılama

İsteğe bağlı PostHog telemetrisi yalnızca **kategorize edilmiş olayları** iletir, altta yatan metni değil:

- `turn / llm / tts / minutes / alias` → gönderilmeden önce `[category] len=N`'e indirgenir
- `skill` → `skill_id`'yi tutar, `args`'ı bırakır
- `fsm / endpointing / session / error / update` → yalnızca meta veri, transkript yok

`Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` içinde doğrulayın (bana güvenmiyorsanız ikilinin dizelerinde görünür).

### TTS için soyulan, sohbet için işlenen Markdown

LLM'ler `**bold**` ve `### headings`'i sever. AVSpeechSynthesizer bunları "yıldız işareti yıldız işareti bold yıldız işareti yıldız işareti" olarak okur. `MarkdownStripper.strip(_:)`, metni `TTSQueue`'ya girmeden hemen önce temizler (sohbet baloncuğu, `AttributedString(markdown:)` aracılığıyla orijinali korur).

### Modüler SwiftPM bölünmesi

Ana uygulamanın yanında iki yeniden kullanılabilir hedef bulunur:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — 14 birim testli, saf Foundation `timeout(for:localeID:)` fonksiyonu. Tabanlı, dile özel `sec/char × 4` çarpanı; ilgisiz bir commit tarafından sessizce geriletilemez.
- **`Endpointing`** (`Sources/Endpointing/`) — `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`'e sahiptir. AVFoundation / Vision bağımlılığı yok. Başka yöne bakma devri, mikrofon-aktif reddi, mandal temizleme kapsayan 7 birim test.

`swift test --filter EndpointingTests` ve `swift test --filter SpeechWatchdogTests`, her biri küçük bir modüle karşı çalışır — hızlı yineleme.

### Durum makinesi

Her aşama geçişi (`idle → listening → thinking → speaking → listening …`) tek bir `PhaseStateMachine.transition(to:reason:)` üzerinden geçer. Geçersiz geçişler, kaydedilmiş bir nedenle reddedilir. Tanılama sekmesinin zaman çizelgesinde görünür, böylece bir şey takıldığında *hangi* kenarın ateşlenmeyi reddettiğini görebilirsiniz.

---

## Topluluk

- **Discussions** — sorular, fikirler, özellik istekleri → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — hata raporları → https://github.com/baryonlabs/talkmode-app/issues
- **E-posta** — support@baryon.ai

## Lisans

Derlenmiş uygulama, kişisel veya ticari, ücretsiz olarak kullanılabilir — sürüm ZIP'leri tek bir imzalı `.app` paketi içerir.

Bu depodaki kaynak kodu **GNU Affero General Public License v3.0** altında lisanslanmıştır — bkz. [LICENSE](../LICENSE). Kullanabilir, inceleyebilir, değiştirebilir ve yeniden dağıtabilirsiniz, ancak değiştirilmiş herhangi bir sürüm — bir ağ hizmeti olarak sunulan dahil — aynı AGPL-3.0 lisansı altında açık kalmalıdır. Telif hakkı Baryon Labs'e aittir; AGPL-3.0 dışında koşullara ihtiyacınız varsa (örneğin ticari bir lisans), **Discussions** aracılığıyla sorun.

Seul'de [Baryon Labs](https://baryon.ai) tarafından yapılmıştır.

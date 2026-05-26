<div align="center">

# TalkMode

**Mac mini превращается в настоящего помощника — мгновенный голос на корейском, на устройстве, на ваших условиях.**
**Mac mini становится полноценным ассистентом. Мгновенные голосовые ответы, всё on-device, по вашим правилам.**

[![macOS Sonoma+](https://img.shields.io/badge/macOS-Sonoma%2B-blue)](https://www.apple.com/macos/)
[![Apple silicon](https://img.shields.io/badge/Apple%20silicon-arm64-success)](https://en.wikipedia.org/wiki/Apple_silicon)
[![Latest release](https://img.shields.io/github/v/release/baryonlabs/talkmode?display_name=tag)](https://talkmode.baryon.ai/)
[![Made by Baryon Labs](https://img.shields.io/badge/made%20by-Baryon%20Labs-7e3ad6)](https://baryon.ai)

<p align="center">
  <a href="../README.md">English</a> | <a href="README.ko.md">한국어</a> | <a href="README.ja.md">日本語</a> | <a href="README.zh-CN.md">简体中文</a> | <a href="README.zh-TW.md">繁體中文</a> | <a href="README.es.md">Español</a> | <a href="README.fr.md">Français</a> | <a href="README.de.md">Deutsch</a> | <a href="README.it.md">Italiano</a> | <a href="README.pt.md">Português</a> | Русский | <a href="README.ar.md">العربية</a> | <a href="README.hi.md">हिन्दी</a> | <a href="README.id.md">Bahasa Indonesia</a> | <a href="README.vi.md">Tiếng Việt</a> | <a href="README.th.md">ไทย</a> | <a href="README.tr.md">Türkçe</a> | <a href="README.nl.md">Nederlands</a> | <a href="README.pl.md">Polski</a> | <a href="README.sv.md">Svenska</a>
</p>

<p align="center">
  <a href="https://github.com/baryonlabs/talkmode-app"><img src="https://img.shields.io/github/stars/baryonlabs/talkmode?style=flat&logo=github&label=stars&color=4c71f2" alt="GitHub stars" /></a>
</p>

</div>

> Публичный репозиторий TalkMode — исходный код, **Releases**, **Issues** и **Discussions**.
> Точное описание того, как приложение обращается с вашими данными, смотрите в **[SECURITY.md](../SECURITY.md)**.

---

## Что такое TalkMode

TalkMode превращает Mac mini (или любой Mac на Apple silicon) в **голосового ассистента корейского языка реального времени**, который ведёт себя как коллега, а не как чат-бот.

- **Передача хода менее чем за секунду** благодаря адаптивному эндпойнтеру, настроенному под корейский язык (взгляд + голос + транскрипт)
- **Заговорите, чтобы прервать, или отведите взгляд, чтобы завершить** — мультимодальные сигналы, а не просто таймеры тишины
- **4 режима**: разговор · протокол встречи · мозговой штурм (с упором на поддержку) · психологическая консультация (с упором на слушание)
- **Диаризация дикторов на устройстве** для протоколов встреч (Apple Accelerate vDSP)
- **Навыки**: чтение календаря, черновики писем, чтение SMS, запрос загрузки CPU/RAM, сохранение памяти, изучение псевдонимов
- **8 LLM-провайдеров**: CLI-инструменты Claude / Codex / Gemini / Cursor Agent / Kimi / OpenCode + OpenAI + Mock
- **20 языков интерфейса**, более 50 локалей STT
- **Персоны**: файлы Soul + Contract для каждого языка, плюс подобранный набор из NVIDIA Nemotron-Personas-Korea
- **Собственные аватары** через DiceBear (10 стилей), ImagePlayground (macOS 15.1+) или ваше собственное изображение
- **Конфиденциальность по умолчанию**: ничто не покидает ваш Mac, кроме (a) выбранного вами LLM-провайдера и (b) анонимизированной диагностики, в которой весь свободный текст заменён на значения длины

---

## Скриншоты

<table>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-main.png"><img src="../docs/screenshots/conversation-main.png" alt="Вкладка разговора — главная" /></a><br/>
      <sub><b>Вкладка разговора</b> — аватар ассистента, опциональный предпросмотр камеры для отслеживания взгляда, наложение уровня микрофона и живой чат. Оранжевый чип «недавнее» показывает активное настроение.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/conversation-chat.png"><img src="../docs/screenshots/conversation-chat.png" alt="Вкладка разговора — диалог в процессе" /></a><br/>
      <sub><b>Живой разговор</b> — markdown отображается в пузырях, STT автоматически расставляет пунктуацию, бейдж «уведомление об отправлении» появляется, когда навык подготовлен.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <a href="../docs/screenshots/settings-persona.png"><img src="../docs/screenshots/settings-persona.png" alt="Настройки — личность ассистента" /></a><br/>
      <sub><b>Настройки — Персона</b> — язык интерфейса / STT, стиль и пол аватара, генерация через ImagePlayground и живой контракт <code>soul.md</code>, который задаёт рамки каждого ответа.</sub>
    </td>
    <td width="50%" align="center">
      <a href="../docs/screenshots/diagnostics-timeline.png"><img src="../docs/screenshots/diagnostics-timeline.png" alt="Диагностика — временная шкала" /></a><br/>
      <sub><b>Диагностика</b> — фаза, yaw/pitch, взгляд, показания STT/лица/CPU и непрерывная временная шкала каждого решения об эндпойнтинге. Отключите шкалу, чтобы сэкономить несколько процентов CPU.</sub>
    </td>
  </tr>
</table>

---

## Поддерживаемые языки

TalkMode разделяет **язык интерфейса** (на каком языке меню, кнопки и сообщения об ошибках) и **язык речи** (на каком языке ассистент распознаёт и отвечает). Их можно задать независимо — читать интерфейс на немецком, а говорить с ассистентом на корейском.

### Языки интерфейса (20)

Задаётся в **Настройки → Язык → Язык интерфейса**. Каждый язык переведён полностью — все меню, кнопки, настройки, описания навыков и метки диагностики.

한국어 · English · 日本語 · 简体中文 · 繁體中文 · Español · Français · Deutsch · Italiano · Português · Русский · العربية · हिन्दी · Bahasa Indonesia · Tiếng Việt · ภาษาไทย · Türkçe · Nederlands · Polski · Svenska

### Языки речи / разговора

Всё, что поддерживает фреймворк Speech вашего Mac — обычно **50–60 локалей** на macOS Sonoma+. Задаётся в **Настройки → Язык → Язык распознавания речи**; список содержит каждую локаль, возвращаемую `SFSpeechRecognizer.supportedLocales()`, причём четыре локали CJK и английская закреплены наверху.

Всегда доступны на стандартной установке macOS Sonoma+ (частичный список — на вашем Mac их может быть больше):

| Регион | Локали |
|---|---|
| **Восточная Азия** | 한국어 (ko-KR) · 日本語 (ja-JP) · 简体中文 (zh-CN) · 繁體中文 (zh-Hant) · 廣東話 (zh-HK) |
| **Английский** | English (en-US / en-GB / en-AU / en-CA / en-IN / en-IE / en-NZ / en-ZA / en-SG) |
| **Западная Европа** | Español (es-ES / es-MX / es-US / es-CL) · Français (fr-FR / fr-CA / fr-CH / fr-BE) · Deutsch (de-DE / de-AT / de-CH) · Italiano (it-IT / it-CH) · Português (pt-BR / pt-PT) · Nederlands (nl-NL / nl-BE) · Dansk · Suomi · Norsk · Svenska |
| **Центральная / Восточная Европа** | Polski · Čeština · Magyar · Română · Slovenčina · Hrvatski · Українська · Български |
| **Греческий / Иврит** | Ελληνικά · עברית |
| **Ближний Восток и Южная Азия** | العربية (ar-SA / ar-AE) · हिन्दी · فارسی |
| **Юго-Восточная Азия** | Bahasa Indonesia · Bahasa Melayu · Tiếng Việt · ภาษาไทย · Filipino |
| **Прочие** | Türkçe · Русский · Català · Қазақ |

> Точный набор зависит от версии ОС и языков диктовки, которые вы загрузили в **Системные настройки → Клавиатура → Диктовка**. TalkMode считывает актуальный список при запуске — откройте выбор на вашем Mac для достоверной картины.

### Голоса TTS

*Озвучивание* речи использует `AVSpeechSynthesizer` — тот же движок, что Siri / диктовка в macOS. Голоса загружаются в **Системные настройки → Универсальный доступ → Проговаривание содержимого → Системный голос → Управление голосами**. Корейский: Yuna / Sora; английский: Samantha / Alex / Daniel / Karen / Moira; японский: Kyoko / O-Ren; китайский: Mei-Jia / Tian-Tian; и т. д. Премиум-голоса (Yuna Premium и др.) выше по качеству, но требуют сети для первого фрагмента.

---

> 🆕 **Latest features and install guide are in этом переводе.** This translation covers the core docs; the visual install walkthrough (macOS 15+ Gatekeeper unblock), free lifetime license signup, Translate mode, Obsidian sync, local LLM (LM Studio / Ollama / MLX) are only on the English / Korean pages:
> · [English readme](https://talkmode.baryon.ai/readme?lang=en) · [한국어 readme](https://talkmode.baryon.ai/readme?lang=ko) · [Step-by-step install guide](https://talkmode.baryon.ai/install) · [Free lifetime license](https://talkmode.baryon.ai/signup)

## Установка

### Homebrew (рекомендуется)

```bash
brew tap baryonlabs/talkmode
brew install --cask talkmode
```

### Прямая загрузка

[Последний релиз](https://talkmode.baryon.ai/download/TalkMode-0.4.23.zip) → распакуйте → перетащите в `Applications` → при первом запуске macOS может сказать «от неизвестного разработчика», щёлкните правой кнопкой → Открыть один раз.

```bash
curl -L https://talkmode.baryon.ai/download/TalkMode-0.4.23.zip -o TalkMode.zip
unzip TalkMode.zip && mv TalkMode.app /Applications/ && open -a TalkMode
```

### Автообновление

Sparkle 2 встроен. После установки (любым способом) TalkMode проверяет обновления в фоне — управляйте через `TalkMode → Проверить обновления…` или `Настройки → Обновление`.

### Требования

- macOS **Sonoma (14.0)** или новее
- Apple silicon (M1 / M2 / M3 / M4)
- LLM-провайдер — как минимум Claude CLI, Codex CLI или ключ OpenAI

---

## Разрешения

Разрешения запрашиваются **только при первом использовании функции**:

| Функция | Разрешение |
|---|---|
| Постоянное прослушивание | Микрофон, Распознавание речи |
| Отслеживание взгляда (опционально) | Камера |
| Правый Option для отключения TTS | Мониторинг ввода |
| Навыки календаря | Календари (полный доступ) |
| Составление писем | Apple Events |
| Навык `messages.list_recent` | Полный доступ к диску (предоставьте вручную в Системных настройках) |

Ничего не выгружается — STT работает на устройстве (или на сервере STT Apple в зависимости от вашей локали), аватары — это локальные PNG, а аудио протоколов встреч остаётся в `~/.talk_mode_mac/recordings/`.

---

## Безопасность и конфиденциальность

Что TalkMode хранит на вашем Mac, что покидает его и куда, что сохраняется на диске и как обрабатываются ключи API и разрешения — вместе с проверкой безопасности на уровне кода и её результатами (нет удалённо эксплуатируемых уязвимостей; текущие ограничения раскрыты прозрачно) — описано в **[SECURITY.md](../SECURITY.md)**.

---

## Создано с помощью

TalkMode — это macOS-приложение на основе SwiftPM. Два сторонних Swift-пакета, остальное — фреймворки Apple.

### Swift-пакеты

| Пакет | Версия | Что делает здесь | Почему |
|---|---|---|---|
| [Sparkle](https://github.com/sparkle-project/Sparkle) | 2.6+ | Автообновление внутри приложения через подписанный appcast | Стандарт платформы Apple; используется в 1Password, Tower, OBS. Обновления с подписью EdDSA, фоновая загрузка, пункт меню «Проверить обновления…». |
| [PostHog iOS SDK](https://github.com/PostHog/posthog-ios) | 3.58+ | Анонимная диагностика по согласию (логи в стиле OpenTelemetry) | Позволяет видеть, *какие* переходы фаз тормозят в реальных условиях, никогда не видя текст пользователя — все свободные поля сводятся к значениям длины перед отправкой. |

### Фреймворки Apple

| Фреймворк | Используется для |
|---|---|
| **AVFoundation** | Однотапный ввод `AVAudioEngine`, TTS `AVSpeechSynthesizer` (Yuna / Premium / Personal Voice), камера `AVCaptureSession` |
| **Speech** | Потоковый STT через `SpeechAnalyzer` (macOS 26) или `SFSpeechRecognizer` с `addsPunctuation` |
| **Vision** | `VNDetectFaceLandmarksRequest` для позы головы → оценки взгляда (ограничено ~10 кадрами/с) |
| **Accelerate (vDSP)** | 1024-точечное FFT + окно Ханна + L2-нормализованное логарифмическое спектральное вложение для диаризации дикторов на устройстве |
| **EventKit** | Навыки чтения / создания / обновления / удаления календаря (область полного доступа) |
| **ImagePlayground** | Генерация аватаров на macOS 15.1+ (иначе откат на DiceBear PNG через URLSession) |
| **CoreImage / CoreVideo** | Преобразование кадров камеры для ввода в Vision |
| **AppKit + SwiftUI** | Окно настроек, многовкладочная компоновка, просмотр логов внутри приложения |
| **Combine** | Распространение состояния `@Published` от `ConversationEngine` ко всему UI |
| **OSLog** | Диагностика через unified log (`subsystem=app.talkmode`) |
| **SQLite3** | Локальное хранилище псевдонимов + память навыков |
| **UniformTypeIdentifiers** | Выбор файла аватара |

### Сторонние (не кодовые) ресурсы

- **[NVIDIA Nemotron-Personas-Korea](https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea)** (CC BY 4.0) — 4 подобранные персоны на режим (이수민·정아람·박도윤·강예린). Пользователи могут переопределить их с помощью `nemotron-extras.json`.
- **[DiceBear](https://www.dicebear.com)** — 10 стилей аватаров, загружаемых как PNG и кэшируемых локально.

---

## Техническая подоплёка

Несколько проектных решений, которые не очевидны из скриншотов:

### Мультимодальный эндпойнтинг — почему ваш ход завершается быстро, но не слишком быстро

Стандартные голосовые ассистенты для CJK либо обрывают вас на первом «эм…», либо ждут 3 секунды после того, как вы действительно закончили. `AdaptiveTurnDetector` в TalkMode считывает четыре сигнала одновременно:

1. **Голосовая активность** (EnergyVAD на микрофоне) — образцы тишины накапливают бюджет
2. **Потоковый транскрипт** (SpeechAnalyzer / SFSpeechRecognizer) — корейские соединительные окончания (`-고`, `-는데`) добавляют 1,2 с; завершающие окончания (`-습니다`, `-요`) вычитают 400 мс; маркеры заминки (`음…`, `어…`) добавляют 1,5 с
3. **Скорость речи** (символов / с) — у быстро говорящих меньший бюджет паузы
4. **Состояние взгляда** (yaw / pitch головы через Vision) — взгляд на экран умножает паузу на 0,3–0,65 (ожидание), отведённый взгляд после завершённого предложения умножает на 1,4 *и* активирует немедленное быстрое срабатывание (вы закончили)

Все четыре подаются в одну функцию `predictedSilenceMs()`, ограниченную поязыковым нижним порогом (CJK 900–7000 мс, английский 300–3000 мс). Никаких параллельных таймеров, никаких состояний гонки.

### Постоянно включённое аудио — несущая конструкция

`AudioInputStream` запускает `AVAudioEngine` **один раз за сессию и никогда не останавливает его** до конца сессии. Ранний код останавливал/перезапускал его на каждой границе фазы; такая схема накапливала ошибки на macOS 26 (`couldn't get default input device, ID = 0`, аборты `format.sampleRate == inputHWFormat.sampleRate`). Теперь один тап транслирует буферы N потребителям (VAD, STT, детектор перебивания, записывающий встречи, индикатор уровня) через `AsyncStream`.

### Диаризация дикторов на устройстве

Режим протокола встречи использует Apple Accelerate vDSP для вычисления **24-мерного L2-нормализованного логарифмического спектрального вложения** (FFT 1024, окно Ханна, шаг 256) на каждое высказывание. Косинусное сходство > 0,82 = тот же диктор, что и раньше, иначе назначается новый ID. Без загрузки модели, без вызова API. Дикторы сохраняются между встречами — переименуйте «Диктор 1» → «지원» один раз, и это закрепится.

### LLM работает по принципу BYOK

`AssistantClient` — это один протокол с восемью реализациями. CLI-провайдеры (`CLIAssistantClient` для `claude`, `codex`, `gemini`, `cursor-agent`, `kimi`, `opencode`) запускают подпроцесс в `~/.talk_mode_mac/work/` с изолированным `currentDirectoryURL`, потоково передают stdout предложение за предложением в `TTSQueue` и никогда не видят ключ API от самого TalkMode. Вы используете ту подписку, за которую уже платите.

### Диагностика с конфиденциальностью по умолчанию

Телеметрия PostHog по согласию пересылает только **категоризированные события**, а не исходный текст:

- `turn / llm / tts / minutes / alias` → сводятся к `[category] len=N` перед отправкой
- `skill` → сохраняет `skill_id`, отбрасывает `args`
- `fsm / endpointing / session / error / update` → только метаданные, без транскрипта

Проверьте в `Sources/TalkModeApp/Telemetry/PostHogTelemetry.swift` (видно в строках бинарника, если вы мне не доверяете).

### Markdown очищается для TTS, отображается для чата

LLM обожают `**жирный**` и `### заголовки`. AVSpeechSynthesizer читает их как «звёздочка звёздочка жирный звёздочка звёздочка». `MarkdownStripper.strip(_:)` очищает текст прямо перед попаданием в `TTSQueue` (пузырь чата сохраняет оригинал через `AttributedString(markdown:)`).

### Модульное разделение SwiftPM

Рядом с основным приложением живут две переиспользуемые цели:

- **`SpeechWatchdog`** (`Sources/SpeechWatchdog/`) — чисто-Foundation функция `timeout(for:localeID:)` с 14 модульными тестами. Поязыковой множитель `сек/символ × 4` с нижним порогом; не может быть тихо ухудшена несвязанным коммитом.
- **`Endpointing`** (`Sources/Endpointing/`) — владеет `AdaptiveTurnDetector`, `VoiceActivity`, `GazeState`. Без зависимостей от AVFoundation / Vision. 7 модульных тестов, покрывающих передачу хода при отведённом взгляде, отклонение при активном микрофоне, очистку защёлки.

`swift test --filter EndpointingTests` и `swift test --filter SpeechWatchdogTests` каждый запускается против крошечного модуля — быстрая итерация.

### Конечный автомат

Каждый переход фазы (`idle → listening → thinking → speaking → listening …`) проходит через один `PhaseStateMachine.transition(to:reason:)`. Недопустимые переходы отклоняются с залогированной причиной. Это отображается во временной шкале вкладки Диагностика, так что когда что-то застряло, вы видите, *какое* ребро отказалось сработать.

---

## Сообщество

- **Discussions** — вопросы, идеи, запросы функций → https://github.com/baryonlabs/talkmode-app/discussions
- **Issues** — отчёты об ошибках → https://github.com/baryonlabs/talkmode-app/issues
- **Email** — support@baryon.ai

## Лицензия

Скомпилированное приложение можно использовать бесплатно, лично или коммерчески — релизные ZIP содержат один подписанный бандл `.app`.

Исходный код в этом репозитории лицензирован по **GNU Affero General Public License v3.0** — см. [LICENSE](../LICENSE). Вы можете использовать, изучать, изменять и распространять его, но любая изменённая версия — включая ту, что предлагается как сетевой сервис — должна оставаться открытой под той же лицензией AGPL-3.0. Baryon Labs владеет авторскими правами; если вам нужны условия вне AGPL-3.0 (например, коммерческая лицензия), обратитесь через **Discussions**.

Сделано в Сеуле компанией [Baryon Labs](https://baryon.ai).

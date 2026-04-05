# Claude Code — пошаговый гайд

Пошаговый гайд по продуктивной работе с Claude Code. Для macOS, [маппинг на Windows](#маппинг-на-windows) включён.

[English version](README.md)

---

## Шаг 1. Установить Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Запустить:

```bash
claude
```

Первое, что стоит попробовать:

```
/powerup
```

Интерактивный туториал с 10 уровнями. Лучший способ изучить возможности.

## Шаг 2. Рабочее место

Эргономика важна. Если сидишь креветкой часами, внимание рассеивается и тело начинает отторгать работу.

- Эргономичное или коленное кресло
- Подставка под ноутбук
- Монитор на уровне глаз
- Стоячий стол (опционально, но рекомендую)

## Шаг 3. Что такое терминал?

Терминал — это текстовый интерфейс к вашему компьютеру. Те же файлы и папки что в Finder (или Проводнике на Windows), только управляете текстом. Все AI-агенты (Claude Code, Codex, Gemini CLI) работают именно здесь.

**macOS:** Terminal.app встроен. Можно начать с него — все команды те же.

**Windows:** Windows Terminal встроен, вместо bash — PowerShell. Часть команд отличается (`dir` вместо `ls`, `start .` вместо `open .`), но Claude Code работает одинаково.

## Шаг 4. Приложение-терминал — Warp

[Warp](https://app.warp.dev/referral/8J544N) — более удобный терминал для macOS (как Chrome вместо Safari). Автодополнение, блоки, темы. Не обязателен, но приятнее.

**Аналог на Windows:** [Wave Terminal](https://www.waveterm.dev/) — open-source, AI, бесплатный.

**Настроить тему:** я использую **Monokai Pro**. Установить:

```bash
cp warp-themes/monokai_pro.yaml ~/.warp/themes/
```

Потом: Settings → Appearance → Theme → Monokai Pro.

**Именовать вкладки** по проектам (Werma, HoneyJourney, AR и т.д.) — сразу видно где что.

**Отключить встроенный AI:** Settings → AI → выключить, чтобы не мешался Claude Code.

**Горячие клавиши:**

| Действие | Сочетание |
|----------|-----------|
| Вкладка по номеру | `Cmd+1`, `Cmd+2`, `Cmd+3`... |
| Новое окно | `Cmd+N` |
| Новая вкладка | `Cmd+T` |
| Закрыть вкладку | `Cmd+W` |
| Переключение вкладок | `Ctrl+Tab` / `Ctrl+Shift+Tab` |
| Разделить вертикально | `Cmd+D` |
| Разделить горизонтально | `Cmd+Shift+D` |
| История команд | `↑` / `↓` |
| Прервать команду | `Ctrl+C` |

**Лайфхак:** `Cmd+T`, `Cmd+W`, `Ctrl+Tab` работают так же в браузере — учишь один раз, используешь везде.

## Шаг 5. Базовые команды терминала

Терминал — это те же папки, что в Finder, только через текст. Ничего сложного.

### Навигация

```bash
pwd                    # где я? (начинаем с домашней директории ~)
ls                     # что в этой папке?
cd projects            # войти в папку projects
cd ..                  # вернуться на уровень выше
cd ~                   # вернуться в домашнюю директорию
cd ~/projects/my-app   # перейти по полному пути
open .                 # открыть текущую папку в Finder (точка = "здесь")
```

### Создание

```bash
mkdir my-project               # создать папку
mkdir -p projects/my-app       # создать вложенные папки
```

### Запуск Claude Code

```bash
cd ~/projects/my-app   # переходишь в папку проекта
claude                 # запускаешь Claude Code — он видит весь проект
```

## Шаг 6. Голосовой ввод — Whisper Flow

[Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1) — голосовой ввод для macOS. ~4x быстрее набора на клавиатуре (45 слов/мин клавиатура vs 220 слов/мин голос).

Диктуешь промпты, команды, код. Работает в любом приложении, включая терминал.

## Шаг 7. Команды Claude Code

| Команда | Что делает |
|---------|-----------|
| `/powerup` | Интерактивное обучение (10 уровней, геймификация) |
| `/help` | Все доступные команды |
| `/resume` | Вернуться в предыдущий диалог (контекст сохраняется!) |
| `/clear` | Очистить контекст |
| `/compact` | Сжать контекст (когда диалог длинный) |
| `/model` | Выбор модели (Opus, Sonnet, Haiku) |
| `/plugins` | Установка плагинов (Slack, Linear, Gmail и др.) |
| `/loop` | Запуск команды на повторе с интервалом |
| `Escape` | Отмотать назад (rewind) — отменить последнее действие |
| `Escape Escape` | Отмотать ещё дальше |
| `Shift+Tab` | Переключить Plan Mode |
| `/exit` | Выход |

Совет: иногда перезапускай Claude Code, чтобы подтянулась новая версия.

## Шаг 8. Режимы доступа (permissions)

| Режим | Поведение |
|-------|-----------|
| Default | Спрашивает перед каждым действием |
| Accept edits | Автоматически принимает изменения файлов |
| Plan mode | Только планирует, не выполняет |
| Bypass permissions | Полный автомат (только если понимаешь риски) |

Настроить можно прямо через диалог с Claude Code:

> "Настрой permissions: разреши читать/писать файлы и git-команды, но спрашивай перед bash"

Он сам обновит `.claude/settings.local.json`.

## Шаг 9. Plan Mode

Самая мощная фича. `Shift+Tab` для переключения.

1. Описываешь задачу
2. Claude Code создаёт план (код пока не пишет)
3. Ты ревьюишь и корректируешь план
4. Переключаешь обратно — Claude Code выполняет

По сути это code review до того, как код написан.

## Шаг 10. Скиллы

Скиллы — расширения, которые учат Claude Code новым workflow.

- Установи набор от [Boris Cherny](https://howborisusesclaudecode.com/) (создатель Claude Code)
- Создавай свои под свои задачи
- В `/powerup` есть раздел про скиллы

## Шаг 11. Claude Code в IDE

Claude Code работает не только в терминале:

| Среда | Ссылка |
|-------|--------|
| Warp (терминал) | [warp.dev](https://app.warp.dev/referral/8J544N) |
| [Cursor](https://www.cursor.com/) (IDE) | Встроенный терминал |
| [Zed](https://zed.dev/) (редактор) | Встроенный терминал |

## Бонус

- **`Alt+Space`** — вызов ChatGPT (отдельно от терминала), удобно для быстрых вопросов
- **[Qwen Code](https://github.com/QwenLM/qwen-code)** — бесплатный, интегрируется с Zed
- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** — бесплатный, AI-агент Google в терминале

## Маппинг на Windows

Гайд написан для macOS. Вот как всё работает на Windows.

### Инструменты

| macOS | Windows | Заметки |
|-------|---------|---------|
| Warp | [Wave Terminal](https://www.waveterm.dev/) | Лучший аналог: open-source, AI, бесплатный. Или встроенный [Windows Terminal](https://aka.ms/terminal) |
| Whisper Flow | Нет прямого аналога | Попробуйте AquaVoice или Weesper Neon Flow |
| Cursor | [Cursor](https://www.cursor.com/) | Полная поддержка |
| Zed | [Zed](https://zed.dev/) | Полная поддержка с октября 2025 |
| Claude Code | Claude Code | `npm install -g @anthropic-ai/claude-code` или PowerShell: `irm https://claude.ai/install.ps1 \| iex` |
| Qwen Code | [Qwen Code](https://github.com/QwenLM/qwen-code) | Полная поддержка, Node.js 20+ |
| Gemini CLI | [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Полная поддержка |
| `open .` | `start .` или `explorer .` | Открыть папку в Проводнике |

### Горячие клавиши

| Действие | macOS | Windows |
|----------|-------|---------|
| Новая вкладка | `Cmd+T` | `Ctrl+Shift+T` (Windows Terminal) |
| Закрыть вкладку | `Cmd+W` | `Ctrl+W` |
| Переключение вкладок | `Ctrl+Tab` | `Ctrl+Tab` |
| Вкладка по номеру | `Cmd+1/2/3` | `Ctrl+1/2/3` (в редакторах) |
| Новое окно | `Cmd+N` | `Ctrl+N` |
| Разделить панель | `Cmd+D` | `Alt+Shift+D` (Windows Terminal) |
| Прервать | `Ctrl+C` | `Ctrl+C` |
| Plan Mode | `Shift+Tab` | `Shift+Tab` |
| Rewind | `Escape` | `Escape` |
| ChatGPT | `Alt+Space` | `Alt+Space` |

## Все ссылки

- [Claude Code документация](https://docs.anthropic.com/en/docs/claude-code/overview)
- [How Boris Uses Claude Code](https://howborisusesclaudecode.com/)
- [Warp Terminal](https://app.warp.dev/referral/8J544N)
- [Wave Terminal](https://www.waveterm.dev/) (аналог Warp на Windows)
- [Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1)
- [Cursor](https://www.cursor.com/)
- [Zed](https://zed.dev/)
- [Qwen Code](https://github.com/QwenLM/qwen-code)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)

# Claude Code — пошаговый гайд

Пошаговый гайд по продуктивной работе с Claude Code. Для macOS.

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

## Шаг 3. Терминал — Warp

[Warp](https://app.warp.dev/referral/8J544N) — современный терминал для macOS.

**Настроить тему:** я использую **Monokai Pro**. Установить:

```bash
cp warp-themes/monokai_pro.yaml ~/.warp/themes/
```

Потом: Settings → Appearance → Theme → Monokai Pro.

**Горячие клавиши:**

| Действие | Сочетание |
|----------|-----------|
| Новая вкладка | `Cmd+T` |
| Переключение вкладок | `Cmd+Shift+[` / `Cmd+Shift+]` |
| Новое окно | `Cmd+N` |
| Разделить вертикально | `Cmd+D` |
| Разделить горизонтально | `Cmd+Shift+D` |

## Шаг 4. Базовые команды терминала

```bash
cd ~/projects          # перейти в папку проектов
mkdir my-project       # создать проект
cd my-project          # войти в него
open .                 # открыть в Finder
claude                 # запустить Claude Code
```

## Шаг 5. Голосовой ввод — Whisper Flow

[Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1) — голосовой ввод для macOS. ~4x быстрее набора на клавиатуре (45 слов/мин клавиатура vs 220 слов/мин голос).

Диктуешь промпты, команды, код. Работает в любом приложении, включая терминал.

## Шаг 6. Команды Claude Code

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
| `Escape` или `/exit` | Выход |
| `Shift+Tab` | Переключить Plan Mode |

Совет: иногда перезапускай Claude Code, чтобы подтянулась новая версия.

## Шаг 7. Режимы доступа (permissions)

| Режим | Поведение |
|-------|-----------|
| Default | Спрашивает перед каждым действием |
| Accept edits | Автоматически принимает изменения файлов |
| Plan mode | Только планирует, не выполняет |
| Bypass permissions | Полный автомат (только если понимаешь риски) |

Настроить можно прямо через диалог с Claude Code:

> "Настрой permissions: разреши читать/писать файлы и git-команды, но спрашивай перед bash"

Он сам обновит `.claude/settings.local.json`.

## Шаг 8. Plan Mode

Самая мощная фича. `Shift+Tab` для переключения.

1. Описываешь задачу
2. Claude Code создаёт план (код пока не пишет)
3. Ты ревьюишь и корректируешь план
4. Переключаешь обратно — Claude Code выполняет

По сути это code review до того, как код написан.

## Шаг 9. Скиллы

Скиллы — расширения, которые учат Claude Code новым workflow.

- Установи набор от [Boris Cherny](https://howborisusesclaudecode.com/) (создатель Claude Code)
- Создавай свои под свои задачи
- В `/powerup` есть раздел про скиллы

## Шаг 10. Claude Code в IDE

Claude Code работает не только в терминале:

| Среда | Ссылка |
|-------|--------|
| Warp (терминал) | [warp.dev](https://app.warp.dev/referral/8J544N) |
| Cursor (IDE) | [cursor.com](https://www.cursor.com/) |
| Zed (редактор) | [zed.dev](https://zed.dev/) |

## Бонус: бесплатные альтернативы

| Инструмент | Заметки |
|-----------|---------|
| [Qwen Code](https://github.com/QwenLM/qwen-code) | Бесплатный, интегрируется с Zed |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Бесплатный, AI-агент Google в терминале |

## Все ссылки

- [Claude Code документация](https://docs.anthropic.com/en/docs/claude-code/overview)
- [How Boris Uses Claude Code](https://howborisusesclaudecode.com/)
- [Warp Terminal](https://app.warp.dev/referral/8J544N)
- [Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1)
- [Cursor](https://www.cursor.com/)
- [Zed](https://zed.dev/)
- [Qwen Code](https://github.com/QwenLM/qwen-code)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)

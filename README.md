# Claude Code Guide

Step-by-step guide to productive work with Claude Code. macOS focused.

[Русская версия](guide-ru.md)

---

## Step 1. Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Run it:

```bash
claude
```

First thing to try:

```
/powerup
```

Interactive tutorial with 10 power-ups. Best way to learn.

## Step 2. Set up your workspace

Ergonomics matter. If you sit hunched over for hours, your attention scatters and your body starts rejecting work.

- Ergonomic or kneeling chair
- Laptop stand
- Monitor at eye level
- Standing desk (optional but recommended)

## Step 3. Terminal — Warp

[Warp](https://app.warp.dev/referral/8J544N) — modern terminal for macOS.

**Set up a theme:** I use **Monokai Pro**. To install:

```bash
cp warp-themes/monokai_pro.yaml ~/.warp/themes/
```

Then: Settings → Appearance → Theme → Monokai Pro.

**Hotkeys:**

| Action | Shortcut |
|--------|----------|
| New tab | `Cmd+T` |
| Switch tabs | `Cmd+Shift+[` / `Cmd+Shift+]` |
| New window | `Cmd+N` |
| Split vertically | `Cmd+D` |
| Split horizontally | `Cmd+Shift+D` |

## Step 4. Terminal basics

```bash
cd ~/projects          # go to your projects folder
mkdir my-project       # create a new project
cd my-project          # enter it
open .                 # open in Finder
claude                 # start Claude Code here
```

## Step 5. Voice input — Whisper Flow

[Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1) — voice dictation for macOS. ~4x faster than typing (45 wpm keyboard vs 220 wpm voice).

Dictate prompts, commands, code. Works in any app including the terminal.

## Step 6. Claude Code commands

| Command | What it does |
|---------|-------------|
| `/powerup` | Interactive tutorial (10 power-ups, gamified) |
| `/help` | All available commands |
| `/resume` | Return to previous conversation (keep context!) |
| `/clear` | Clear context |
| `/compact` | Compress context (for long conversations) |
| `/model` | Switch model (Opus, Sonnet, Haiku) |
| `/plugins` | Install plugins (Slack, Linear, Gmail, etc.) |
| `/loop` | Run a command on repeat with interval |
| `Escape` or `/exit` | Exit |
| `Shift+Tab` | Toggle Plan Mode |

Tip: restart Claude Code occasionally to pick up version updates.

## Step 7. Permission modes

| Mode | Behavior |
|------|----------|
| Default | Asks before every action |
| Accept edits | Auto-accepts file changes |
| Plan mode | Plans only, doesn't execute |
| Bypass permissions | Full auto (use at your own risk) |

You can configure permissions by asking Claude Code directly:

> "Configure permissions: allow read/write files and git commands, but ask before running bash"

It will update `.claude/settings.local.json` for you.

## Step 8. Plan Mode

The most powerful feature. `Shift+Tab` to toggle.

1. Describe what you want
2. Claude Code creates a plan (doesn't write code yet)
3. You review and adjust the plan
4. Switch back to normal mode — Claude Code executes

Think of it as code review before the code exists.

## Step 9. Skills

Skills are extensions that teach Claude Code new workflows.

- Install a curated set from [Boris Cherny](https://howborisusesclaudecode.com/) (creator of Claude Code)
- Create your own for your specific workflows
- `/powerup` has a section on skills

## Step 10. Run Claude Code in IDEs

Claude Code works not only in the terminal:

| Environment | Link |
|-------------|------|
| Warp (terminal) | [warp.dev](https://app.warp.dev/referral/8J544N) |
| Cursor (IDE) | [cursor.com](https://www.cursor.com/) |
| Zed (editor) | [zed.dev](https://zed.dev/) |

## Bonus: free alternatives

| Tool | Notes |
|------|-------|
| [Qwen Code](https://github.com/QwenLM/qwen-code) | Free, integrates with Zed |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Free, Google's terminal AI agent |

## All links

- [Claude Code docs](https://docs.anthropic.com/en/docs/claude-code/overview)
- [How Boris Uses Claude Code](https://howborisusesclaudecode.com/)
- [Warp Terminal](https://app.warp.dev/referral/8J544N)
- [Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1)
- [Cursor](https://www.cursor.com/)
- [Zed](https://zed.dev/)
- [Qwen Code](https://github.com/QwenLM/qwen-code)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)

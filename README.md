# Claude Code Guide

Step-by-step guide to productive work with Claude Code. macOS focused, [Windows mapping](#windows-mapping) included.

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

## Step 3. What is a terminal?

A terminal is a text interface to your computer. Same files and folders as Finder (or File Explorer on Windows), but you control them with text commands. All AI agents (Claude Code, Codex, Gemini CLI) work here.

**macOS:** Terminal.app is built-in. You can start with it — all commands work the same.

**Windows:** Windows Terminal is built-in, uses PowerShell instead of bash. Some commands differ (`dir` instead of `ls`, `start .` instead of `open .`), but Claude Code works identically.

## Step 4. Terminal app — Warp

[Warp](https://app.warp.dev/referral/8J544N) — a more comfortable terminal app for macOS (like Chrome instead of Safari). Autocomplete, blocks, themes. Not required, but nicer.

**Windows alternative:** [Wave Terminal](https://www.waveterm.dev/) — open-source, AI integration, free.

**Set up a theme:** I use **Monokai Pro**. To install:

```bash
cp warp-themes/monokai_pro.yaml ~/.warp/themes/
```

Then: Settings → Appearance → Theme → Monokai Pro.

**Name your tabs** by project (e.g. Werma, HoneyJourney, AR) — instantly see where you are.

**Disable built-in AI:** Settings → AI → turn off, so it doesn't interfere with Claude Code.

**Hotkeys:**

| Action | Shortcut |
|--------|----------|
| Tab by number | `Cmd+1`, `Cmd+2`, `Cmd+3`... |
| New window | `Cmd+N` |
| New tab | `Cmd+T` |
| Close tab | `Cmd+W` |
| Switch tabs | `Ctrl+Tab` / `Ctrl+Shift+Tab` |
| Split vertically | `Cmd+D` |
| Split horizontally | `Cmd+Shift+D` |
| Command history | `↑` / `↓` |
| Interrupt | `Ctrl+C` |

**Tip:** `Cmd+T`, `Cmd+W`, `Ctrl+Tab` work the same in browsers — learn once, use everywhere.

## Step 5. Terminal basics

The terminal is just your file system in text form. Same folders as Finder, nothing complicated.

### Navigation

```bash
pwd                    # where am I? (starts in home directory ~)
ls                     # what's in this folder?
cd projects            # enter folder "projects"
cd ..                  # go up one level
cd ~                   # go back to home directory
cd ~/projects/my-app   # go to full path
open .                 # open current folder in Finder (. = "here")
```

### Create

```bash
mkdir my-project               # create folder
mkdir -p projects/my-app       # create nested folders
```

### Start Claude Code

```bash
cd ~/projects/my-app   # navigate to your project
claude                 # start Claude Code — it sees your whole project
```

## Step 6. Voice input — Whisper Flow

[Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1) — voice dictation for macOS. ~4x faster than typing (45 wpm keyboard vs 220 wpm voice).

Dictate prompts, commands, code. Works in any app including the terminal.

## Step 7. Claude Code commands

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
| `Escape` | Rewind — undo last action |
| `Escape Escape` | Rewind further |
| `Shift+Tab` | Toggle Plan Mode |
| `/exit` | Exit |

Tip: restart Claude Code occasionally to pick up version updates.

## Step 8. Permission modes

| Mode | Behavior |
|------|----------|
| Default | Asks before every action |
| Accept edits | Auto-accepts file changes |
| Plan mode | Plans only, doesn't execute |
| Bypass permissions | Full auto (use at your own risk) |

You can configure permissions by asking Claude Code directly:

> "Configure permissions: allow read/write files and git commands, but ask before running bash"

It will update `.claude/settings.local.json` for you.

## Step 9. Plan Mode

The most powerful feature. `Shift+Tab` to toggle.

1. Describe what you want
2. Claude Code creates a plan (doesn't write code yet)
3. You review and adjust the plan
4. Switch back to normal mode — Claude Code executes

Think of it as code review before the code exists.

## Step 10. Skills

Skills are extensions that teach Claude Code new workflows.

- Install a curated set from [Boris Cherny](https://howborisusesclaudecode.com/) (creator of Claude Code)
- Create your own for your specific workflows
- `/powerup` has a section on skills

## Step 11. Run Claude Code in IDEs

Claude Code works not only in the terminal:

| Environment | Link |
|-------------|------|
| Warp (terminal) | [warp.dev](https://app.warp.dev/referral/8J544N) |
| [Cursor](https://www.cursor.com/) (IDE) | Built-in terminal |
| [Zed](https://zed.dev/) (editor) | Built-in terminal |

## Bonus

- **`Alt+Space`** — invoke ChatGPT (separate from terminal), handy for quick questions
- **[Qwen Code](https://github.com/QwenLM/qwen-code)** — free, integrates with Zed
- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** — free, Google's terminal AI agent

## Windows mapping

This guide is macOS-focused. Here's how everything maps to Windows.

### Tools

| macOS | Windows | Notes |
|-------|---------|-------|
| Warp | [Wave Terminal](https://www.waveterm.dev/) | Best alternative: open-source, AI, free. Or use built-in [Windows Terminal](https://aka.ms/terminal) |
| Whisper Flow | No direct equivalent | Try AquaVoice or Weesper Neon Flow |
| Cursor | [Cursor](https://www.cursor.com/) | Fully supported |
| Zed | [Zed](https://zed.dev/) | Fully supported since Oct 2025 |
| Claude Code | Claude Code | `npm install -g @anthropic-ai/claude-code` or PowerShell: `irm https://claude.ai/install.ps1 \| iex` |
| Qwen Code | [Qwen Code](https://github.com/QwenLM/qwen-code) | Fully supported, Node.js 20+ |
| Gemini CLI | [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Fully supported |
| `open .` | `start .` or `explorer .` | Opens current folder in File Explorer |

### Keyboard shortcuts

| Action | macOS | Windows |
|--------|-------|---------|
| New tab | `Cmd+T` | `Ctrl+Shift+T` (Windows Terminal) |
| Close tab | `Cmd+W` | `Ctrl+W` |
| Switch tabs | `Ctrl+Tab` | `Ctrl+Tab` |
| Tab by number | `Cmd+1/2/3` | `Ctrl+1/2/3` (in editors) |
| New window | `Cmd+N` | `Ctrl+N` |
| Split pane | `Cmd+D` | `Alt+Shift+D` (Windows Terminal) |
| Interrupt | `Ctrl+C` | `Ctrl+C` |
| Plan Mode | `Shift+Tab` | `Shift+Tab` |
| Rewind | `Escape` | `Escape` |
| ChatGPT | `Alt+Space` | `Alt+Space` |

## All links

- [Claude Code docs](https://docs.anthropic.com/en/docs/claude-code/overview)
- [How Boris Uses Claude Code](https://howborisusesclaudecode.com/)
- [Warp Terminal](https://app.warp.dev/referral/8J544N)
- [Wave Terminal](https://www.waveterm.dev/) (Windows alternative to Warp)
- [Whisper Flow](https://wisprflow.ai/r?AKHWHISPR1)
- [Cursor](https://www.cursor.com/)
- [Zed](https://zed.dev/)
- [Qwen Code](https://github.com/QwenLM/qwen-code)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)

# cca (Claude Code AutoFlow)

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-AGPL--3.0-green.svg)
![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20macOS%20%7C%20WSL-lightgrey.svg)

**Claude Code AutoFlow (cca)** is a structured task automation workflow system designed for AI-assisted development. It enables Claude to plan and execute complex tasks autonomously with dual-design validation.

## 🔗 Dependency Chain

```
WezTerm  →  ccb (Claude Code Bridge)  →  cca (Claude Code AutoFlow)
```

- **WezTerm**: Terminal emulator with pane control support
- **ccb**: Bridge connecting terminal to AI context
- **cca**: High-level workflow engine for task automation

## ✨ Core Features

| Feature | Description |
| :--- | :--- |
| **Task Planning** | Dual-design (Claude + Codex) plan generation |
| **Auto Execution** | Autoloop daemon triggers `/tr` automatically after planning |
| **State Management** | `state.json` as Single Source of Truth |
| **Context Awareness** | Auto `/clear` when context usage exceeds threshold |

## 🚀 Installation

### 1. Install WezTerm
Download from: [https://wezfurlong.org/wezterm/](https://wezfurlong.org/wezterm/)

### 2. Install ccb (Claude Code Bridge)
```bash
git clone https://github.com/bfly123/claude_code_bridge.git
cd claude_code_bridge
./install.sh install
```

### 3. Install cca (AutoFlow)
```bash
git clone https://github.com/bfly123/claude_code_autoflow.git
cd claude_code_autoflow
./install.sh install
```

## 📖 Usage

### CLI Commands

| Command | Description |
| :--- | :--- |
| `cca add .` | Enable AutoFlow for current project |
| `cca add /path` | Enable AutoFlow for specific path |
| `cca delete .` | Remove AutoFlow from current project |
| `cca update` | Update cca and refresh global skills |
| `cca version` | Display version info |

### Slash Commands (In-Session)

| Command | Description |
| :--- | :--- |
| `/auto <requirement>` | Create task plan (invokes tp skill) |
| `/auto run` | Execute current step (invokes tr skill) |

Example:
```bash
/auto implement user login    # Creates plan, autoloop starts execution
```

> **Note**: After `/auto <requirement>` completes planning, autoloop automatically triggers execution. No manual `/auto run` needed.

## 📄 License

[AGPL-3.0](LICENSE)

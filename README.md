# 🚀 Claude Code + NVIDIA NIM ឥតគិតថ្លៃ (Windows + MacBook)

## 📌 គោលបំណង

Setup នេះអនុញ្ញាតឱ្យអ្នកប្រើ:

* Claude Code ក្នុង VS Code
* NVIDIA NIM Free Models
* Free Claude Code Gateway
* Agent Mode
* Coding Assistant ឥតគិតថ្លៃ

---

# 🪟 Windows 11 + WSL

## ១. ដំឡើង WSL

បើក PowerShell (Run as Administrator)

```powershell
wsl --install Ubuntu
```

បង្កើត Username និង Password។
បិទ terminal Search app បើក Ubuntu 

---

## ២. ដំឡើង VS Code

ដំឡើង:

* VS Code
* Claude Code Extension
* Remote - WSL Extension

---
## ៣. បើក Ubuntu (WSL)

```bash
sudo apt update
sudo apt install -y nodejs npm

sudo apt install git curl unzip -y
```

---

## ៤. ដំឡើង Claude Code

```powershell
npm install -g @anthropic-ai/claude-code
```

ពិនិត្យ:

```powershell
claude --version
```

---


## ៥. ដំឡើង UV

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Restart Terminal

---

## ៦. Download Free Claude Code

```bash
git clone https://github.com/Alishahryar1/free-claude-code.git

cd free-claude-code
```

---

## ៧. កំណត់ NVIDIA API Key

```bash
cp .env.example .env

nano .env
```

ដាក់:

```env
NVIDIA_NIM_API_KEY="API_KEY_របស់អ្នក"
```

Save:

```text
CTRL + X
Y
ENTER
```

---

## ៨. ដំឡើង Dependencies

```bash
source $HOME/.local/bin
uv sync
```

---

## ៩. ចាប់ផ្តើម Gateway

```bash
uv run python server.py
```

---

## ១០. បើក Admin UI

Browser:

```text
http://127.0.0.1:8082/admin
```

ជ្រើស Model:

```text
nvidia_nim/nvidia/nemotron-3-super-120b-a12b
```

ចុច Apply

---

## ១១. កំណត់ VS Code

Settings JSON:

```json
"claudeCode.environmentVariables": [
  {
    "name": "ANTHROPIC_BASE_URL",
    "value": "http://localhost:8082"
  },
  {
    "name": "ANTHROPIC_AUTH_TOKEN",
    "value": "freecc"
  },
  {
    "name": "CLAUDE_CODE_ENABLE_GATEWAY_MODEL_DISCOVERY",
    "value": "1"
  }
]
```

---

# 🍎 MacBook (Intel + Apple Silicon)

## ១. ដំឡើង Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

---

## ២. ដំឡើង Node.js

```bash
brew install node
```

ពិនិត្យ:

```bash
node -v
npm -v
```

---

## ៣. ដំឡើង Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

ពិនិត្យ:

```bash
claude --version
```

---

## ៤. ដំឡើង Git

```bash
brew install git
```

---

## ៥. ដំឡើង UV

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Restart Terminal

---

## ៦. Download Free Claude Code

```bash
git clone https://github.com/Alishahryar1/free-claude-code.git

cd free-claude-code
```

---

## ៧. កំណត់ NVIDIA API Key

```bash
cp .env.example .env

nano .env
```

ដាក់:

```env
NVIDIA_NIM_API_KEY="API_KEY_របស់អ្នក"
```

Save:

```text
CTRL + X
Y
ENTER
```

---

## ៨. ដំឡើង Dependencies

```bash
uv sync
```

---

## ៩. ចាប់ផ្តើម Gateway

```bash
uv run python server.py
```

---

## ១០. បើក Admin UI

Browser:

```text
http://127.0.0.1:8082/admin
```

ជ្រើស Model:

```text
nvidia_nim/nvidia/nemotron-3-super-120b-a12b
```

ចុច Apply

---

## ១១. កំណត់ VS Code

Settings JSON:

```json
"claudeCode.environmentVariables": [
  {
    "name": "ANTHROPIC_BASE_URL",
    "value": "http://localhost:8082"
  },
  {
    "name": "ANTHROPIC_AUTH_TOKEN",
    "value": "freecc"
  },
  {
    "name": "CLAUDE_CODE_ENABLE_GATEWAY_MODEL_DISCOVERY",
    "value": "1"
  }
]
```

---

# ⚡ បង្កើត Command ខ្លី

### Windows (WSL)

```bash
echo 'alias fcc="cd ~/free-claude-code && nohup uv run python server.py >/dev/null 2>&1 &"' >> ~/.bashrc

source ~/.bashrc
```

### MacBook

```bash
echo 'alias fcc="cd ~/free-claude-code && nohup uv run python server.py >/dev/null 2>&1 &"' >> ~/.zshrc

source ~/.zshrc
```

ប្រើ:

```bash
fcc
```

---

# 🔧 Commands មានប្រយោជន៍

ពិនិត្យ Gateway:

```bash
curl http://127.0.0.1:8082/health
```

លទ្ធផល:

```json
{"status":"healthy"}
```

បិទ Gateway:

```bash
pkill -f server.py
```

ពិនិត្យ Process:

```bash
pgrep -af server.py
```

---

# 🔄 បើ NVIDIA Limit អស់

បន្ទាប់ពី Reset ឬប្ដូរ Model រួច សរសេរ:

```text
Continue from where you stopped.

First inspect the project files and continue the unfinished work.
```

---

# 🎉 រួចរាល់

អ្នកមាន:

✅ Claude Code

✅ NVIDIA NIM Free

✅ Free Claude Code Gateway

✅ VS Code Agent Mode

✅ Coding Assistant ឥតគិតថ្លៃ

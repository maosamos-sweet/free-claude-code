# 🚀 របៀបដំឡើង Claude Code + NVIDIA NIM ឥតគិតថ្លៃ (Windows + WSL)

## 📌 គោលបំណង

Setup នេះអនុញ្ញាតឱ្យអ្នកប្រើ:

* Claude Code ក្នុង VS Code
* NVIDIA NIM Free Models
* Free Claude Code Gateway
* Agent Mode
* Coding Assistant ឥតគិតថ្លៃ

---

# ១. ដំឡើង WSL

បើក PowerShell (Run as Administrator)

```powershell
wsl --install
```

Restart កុំព្យូទ័រ។

បន្ទាប់មកបង្កើត:

```text
Username
Password
```

---

# ២. ដំឡើង VS Code

ដំឡើង:

* VS Code
* Claude Code Extension
* Remote - WSL Extension

---

# ៣. ដំឡើង Claude Code CLI

បើក PowerShell:

```powershell
npm install -g @anthropic-ai/claude-code
```

ពិនិត្យ:

```powershell
claude --version
```

---

# ៤. បើក Ubuntu (WSL)

Update ប្រព័ន្ធ:

```bash
sudo apt update && sudo apt upgrade -y
```

ដំឡើង Package ចាំបាច់:

```bash
sudo apt install git curl unzip -y
```

---

# ៥. ដំឡើង UV

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

បិទ Terminal ហើយបើកឡើងវិញ។

ពិនិត្យ:

```bash
uv --version
```

---

# ៦. Download Free Claude Code

```bash
git clone https://github.com/Alishahryar1/free-claude-code.git

cd free-claude-code
```

---

# ៧. បង្កើត NVIDIA API Key

ចូល:

https://build.nvidia.com/settings/api-keys

បង្កើត API Key ថ្មី។

Copy ទុក។

---

# ៨. កំណត់ API Key

បង្កើត File:

```bash
cp .env.example .env
```

កែសម្រួល:

```bash
nano .env
```

ស្វែងរក:

```env
NVIDIA_NIM_API_KEY=""
```

ប្ដូរទៅ:

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

# ៩. ដំឡើង Dependencies

```bash
uv sync
```

រង់ចាំឱ្យចប់។

---

# ១០. ចាប់ផ្តើម Gateway

```bash
uv run python server.py
```

បើជោគជ័យ អ្នកនឹងឃើញ:

```text
Admin UI: http://127.0.0.1:8082/admin
```

⚠️ កុំបិទ Terminal នេះ។

---

# ១១. កំណត់ Model

បើក Browser:

```text
http://127.0.0.1:8082/admin
```

ចូលផ្នែក:

```text
Providers
```

Refresh Models។

បន្ទាប់មកចូល:

```text
Model Config
```

ជ្រើស:

```text
nvidia_nim/nvidia/nemotron-3-super-120b-a12b
```

ចុច:

```text
Apply
```

---

# ១២. កំណត់ VS Code

បើក:

```text
Settings (JSON)
```

បន្ថែម:

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

Save និង Reload VS Code។

---

# ១៣. ពិនិត្យថាដំណើរការ

Run:

```bash
curl http://127.0.0.1:8082/health
```

លទ្ធផល:

```json
{"status":"healthy"}
```

បើក Claude Code។

អ្នកគួរតែឃើញ:

```text
nvidia_nim/nvidia/nemotron-3-super-120b-a12b
```

ក្នុង Model List។

---

# ⚡ ការប្រើប្រាស់ប្រចាំថ្ងៃ

បើក WSL:

```bash
cd ~/free-claude-code

uv run python server.py
```

បន្ទាប់មកបើក VS Code ហើយប្រើ Claude Code ធម្មតា។

---

# ⚡ បង្កើត Command ខ្លី

បន្ថែម Alias:

```bash
echo 'alias fcc="cd ~/free-claude-code && nohup uv run python server.py >/dev/null 2>&1 &"' >> ~/.bashrc

source ~/.bashrc
```

ចាប់ពីពេលនេះទៅ:

```bash
fcc
```

គឺចាប់ផ្តើម Gateway ភ្លាម។

---

# 🔧 Command មានប្រយោជន៍

ពិនិត្យ Gateway:

```bash
curl http://127.0.0.1:8082/health
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

Claude Code នឹងបន្តការងារពី Project បច្ចុប្បន្ន។

---

# 🎉 រួចរាល់

អ្នកមាន:

✅ Claude Code

✅ NVIDIA NIM Free

✅ Free Claude Code Gateway

✅ VS Code Agent Mode

✅ Coding Assistant ឥតគិតថ្លៃ

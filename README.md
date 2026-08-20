# 🧰 Prerequisites & Setup

Before getting started, make sure your development environment is ready. These are the basic tools and setup I use for my Python, AI, and Agentic AI projects.

> This setup is mainly focused on my Python, AI, and Agentic AI learning journey.

---

## 🐍 Python

Make sure Python 3.10 or above is installed.

Check your version:

```bash
python --version
```

- If it's below `3.10`, install a current Python from [python.org](https://python.org) or your OS package manager.
- Individual project folders pin an exact version via `.python-version` — **UV** (next step) reads that automatically, so you don't need to juggle versions by hand.

---

## 2. Install UV — the package & project manager used all course long

**Mac / Linux:**

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Windows:**  
Use **Git Bash** or **Windows Terminal** (never plain CMD/PowerShell — see Class 01) and follow the [UV install docs](https://docs.astral.sh/uv/getting-started/installation/).

### Why UV, not `pip + venv + conda`?

One fast tool replaces the juggling act. Every class folder with code ships its own:

- `pyproject.toml`
- `uv.lock`

These define the exact Python version and dependency list any machine can reproduce identically — the same role `package.json` plays in Node.

---

## 3. Install VS Code

This is an **Agentic AI** course, not classic Data Science — the workflow leans on:

- `.py` scripts
- A real terminal (you'll SSH into cloud machines later in the course)
- Proper debugging, not just notebooks

Get it from: [code.visualstudio.com](https://code.visualstudio.com)

---

## 4. Get at least one free LLM API key

Every class folder needs at least one provider key to run its live calls. Two are free:

| Provider     | Cost                     | Get a key                                      |
|--------------|--------------------------|------------------------------------------------|
| **Groq**     | Free, fast               | [console.groq.com/keys](https://console.groq.com/keys) |
| **OpenRouter** | Free tier (`model="openrouter/free"` auto-routes so it never goes stale) | [openrouter.ai/keys](https://openrouter.ai/keys) |
| **OpenAI**   | Paid                     | [platform.openai.com/api-keys](https://platform.openai.com/api-keys) |
| **Anthropic**| Paid                     | [console.anthropic.com](https://console.anthropic.com) |

> You only need **one** to get started — **Groq** is the fastest to sign up for.

---

## 5. The `.env` workflow — every project folder, same pattern

Every folder with code ships a `.env.example` template. **Never edit that file directly** — copy it:

```bash
cd "Weekend 01 - 27-28 Jun/01 - 27 Jun - Python Setup & API Basics"
uv sync
cp .env.example .env
# open .env and paste in at least one real key, e.g.:
#   GROQ_API_KEY=gsk_your_real_key_here
uv run main.py
```

- `.env` is git-ignored at the repo root — a real key will never get committed by accident.
- `.env.example` is the only one that ever ships with placeholder values.
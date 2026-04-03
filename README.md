# 🧑💻 MergeGuru – AI-Powered Code Companion

MergeGuru is an AI-powered assistant that helps developers understand, review, and optimize codebases using locally-hosted LLMs. All processing happens on your own infrastructure — no code is shared with third-party APIs.

## Features

- **Repository Analysis** — Scans entire repos, analyzes each module for structure, bugs, optimization opportunities, and generates documentation
- **Merge Request Reviews** — Reviews GitHub PRs for bugs, code smells, refactoring suggestions, and provides change summaries
- **Auto Documentation** — Generates consolidated, human-readable documentation for the entire codebase
- **Code Assistant** — Generates code snippets and answers coding questions (Python, Java, JavaScript)

## Architecture

- **Backend**: Flask (Python)
- **LLM Inference**: llama.cpp via `llama-cpp-python`
- **Models**: Quantized GGUF models running on CPU
- **Frontend**: Vanilla HTML/CSS/JS with a dark-themed responsive UI

## Models Used

| Model | Purpose |
|-------|---------|
| `codellama-7b-instruct.Q4_0.gguf` | Code generation assistant |
| `Meta-Llama-3.1-8B-Instruct-Q4_K_S.gguf` | File classification & documentation |
| `qwen2.5-coder-7b-instruct-q4_0.gguf` | Code analysis & review |
| `qwen2.5-14b-instruct-q4_0.gguf` | MR/PR review |

## Setup

```bash
# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Edit .env with your MODEL_BASE_PATH and GITHUB_TOKEN

# Download models into your models directory
# (See Hugging Face links for each model above)

# Run
python start.py
```

Open `http://localhost:8000` in your browser.

## Configuration

Set these in your `.env` file:

| Variable | Description |
|----------|-------------|
| `MODEL_BASE_PATH` | Path to directory containing GGUF model files |
| `GITHUB_TOKEN` | GitHub Personal Access Token (for PR review feature) |

## System Requirements

- 16+ CPU cores (recommended)
- 32 GB RAM
- No GPU required — runs fully on CPU with quantized models

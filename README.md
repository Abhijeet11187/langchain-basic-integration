# 🦜🔗 LangChain Basics Integration

A beginner-friendly notebook demonstrating how to use **LangChain** to interact with multiple LLM providers (OpenAI and Google Gemini) through a unified interface.

---

## 📖 Overview

One of LangChain's biggest strengths is its **provider-agnostic design** — you can swap between OpenAI, Google Gemini, Anthropic, and others by simply changing the model object, while keeping the rest of your code identical. This notebook walks through that concept with hands-on examples.

---

## 📁 Project Structure

```
langchain-basics-integration/
│
├── langchain_basics_integration.ipynb   # Main notebook
├── keys/
│   └── .openai_api_key.txt              # OpenAI API key (not committed)
├── gemini_keys/
│   └── .gemini_api_key.txt              # Gemini API key (not committed)
└── README.md
```

> ⚠️ **Never commit API keys to GitHub.** Add `keys/` and `gemini_keys/` to your `.gitignore`.

---

## 🚀 What's Covered

| Section | Description |
|---|---|
| **OpenAI LLM** | Using `langchain-openai` with the `OpenAI` completion wrapper |
| **OpenAI Chat Model** | Using `ChatOpenAI` for chat-style interactions |
| **Google Gemini** | Switching to `GoogleGenerativeAI` via `langchain-google-genai` |
| **Unified `.invoke()`** | Same interface across all providers |

---

## 🛠️ Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/langchain-basics-integration.git
cd langchain-basics-integration
```

### 2. Install dependencies

```bash
pip install langchain-openai langchain-google-genai
```

### 3. Add your API keys

Create the key files locally (these are excluded from git):

```bash
mkdir -p keys gemini_keys
echo "your-openai-api-key" > keys/.openai_api_key.txt
echo "your-gemini-api-key" > gemini_keys/.gemini_api_key.txt
```

- Get your OpenAI API key from [platform.openai.com](https://platform.openai.com)
- Get your Gemini API key from [aistudio.google.com](https://aistudio.google.com)

### 4. Launch Jupyter

```bash
jupyter notebook langchain_basics_integration.ipynb
```

---

## 💡 Key Concept

```python
# OpenAI
from langchain_openai import ChatOpenAI
llm = ChatOpenAI(api_key=OPENAI_KEY, model="gpt-4o-mini", temperature=0)

# Google Gemini
from langchain_google_genai import GoogleGenerativeAI
llm = GoogleGenerativeAI(google_api_key=GEMINI_KEY, model="gemini-2.5-flash", temperature=0)

# Same call regardless of provider ✅
llm.invoke("How many states are there in India?")
```

---

## 📦 Requirements

- Python 3.9+
- `langchain-openai`
- `langchain-google-genai`
- Jupyter Notebook / JupyterLab

---

## 🔒 .gitignore

Make sure your `.gitignore` includes:

```
keys/
gemini_keys/
.env
__pycache__/
*.pyc
.ipynb_checkpoints/
```

---

## 📌 Notes

- `temperature=0` is used throughout for deterministic, reproducible outputs.
- The notebook uses both **LLM-style** (completion) and **Chat-style** model wrappers to highlight the difference.

---

## 📄 License

This project is for educational purposes. Feel free to use and modify it as needed.

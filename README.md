# AI Tutor MCP Toolkit

> A Gradio + OpenAI example application for teaching, summarizing, quizzing, and flashcard generation via streaming.  
> Built as part of my learning journey from the **“Master LLM Engineering & AI Agents: Build 14 Projects – 2025”** Udemy course.  
> Course link: https://www.udemy.com/share/10dwct3@ldM-I-uTdPMY73imN1Wq5Sf_1xPSReqZEYPg_1QudAvzw4AkFaSNCAci49wx_rfSWw==/

## 🧠 Overview

This project is an interactive AI Tutor interface built using:

- **Gradio** for the frontend UI  
- **OpenAI’s streaming Chat API** (e.g. GPT-4o mini) for real-time responses  
- A small MCP (Multi-Channel Proxy / Server-Side Events) tool system (in your first file) to manage multiple “tools” like concept explanation, summarization, flashcard generation, and quizzing  
- Python, asyncio, and HTTPX / requests for integration

The goal is to demonstrate how you can build a modular AI teaching assistant with multiple streaming capabilities — a good reference for projects from the Udemy course.

## 🎯 Features / Tools

| Tool Name           | Purpose                                                                 | Inputs / Arguments                             | Output Style        |
|----------------------|-------------------------------------------------------------------------|--------------------------------------------------|---------------------|
| `explain_concept`     | Explain a concept at different comprehension levels (1 to 5)             | `question`, `level` (1–5)                        | Streaming explanation |
| `summarize_text`      | Summarize long text down to a target compression ratio                    | `text`, `compression_ratio` (0.1–0.8)           | Streaming summary     |
| `generate_flashcards` | Produce a set of Q/A flashcards (JSON-lines format)                        | `topic`, `num_cards` (1–20)                     | JSON-lines stream     |
| `quiz_me`              | Generate a multiple-choice quiz + answer key                               | `topic`, `level`, `num_questions` (1–15)        | Quiz (streamed)       |

The Gradio web app binds UI tabs to each tool so you can try them interactively via browser.

## 🛠️ Setup & Usage

### Prerequisites

- A valid OpenAI API key  
- Python ≥ 3.8  
- Internet access from your environment  

### Installation & Running

```bash
git clone <this-repo-url>
cd <repo-directory>

# Create a virtual environment and activate it
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate         # Windows (PowerShell or CMD)

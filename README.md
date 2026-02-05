# Custom Burp AI Agent (Windows)

This repository provides a **Windows-focused setup** for using **Burp AI Agent**
with **Ollama (free, local AI)** and **OpenAI (cloud AI)**.

It is intended for **learning, testing, and experimentation** with AI-assisted
web application security testing.

---

## Setup (Windows)

### Prerequisites
- Java **JDK 21**
- Burp Suite (Community or Professional)
- Git (optional)

---

## Build Extension

```bat
git clone https://github.com/Naresh76191/Custom-Burp-AI-Agent.git
cd Custom-Burp-AI-Agent
gradlew clean shadowJar
build\libs\
```
### Load into Burp

1. Open Burp Suite
2. Extensions → Installed → Add
3. Extension type: Java
4. Select the generated .jar

### Option 1: Ollama (FREE – Local AI)
Install Ollama
Link : https://ollama.com/download
-> ollama pull qwen2.5:7b
-> ollama run qwen2.5:7b

### Burp Configuration
Backend: openai-compatible
Base URL: http://127.0.0.1:11434/v1
Model: qwen2.5:7b
API Key: ollama
Timeout: 120

### Option 2: OpenAI (Cloud AI)
Get API key:
https://platform.openai.com/api-keys
Backend: openai-compatible
Base URL: https://api.openai.com/v1
Model: gpt-4o-mini
API Key: YOUR_OPENAI_API_KEY
Timeout: 60

### Usage:
1. Browse a target through Burp Proxy
2. Capture a request with parameters
3. Right-click → Extensions → Custom AI Agent → Find vulnerabilities


Credits

This project is based on the original Burp AI Agent by
https://github.com/six2dez/burp-ai-agent

This repository contains custom modifications, Windows setup,
and Ollama/OpenAI integration by Naresh Kumar.

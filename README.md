# Local RAG Chat with Llama 3.2

![Python](https://img.shields.io/badge/Python-3.12%2B-blue)
![Ollama](https://img.shields.io/badge/Ollama-Llama3.2-orange)
![Reflex](https://img.shields.io/badge/Frontend-Reflex-black)
![License](https://img.shields.io/badge/License-MIT-green)

A privacy-focused, local Retrieval-Augmented Generation (RAG) chatbot built with **Reflex**, **LangChain**, and **Ollama**. 

This application allows you to chat with your documents using the power of the **Llama 3.2** model entirely offline on your Mac. It enhances standard AI responses by retrieving context from a local vector database before answering.

##  Features

- ** Modern Interface:** A clean, dark-mode chat interface built with Reflex.
- ** 100% Local:** Runs entirely on your machine using Ollama—no data leaves your device.
- ** Llama 3.2 Powered:** Leverages Meta's latest lightweight model for fast, accurate reasoning.
- ** RAG Architecture:** Retrieves relevant context using FAISS vector search for factual answers.
- ** Extensible:** Built on LangChain, making it easy to swap models or datasets.

## Prerequisites

Before running the project, ensure you have the following installed:

- **Python 3.12+**
- **[Ollama](https://ollama.com/)** (Installed and running)

### Model Setup
You need to pull the Llama 3.2 model locally. Open your terminal and run:

```bash
ollama pull llama3.2
```
##  Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/debda45/Local-RAG-with-Ollama.git](https://github.com/debda45/Local-RAG-with-Ollama.git)
   cd Local-RAG-with-Ollama
   ```
2. **Create a virtual environment:**
  ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. **Install dependencies:**
   ```bash
      pip install -r requirements.txt
   ```
##  Usage

1. **Start Ollama:**
   Ensure the Ollama application is running in the background (look for the icon in your menu bar).

2. **Run the application:**
   To use the Llama 3.2 model, set the environment variable and start the server:
   ```bash
   export OLLAMA_MODEL=llama3.2
   reflex run

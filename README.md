# Local RAG Chat with Llama 3.2

![Python](https://img.shields.io/badge/Python-3.12%2B-blue)
![Ollama](https://img.shields.io/badge/Ollama-Llama3.2-orange)
![Reflex](https://img.shields.io/badge/Frontend-Reflex-black)
![License](https://img.shields.io/badge/License-MIT-green)

A privacy-focused, local Retrieval-Augmented Generation (RAG) chatbot built with **Reflex**, **LangChain**, and **Ollama**. 

This application allows you to chat with your documents using the power of the **Llama 3.2** model entirely offline on your Mac. It enhances standard AI responses by retrieving context from a local vector database before answering.

##  Features

- **Modern Interface:** A clean, dark-mode chat interface built with Reflex.
- **100% Local:** Runs entirely on your machine using Ollama—no data leaves your device.
- **Llama 3.2 Powered:** Leverages Meta's latest lightweight model for fast, accurate reasoning.
- **RAG Architecture:** Retrieves relevant context using FAISS vector search for factual answers.
- **Extensible:** Built on LangChain, making it easy to swap models or datasets.

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
3. **Start Chatting:**
    Open your browser and navigate to: http://localhost:3000

##  Project Structure
Local-RAG-with-Ollama/
├── assets/                    # Static assets
├── faiss_index_neural_bridge/ # FAISS vector database (Main)
│   ├── index.faiss            # Index file
│   └── index.pkl              # Metadata
├── faiss_index_subset/        # FAISS vector database (Subset)
├── rag_gemma_reflex/          # Main Application Logic
│   ├── rag_gemma_reflex.py    # UI components & styling
│   ├── rag_logic.py           # Core RAG & LangChain logic
│   └── state.py               # State management
├── requirements.txt           # Python dependencies
└── rxconfig.py                # Reflex configuration

##  How It Works

This application implements a standard RAG pipeline:

1.  **Embedding:** Documents are converted into numerical vectors using HuggingFace's `all-MiniLM-L6-v2` model and stored in a FAISS index.
2.  **Retrieval:** When you ask a question, the system searches the FAISS index for the most relevant text chunks.
3.  **Generation:** The retrieved text + your question are sent to **Llama 3.2** (via Ollama) to generate a final answer based on the facts provided.

##  Customization

You can customize the application by editing `rag_gemma_reflex/rag_logic.py`:

- **Change Model:** Update `DEFAULT_OLLAMA_MODEL` to use other models (e.g., `mistral`, `gemma2`).
- **Change Dataset:** Modify `DATASET_NAME` to load different HuggingFace datasets.
- **Use Custom Data:** Replace the dataset loader with `PyPDFLoader` or `TextLoader` to chat with your own files.

##  License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- **Reflex** for the reactive web framework.
- **LangChain** for the RAG chain orchestration.
- **Ollama** for making local LLMs accessible.

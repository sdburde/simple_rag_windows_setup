# LLM RAG Project - Windows Setup Guide

## Prerequisites
- Windows 10/11
- Python 3.12
- Ollama (for local embeddings)
- GROQ API key (for ChatGroq)

## Setup Instructions

### 1. Clone the Repository
```powershell
git clone <your-repo-url>
cd llm_rag
```

### 2. Create Python Virtual Environment
```powershell
python -m venv langchain_venv
langchain_venv\Scripts\activate
```

### 3. Install Dependencies
```powershell
pip install -r requirements.txt
```

### 4. Set Up Ollama
1. Download and install Ollama from [ollama.com](https://ollama.com/)
2. Pull required models:
```powershell
ollama pull mxbai-embed-large
ollama pull llama3
```

### 5. Fix DNS Resolution (If Needed)
If you encounter download errors:
1. Open Notepad as Administrator
2. Edit `C:\Windows\System32\drivers\etc\hosts`
3. Add this line:
```
104.16.17.85 dd20bb891979d25aebc8bec07b2b3bbc.r2.cloudflarestorage.com
```
4. Save and flush DNS:
```powershell
ipconfig /flushdns
```

### 6. Environment Variables
Create `.env` file with your GROQ API key:
```env
GROQ_API_KEY=your_api_key_here
```

## Running the Project

### 1. Activate Environment
```powershell
langchain_venv\Scripts\activate
```

### 2. Start Jupyter Notebook
```powershell
jupyter notebook
```
Open `simplerag.ipynb` to run the RAG pipeline.

### 3. Alternative: Run Script Directly
```powershell
python your_script.py
```

## Project Structure
```
llm_rag/
├── chroma_db/            # Vector store directory
├── langchain_venv/       # Python virtual environment
├── .env                  # Environment variables
├── attention.pdf         # Example document
├── requirements.txt      # Python dependencies
├── simplerag.ipynb       # Jupyter notebook with RAG implementation
└── speech.txt            # Example text document
```

## Troubleshooting
- **Ollama connection issues**: Try changing DNS to Google (8.8.8.8) or Cloudflare (1.1.1.1)
- **Missing dependencies**: Run `pip install -r requirements.txt` again
- **GROQ API errors**: Verify your API key in `.env`



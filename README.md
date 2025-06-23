# Earnings Call Summarizer

AI-powered tool for analyzing and summarizing earnings call recordings from YouTube.

---

## Overview

**Earnings Call Summarizer** helps investors and analysts quickly extract actionable insights from earnings call recordings. With advanced speech-to-text, text embedding, and Retrieval-Augmented Generation (RAG), it provides detailed analysis and answers to your custom questions—all through an intuitive web interface.

Just paste a YouTube link to an earnings call, and the app will:
- Download and transcribe the audio,
- Break the transcript into sections,
- Let you ask specific questions,
- Deliver comprehensive, AI-generated answers.

---

## Features

- **Audio Download & Transcription**
  - Download audio directly from YouTube.
  - Transcribe speech to text using [AssemblyAI](https://www.assemblyai.com/).

- **Text Chunking & Embedding**
  - Split transcripts into manageable text chunks.
  - Generate vector embeddings using [SentenceTransformers](https://www.sbert.net/).

- **AI-Powered Question Answering**
  - Retrieve relevant transcript sections with [FAISS](https://github.com/facebookresearch/faiss).
  - Generate detailed answers via OpenAI’s GPT-3.5-turbo.

- **User-Friendly Web Interface**
  - Enter YouTube URLs, track analysis progress, and ask questions.
  - Real-time status updates.

---

## How It Works

### Indexing Pipeline

1. **Audio Download**
    - Paste a YouTube link; audio is downloaded with `yt-dlp`.
    - Audio is converted to MP3 using `ffmpeg`.
2. **Transcription**
    - Audio is transcribed by AssemblyAI.
    - The transcript is saved for processing.
3. **Text Processing**
    - The transcript is split into smaller chunks.
    - Each chunk is embedded into a vector using SentenceTransformer.
4. **Indexing**
    - Chunks are indexed with FAISS for efficient similarity search.

### Query Pipeline

1. **Retrieval**
    - User submits a question.
    - The system retrieves and reranks the most relevant transcript chunks.
2. **Generation**
    - The top chunks are sent to GPT-3.5-turbo to generate an accurate answer.

---

## Quickstart

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/earnings-call-summarizer.git

# 2. Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set your API keys
# Replace 'assemblyaiapikey' and 'enter_open_AI_API_Key' in your configuration

# 5. Run the app
streamlit run app.py

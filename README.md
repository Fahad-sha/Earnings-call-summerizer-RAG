Earnings Call Summarizer: AI-Powered Insights from Earnings Calls
Overview
Earnings Call Summarizer is a powerful web application designed for investors and analysts to quickly extract actionable insights from earnings call recordings. Leveraging state-of-the-art speech-to-text, text embedding, and Retrieval Augmented Generation (RAG) with large language models, it delivers detailed analysis and question-answering on any earnings call, all within an intuitive web interface.

Simply input a YouTube link to an earnings call—Earnings Call Summarizer will transcribe the audio, break the transcript into manageable sections, and let you ask targeted questions to get comprehensive, AI-generated answers.

Key Features
Audio Download & Transcription

Download audio from YouTube earnings call videos.

Convert speech to text using AssemblyAI for highly accurate transcription.

Text Chunking & Embedding

Automatically split transcripts into processable chunks.

Generate vector representations of each chunk using SentenceTransformers.

AI-Powered Question Answering with RAG

Efficiently retrieve relevant transcript sections using a FAISS index.

Generate detailed answers to user questions via OpenAI’s GPT-3.5-turbo.

Interactive Web Interface

Simple UI to enter YouTube URLs, track analysis progress, and ask questions.

Real-time feedback on processing status.

How It Works
Indexing Pipeline
Audio Download

Input a YouTube URL; the app uses yt-dlp to download audio.

Converts audio to MP3 format using ffmpeg.

Transcription

Uploads audio to AssemblyAI for transcription.

Retrieves and stores the transcript.

Text Processing

Splits the transcript into manageable chunks.

Embeds each chunk as a vector using SentenceTransformer.

Indexing

Indexes embedded chunks using FAISS for efficient similarity search.

Query Pipeline
Retrieval

User submits a question about the earnings call.

System retrieves the most relevant transcript chunks using vector search and reranks them with a semantic ranking model.

Generation

Top 10 relevant chunks are passed to GPT-3.5-turbo to generate a conversational, context-aware response.

Setup & Installation
Clone the Repository
git clone https://github.com/yourusername/earnings-call-summarizer.git

Create and Activate a Virtual Environment
python -m venv .venv
source .venv/bin/activate # On Windows: .venv\Scripts\activate

Install Dependencies
pip install -r requirements.txt

Configure API Keys

Replace 'assemblyaiapikey' and 'enter_open_AI_API_Key' in your config.

Run the Application
streamlit run app.py


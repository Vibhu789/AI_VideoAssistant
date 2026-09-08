# 🎥 AI Video Agent

An AI-powered video and meeting assistant that transforms YouTube videos into searchable, intelligent knowledge.

The application extracts audio from a YouTube video, converts speech into text using **Sarvam AI**, generates summaries and professional titles using **Mistral AI**, and enables users to ask questions about the video using **Retrieval-Augmented Generation (RAG)**.

---

## 🚀 Features

* 🎬 Download audio from YouTube videos
* 🎙️ Convert audio into text using **Sarvam AI**
* 🌐 Support for Hindi / Hinglish transcription
* 📝 Generate concise meeting summaries
* 🏷️ Automatically generate professional meeting titles
* 🔎 Store transcript data in a vector store
* 🤖 Ask questions about the video using RAG
* 📚 Retrieve relevant transcript context before answering
* 🔐 Secure API key management using environment variables
* ⚡ Built using LangChain and LCEL pipelines

---

## 🧠 How It Works

```text
YouTube Video
     │
     ▼
   yt-dlp
     │
     ▼
 Audio Extraction
     │
     ▼
  Sarvam AI API
     │
     ▼
   Transcript
     │
     ├──────────────► Mistral AI
     │                    │
     │                    ├──► Meeting Summary
     │                    └──► Meeting Title
     │
     ▼
  Vector Store
     │
     ▼
     RAG Pipeline
     │
     ▼
 User Question
     │
     ▼
 Relevant Context Retrieval
     │
     ▼
 Mistral AI
     │
     ▼
   Answer
```

---

## 🛠️ Tech Stack

| Technology        | Purpose                                   |
| ----------------- | ----------------------------------------- |
| **Python**        | Core programming language                 |
| **LangChain**     | LLM and RAG pipeline                      |
| **Mistral AI**    | Summarization, title generation & Q&A     |
| **Sarvam AI**     | Speech-to-text transcription              |
| **yt-dlp**        | YouTube audio extraction                  |
| **Vector Store**  | Transcript storage and semantic retrieval |
| **LCEL**          | Building LangChain pipelines              |
| **python-dotenv** | Environment variable management           |

---

## 🔑 APIs Used

### 1. Mistral AI API

Used for:

* Meeting summarization
* Automatic meeting title generation
* RAG-based question answering

Model:

```text
mistral-small-latest
```

### 2. Sarvam AI API

Used for:

* Speech-to-text transcription
* Hindi / Hinglish audio transcription

---

## 📂 Project Structure

```text
AI-VidioAgent/
│
├── core/
│   ├── summarizer.py
│   ├── vector_store.py
│   └── ...
│
├── main.py
├── requirements.txt
├── .env
├── .gitignore
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd AI-VidioAgent
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv .venv
```

Activate it:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔐 Environment Variables

Create a `.env` file in the project root:

```env
MISTRAL_API_KEY=your_mistral_api_key
SARVAM_API_KEY=your_sarvam_api_key
```

> ⚠️ Never commit your `.env` file or API keys to GitHub.

Add this to `.gitignore`:

```gitignore
.env
.venv/
__pycache__/
```

---

## ▶️ Usage

Run the application:

```bash
python main.py
```

Provide a YouTube video URL and select the required language.

The application will:

1. Download the video's audio.
2. Split the audio into manageable chunks.
3. Transcribe the audio using Sarvam AI.
4. Generate a meeting title using Mistral AI.
5. Generate a concise summary.
6. Build a vector store from the transcript.
7. Allow users to ask questions about the video.

---

## 💬 RAG-Based Question Answering

The project uses **Retrieval-Augmented Generation (RAG)** to answer questions based only on the transcript.

For example:

```text
Question:
What were the main topics discussed in the meeting?

Answer:
The meeting mainly discussed project progress,
upcoming tasks, and the next development milestones.
```

The system first retrieves the most relevant transcript sections and then provides them as context to the Mistral model.

This helps keep answers relevant to the actual video content.

---

## 🧩 LangChain Pipeline

The RAG pipeline follows this flow:

```text
User Question
      │
      ▼
Retriever
      │
      ▼
Relevant Transcript Chunks
      │
      ▼
Context Formatting
      │
      ▼
Prompt Template
      │
      ▼
Mistral AI
      │
      ▼
Final Answer
```

---

## 🔒 Security

API credentials are loaded through environment variables rather than being hardcoded in the source code.

Example:

```python
import os

api_key = os.getenv("MISTRAL_API_KEY")
```

Make sure `.env` is included in `.gitignore`.

---

## 🎯 Project Goal

The goal of **AI Video Agent** is to make long-form video content easier to understand, search, and interact with.

Instead of manually watching an entire meeting or lecture, users can:

* Get a quick summary
* Understand the main discussion points
* Search the transcript
* Ask natural-language questions
* Get answers based on the video's actual content

---

## 🔮 Future Improvements

* 🌍 Multi-language transcription
* 📌 Timestamp-based answers
* 📊 Better meeting insights
* 👥 Speaker identification
* 💾 Persistent conversation history
* 🌐 Web-based user interface
* ⚡ Streaming responses
* 📈 Advanced analytics for meetings

---

## 📌 Key Concepts

This project demonstrates practical implementation of:

* Large Language Models (LLMs)
* Speech-to-Text
* Prompt Engineering
* LangChain
* LCEL
* Vector Search
* Retrieval-Augmented Generation (RAG)
* Semantic Search
* AI-powered Document/Transcript Q&A

---

## 👨‍💻 Author

Developed as an AI-powered video intelligence project using Python, LangChain, Mistral AI, and Sarvam AI.

---



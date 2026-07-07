# 🎬 AI Video Assistant

An intelligent video analysis and meeting assistant built with Streamlit, Whisper, LangChain, and Mistral AI. It processes videos/audio, transcribes content, and uses advanced language models to summarize, extract action items, and provide an interactive Q&A experience based on the video context.

## 🌟 Features

- **Audio/Video Acquisition**: Easily ingest media from local files or online sources (via `yt-dlp`).
- **High-Quality Transcription**: Local speech-to-text powered by OpenAI's Whisper model.
- **Translation**: Translates Hindi content to English (using `deep-translator`).
- **Intelligent Summarization**: Automatically generates concise summaries and titles from transcripts.
- **Information Extraction**: Automatically pulls out key decisions, action items, and important questions discussed in the media.
- **Interactive Q&A (RAG)**: Ask specific questions about the video context using Retrieval-Augmented Generation powered by ChromaDB, LangChain, and Mistral AI.
- **Export Options**: Export transcripts, summaries, and Q&A to PDF or Text formats.
- **Modern UI**: A sleek, custom-styled Streamlit interface for a smooth user experience.

## 🛠️ Technology Stack

- **Frontend**: [Streamlit](https://streamlit.io/)
- **Transcription**: [OpenAI Whisper](https://github.com/openai/whisper) & [PyTorch](https://pytorch.org/)
- **LLM Orchestration**: [LangChain](https://www.langchain.com/) & [Mistral AI API](https://mistral.ai/)
- **Vector Database**: [ChromaDB](https://www.trychroma.com/)
- **Embeddings**: [Sentence Transformers](https://www.sbert.net/) (HuggingFace)
- **Audio Processing**: [FFmpeg](https://ffmpeg.org/) & [PyDub](http://pydub.com/)

## 🚀 Getting Started

### Prerequisites

1. **Python 3.10+**
2. **FFmpeg**: Must be installed on your system and available in your PATH.
   - *Windows*: Download from [gyan.dev](https://www.gyan.dev/ffmpeg/builds/) or use `winget install ffmpeg`.
   - *macOS*: `brew install ffmpeg`
   - *Linux*: `sudo apt install ffmpeg`

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/video_ai_assistant.git
   cd video_ai_assistant
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # macOS/Linux
   source venv/bin/activate
   ```

3. **Install the dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up Environment Variables:**
   Create a `.env` file in the root directory and add your API keys:
   ```env
   MISTRAL_API_KEY=your_mistral_api_key_here
   ```

### Running the Application

Start the Streamlit development server:

```bash
python -m streamlit run app.py
```

Open your browser and navigate to `http://localhost:8501`.

## 📁 Project Structure

- `app.py`: The main Streamlit application entry point containing the UI layout and logic.
- `main.py`: CLI or alternative entry point for testing backend features.
- `core/`: Core business logic modules.
  - `transcriber.py`: Whisper-based audio transcription.
  - `summarizer.py`: Text summarization logic.
  - `extractor.py`: Extracts action items, decisions, etc.
  - `rag_engine.py`: RAG chain builder and querying logic.
  - `vector_store.py`: ChromaDB initialization and document ingestion.
- `utils/`: Utility scripts.
  - `audio_processor.py`: Audio extraction, format conversion, and splitting.
- `.env`: (Not tracked) Your environment variables.
- `requirements.txt`: Python package dependencies.
- `vector_db/`: (Ignored) Local directory where ChromaDB stores its vector indices.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

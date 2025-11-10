# 🤖 Jarvis - AI Document Chat Assistant

An intelligent chatbot powered by **Google Gemini AI**, **Pinecone Vector Database**, and **Streamlit** that lets you upload documents (PDF/PPTX) and chat with their content using natural language.

## ✨ Features

- 📄 **Upload Documents**: Support for PDF and PowerPoint (PPTX) files
- 🔍 **Semantic Search**: Intelligent retrieval of relevant document snippets using sentence transformers
- 💬 **AI Chatbot**: Conversational interface powered by Google Gemini 2.5 Flash
- 💾 **Vector Database**: Pinecone for efficient document embedding storage and retrieval
- 🔄 **Chat History**: Persistent conversation history within a session
- 🌐 **Cloud Deployment**: Live on Streamlit Cloud for online access
- ⚡ **Fast & Free**: Uses free tier APIs and models

## 🚀 Live Demo

**Try it here:** [Jarvis AI Chatbot](https://jarvis-24mcab48rohan.streamlit.app)

## 📋 How It Works

1. **Upload Documents**: Upload PDF or PPTX files through the Upload tab
2. **Processing**: Files are split into chunks and embedded using SentenceTransformers
3. **Storage**: Embeddings are stored in Pinecone vector database
4. **Query**: When you ask a question, it finds similar document chunks
5. **Response**: Gemini AI generates an answer based on the retrieved context

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Frontend** | Streamlit |
| **LLM** | Google Gemini 2.5 Flash API |
| **Vector DB** | Pinecone |
| **Embeddings** | Sentence-Transformers (all-MiniLM-L6-v2) |
| **Document Parsing** | PyPDF, python-pptx |
| **Deployment** | Streamlit Cloud |

## 📦 Installation

### Prerequisites
- Python 3.8+
- Git
- API Keys:
  - [Google Gemini API Key](https://aistudio.google.com/apikey)
  - [Pinecone API Key](https://app.pinecone.io)

### Local Setup

1. **Clone the repository**
```bash
git clone https://github.com/24mcab48-rohan/jarvis.git
cd jarvis
```

2. **Create virtual environment**
```bash
python -m venv venv
venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Configure environment variables**

Create a `.env` file in the project root:
```
GEMINI_API_KEY=your_gemini_api_key_here
PINECONE_API_KEY=your_pinecone_api_key_here
INDEX_NAME=jarvis-index
```

5. **Run the app locally**
```bash
streamlit run app.py
```

The app will open at `http://localhost:8501`

## 📝 Usage

### Upload Documents
1. Go to the **"📤 Upload"** tab
2. Select one or more PDF/PPTX files
3. Click **"Send to Pinecone"**
4. Wait for processing (files are split into chunks and embedded)

### Chat with Documents
1. Go to the **"💬 Chat"** tab
2. Type your question in the input box
3. Click **"Ask"**
4. Get AI-powered responses based on your documents
5. Continue the conversation - chat history is maintained

## 🔧 Configuration

### Key Parameters (in `app.py`)

```python
EMBED_MODEL_NAME = "sentence-transformers/all-MiniLM-L6-v2"  # Embedding model
EMBED_DIM = 384                                               # Embedding dimension
max_output_tokens = 4096                                      # Max response length
temperature = 0.7                                             # Response creativity (0-1)
```

### Document Chunking
```python
chunk_size = 800     # Words per chunk
chunk_overlap = 150  # Overlap between chunks
```

## 🌐 Deployment

### Deploy to Streamlit Cloud

1. Push code to GitHub (already done ✅)
2. Go to [Streamlit Cloud](https://share.streamlit.io)
3. Click **"New app"**
4. Select repository: `24mcab48-rohan/jarvis`
5. Set main file to `app.py`
6. Click **"Deploy"**

### Add Secrets in Streamlit Cloud
1. Go to app settings (⋯ menu)
2. Click **"Settings"** → **"Secrets"**
3. Add your API keys:
```toml
GEMINI_API_KEY = "your_key_here"
PINECONE_API_KEY = "your_key_here"
INDEX_NAME = "jarvis-index"
```

## 📊 Project Structure

```
jarvis/
├── app.py                  # Main Streamlit application
├── requirements.txt        # Python dependencies
├── .env                    # Environment variables (local only)
├── .streamlit/
│   └── secrets.toml       # Streamlit secrets (cloud only)
├── .gitignore             # Git ignore file
└── README.md              # This file
```

## 🔑 Environment Variables

| Variable | Description |
|----------|-------------|
| `GEMINI_API_KEY` | Google Gemini API key |
| `PINECONE_API_KEY` | Pinecone database API key |
| `INDEX_NAME` | Pinecone index name (default: "jarvis-index") |

## 📚 Dependencies

- **streamlit** - Web app framework
- **google-generativeai** - Gemini AI integration
- **pinecone-client** - Vector database client
- **sentence-transformers** - Document embeddings
- **pypdf** - PDF parsing
- **python-pptx** - PowerPoint parsing
- **python-dotenv** - Environment variables

See `requirements.txt` for full list.

## 🎯 Features Implemented

- ✅ Multi-file upload support
- ✅ PDF and PPTX parsing
- ✅ Semantic chunking and embedding
- ✅ Vector database integration
- ✅ Multi-turn chat with history
- ✅ Comprehensive AI responses
- ✅ Cloud deployment ready
- ✅ Error handling and validation

## 🚦 Roadmap

- [ ] User authentication
- [ ] Document management (delete, update)
- [ ] Export chat history
- [ ] Custom UI styling
- [ ] Multi-language support
- [ ] Web search integration
- [ ] Document metadata display
- [ ] Query suggestions

## 🐛 Troubleshooting

### Issue: "No data found. Please upload files first."
**Solution**: Make sure you've uploaded documents and clicked "Send to Pinecone" button

### Issue: API Key errors
**Solution**: Verify your API keys are correctly set in `.env` (local) or Streamlit Secrets (cloud)

### Issue: Slow responses
**Solution**: Pinecone free tier has rate limits. Wait a moment before next query

### Issue: Empty responses from Gemini
**Solution**: Content safety filters may be active. Try rephrasing your question

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

- **GitHub**: [@24mcab48-rohan](https://github.com/24mcab48-rohan)
- **Repository**: [Jarvis](https://github.com/24mcab48-rohan/jarvis)

## 🤝 Contributing

Contributions are welcome! Feel free to:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📞 Support

For issues, questions, or suggestions, please:
- Open an issue on [GitHub Issues](https://github.com/24mcab48-rohan/jarvis/issues)
- Check existing documentation

## 🙏 Acknowledgments

- [Google Gemini API](https://ai.google.dev/)
- [Pinecone Vector Database](https://www.pinecone.io/)
- [Streamlit](https://streamlit.io/)
- [Sentence Transformers](https://www.sbert.net/)

---

**Made with ❤️ by Rohan**

⭐ If you like this project, please consider giving it a star on GitHub!

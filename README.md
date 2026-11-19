
# RAG-Based Document Question Answering System

## About the Project

This project implements a Retrieval-Augmented Generation (RAG) system that allows users to ask questions directly from PDF documents.

It retrieves relevant information from the uploaded document and generates context-based answers using NVIDIA Nemotron.

## Technologies Used

- Python
- LangChain
- NVIDIA Nemotron
- Qdrant Vector Database
- FastEmbed
- PyPDF
- Python Dotenv

## Project Workflow

1. Load PDF documents.
2. Split documents into smaller text chunks.
3. Generate vector embeddings using FastEmbed.
4. Store embeddings in Qdrant.
5. Retrieve relevant document chunks.
6. Generate answers using NVIDIA Nemotron.

## Project Structure

```text
RAG-Document-QA-System/
│
├── document_loader/
│   └── your_document.pdf
│
├── main.py
├── requirements.txt
├── README.md
├── .gitignore
└── .env (create manually)
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Navigate into the project directory:

```bash
cd RAG-Document-QA-System
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## Provide Your Own PDF Document

The PDF used during development is not included in this repository.

Users need to provide their own PDF document.

Follow these steps:

1. Open the project directory.
2. Navigate to the `document_loader` folder.
3. Place your PDF document inside this folder.
4. Rename the PDF file to `STATS.pdf`.

Alternatively, if you want to use a different filename, update the PDF path in `main.py`:

```python
pdf_path = os.path.join(
    os.path.dirname(__file__),
    "document_loader",
    "YOUR_FILENAME.pdf"
)
```

**Note:** The current implementation supports PDF documents using PyPDFLoader.

## NVIDIA API Configuration

This project uses NVIDIA Nemotron for answer generation.

1. Visit https://build.nvidia.com/
2. Generate your NVIDIA API key.
3. Create a `.env` file in the root project directory.
4. Add your API key:

```env
NVIDIA_API_KEY=your_nvidia_api_key_here
```

Keep your API key private. Do not upload the `.env` file to GitHub.

## Run the Project

Execute:

```bash
python main.py
```

Once the application starts, you can enter questions directly into the terminal.

Type `exit` or `quit` to close the application.

## Example Questions

- What is the main topic discussed in the document?
- Explain the important concepts covered in the PDF.
- Summarize the key findings of the document.

## Key Features

- PDF document loading
- Automatic text chunking
- Vector embedding generation
- Semantic similarity search
- Context-based AI responses
- Interactive terminal-based question answering

## Future Improvements

- Web-based user interface
- Multiple PDF document support
- Persistent vector database storage
- Hybrid search using BM25
- FastAPI backend integration

## Author

Alok Shrivastaw

## License

MIT

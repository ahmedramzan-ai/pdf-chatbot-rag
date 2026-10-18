# PDF Chatbot with Retrieval-Augmented Generation (RAG)

A Python-based PDF question-answering application that allows users to upload documents and ask questions about their contents. The application uses document processing, semantic search, vector embeddings, and a language model to retrieve relevant information and generate answers.

## Overview

Reading and searching through lengthy PDF documents can be time-consuming. This project aims to simplify that process by providing an interactive chatbot that helps users find information within uploaded documents.

The application processes PDF files, divides their text into smaller chunks, converts those chunks into embeddings, and stores them in a vector database. When a user asks a question, the system retrieves relevant text to provide context for generating an answer.

## Features

- **PDF Upload:** Upload PDF documents through the Streamlit interface.
- **Text Extraction:** Extract readable text from uploaded PDF files.
- **Text Chunking:** Divide extracted text into smaller, manageable sections.
- **Semantic Embeddings:** Represent document chunks as numerical vectors.
- **Vector Search:** Use FAISS to retrieve relevant document sections.
- **Question Answering:** Generate document-based responses using a configured language model.
- **Conversational Memory:** Maintain conversation context across follow-up questions.
- **Interactive Interface:** Use a simple Streamlit web interface to upload documents and interact with the chatbot.
- **Configurable Settings:** Manage application settings and API credentials through environment variables and configuration files.
- **Error Handling:** Handle document-processing and language-model errors.

## Technology Stack

- Python
- Streamlit
- LangChain
- FAISS
- Hugging Face Sentence Transformers
- Google Gemini API
- PyPDF2

## How It Works

1. **Upload a PDF:** The user selects a document through the application interface.
2. **Extract Text:** The application extracts text from the uploaded PDF.
3. **Split Text into Chunks:** The extracted text is divided into smaller sections for processing.
4. **Generate Embeddings:** A sentence-transformer model converts the text chunks into vector representations.
5. **Store and Retrieve:** FAISS stores the vectors and retrieves the most relevant chunks for a user's question.
6. **Generate an Answer:** The configured language model uses the retrieved context to generate a response.
7. **Continue the Conversation:** Conversation memory supports follow-up questions.

## Project Structure

```text
pdf-chatbot-rag/
├── app.py
├── src/
│   ├── processor.py
│   ├── embedding.py
│   ├── chat.py
│   └── config.py
├── requirements.txt
├── README.md
└── .gitignore
```

*The structure above represents the expected project layout. Adjust it if your actual files differ.*

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/ahmedramzan-ai/pdf-chatbot-rag.git
cd pdf-chatbot-rag
```

### 2. Create a Virtual Environment

On Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

On macOS or Linux:

```bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the project root and add the API key required by the configured language model:

```env
GEMINI_API_KEY=your_api_key_here
```

Replace the placeholder with your own API key. Never commit `.env` or publish API credentials to GitHub.

### 5. Run the Application

```bash
python -m streamlit run app.py
```

The application will display a local URL in the terminal. Open that URL in your browser.

## Usage

1. Start the application.
2. Upload a PDF document using the sidebar.
3. Select the document-processing option.
4. Wait for the text extraction and embedding process to finish.
5. Enter a question about the document.
6. Review the response and ask follow-up questions as needed.

## Current Project Status

The PDF extraction, text chunking, and embedding-generation pipeline has been tested locally. Language-model response generation is currently pending resolution of API access and configuration issues.

The application requires a working API key and a supported model to complete the question-answering workflow successfully.

## Future Improvements

- Restore and test language-model API integration.
- Improve error messages and API failure handling.
- Test retrieval quality across different PDF documents.
- Add document previews and source references to responses.
- Improve the interface and conversation controls.
- Deploy the application after successful end-to-end testing.

## Security

- Store API keys in environment variables.
- Keep `.env` and `.venv` out of version control.
- Never expose API keys in source files, screenshots, or public commits.
- Review third-party dependency and licensing requirements before distributing the project.

## License

Refer to the applicable licenses of the source code and third-party dependencies used in this project. Ensure that any required copyright notices and attribution are preserved.

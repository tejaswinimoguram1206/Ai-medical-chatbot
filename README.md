# AI Medical Assistant (RAG Pipeline)

A context-aware medical question-answering assistant implementing Retrieval-Augmented Generation (RAG). The system processes unstructured medical documentation, constructs dense vector embeddings, and performs semantic similarity search using FAISS to ground LLM responses in verified medical references.


## Architecture Overview
Raw Documents (PDFs) ──> Text Chunking ──> Embeddings Generation
│
▼
User Query ──> Dense Retrieval (FAISS) ──> Context Assembly ──> LLM Response

Set up a virtual environment:

Bash
# Using pip
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt

Execution Workflow
1. Build the Vector Store
Process the source files in data/ and serialize the FAISS embeddings index:

Bash
python create_memory_for_llm.py
2. Start the Application
Initialize the retrieval chain and start the query interface:

Bash
python medibot.py
Technical Specifications
Language: Python 3.10+

Framework: LangChain

Vector Engine: FAISS (Facebook AI Similarity Search)

Embedding Model: Hugging Face sentence-transformers

Medical Disclaimer
This project is built for research and demonstration purposes only. It is not evaluated for clinical decision-making or diagnostic use. Consult qualified healthcare professionals for medical advice and treatment.

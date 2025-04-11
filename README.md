# LangChain Documentation RAG Chatbot

This repository contains a Retrieval-Augmented Generation (RAG) chatbot that answers questions about LangChain documentation. The chatbot uses a local vector database built from LangChain documentation and leverages the Ollama's tinyllama model to generate accurate, context-aware responses.

## Features

- **Documentation-aware responses**: Answers questions based on LangChain documentation
- **Source citations**: Shows the exact documentation sources used for answers
- **Evaluation system**: Collects feedback on response quality
- **Parameter optimization**: Tools to find optimal retrieval settings
- **Simple CLI interface**: Easy-to-use command-line interaction

## System Requirements

- Python 3.8 or higher
- [Ollama](https://ollama.ai/) installed and running
- tinyllama model pulled in Ollama

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/C-W-Evans/chatbot_RAG.git
   cd chatbot_RAG
   ```

2. **Create a virtual environment**:
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On MacOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Install Ollama** (if not already installed):
   - Download from [ollama.ai](https://ollama.ai/)
   - Follow the installation instructions for your platform
   - Pull the tinyllama model:
     ```bash
     ollama pull tinyllama
     ```

## Usage

### Setup

1. **Ensure Ollama is running** with the tinyllama model available

2. **Process the LangChain documentation data**:
   ```bash
   cd src
   python main.py
   ```
   This will create the vector database required for answering questions.

### Using the Chatbot

1. **Launch the chatbot**:
   ```bash
   cd src
   python chatbot.py
   ```

2. **Ask questions** about LangChain documentation
   - Example: "What are different types of chains in LangChain?"
   - Example: "How do I create a retrieval QA chain?"
   - Example: "Explain agents in LangChain"

3. **View source citations** when prompted
   - Type 'y' when asked "Do you want to see the sources?"

4. **Rate answers and provide feedback** to help improve the system

5. **Exit the chatbot** by typing 'exit', 'quit', or 'bye'

### Running Tests

To test the chatbot with pre-defined complex queries:
```bash
cd tests
python complex_queries.py
```

## Project Structure

```
chatbot_RAG/
├── src/                  # Source code
│   ├── utils.py          # Document loading utilities
│   ├── embedding.py      # Document embedding and vectorization
│   ├── rag.py            # RAG implementation
│   ├── evaluation.py     # Evaluation system
│   ├── chatbot.py        # CLI interface
│   ├── main.py           # Data processing
│   └── optimize.py       # Parameter optimization
├── tests/                # Test scripts
│   └── complex_queries.py # Complex test questions
├── data/                 # Data directory
│   ├── input/            # Raw document data
│   └── vectordb/         # Vector database (created during setup)
├── logs/                 # Evaluation logs (created during usage)
└── README.md             # This file
```

## How It Works

This chatbot uses Retrieval-Augmented Generation (RAG) to provide accurate answers:

1. **Document Processing**: LangChain documentation is chunked and embedded into vector representations
2. **Question Processing**: User questions are converted to the same vector space
3. **Retrieval**: The system finds the most relevant documentation chunks for the question
4. **Generation**: The tinyllama model generates an answer using the retrieved documentation
5. **Evaluation**: Users can rate responses to help improve the system

## Acknowledgments

- Built using [LangChain](https://python.langchain.com/)
- Based on [Ollama](https://ollama.ai/) for local LLM inference
- Uses [ChromaDB](https://www.trychroma.com/) for vector storage
- Documentation source: [LangChain Documentation](https://python.langchain.com/docs/get_started)

## License

This project is released under the MIT License.
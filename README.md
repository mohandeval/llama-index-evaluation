# LlamaIndex Tutorials & RAG System Evaluation

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![LlamaIndex](https://img.shields.io/badge/LlamaIndex-Latest-green.svg)](https://www.llamaindex.ai/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A comprehensive collection of tutorials and experiments for building, evaluating, and optimizing **Retrieval-Augmented Generation (RAG)** systems using LlamaIndex.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Setup](#environment-setup)
- [Tutorials](#tutorials)
- [Key Experiments](#key-experiments)
- [Usage Examples](#usage-examples)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [Branches](#branches)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## 🎯 Overview

This repository contains hands-on tutorials and experiments exploring the **LlamaIndex** framework for building production-ready RAG systems. The primary focus is on understanding and optimizing key parameters like **chunk size**, **retrieval strategies**, and **evaluation metrics** to achieve the best performance for your use case.

### What You'll Learn

- Setting up LlamaIndex and understanding its core concepts
- Document loading, chunking, and indexing strategies
- Query engines and retrieval mechanisms
- Evaluating RAG systems using Faithfulness and Relevancy metrics
- Advanced retrieval techniques including hybrid search and reranking
- Finding optimal chunk sizes for your specific documents
- Real-world applications with SEC 10-K filings

## ✨ Features

- 📚 **Comprehensive Tutorials**: Step-by-step notebooks covering LlamaIndex basics to advanced topics
- 🔬 **Chunk Size Optimization**: Scientific evaluation of different chunk sizes (128, 256, 512, 1024, 2048)
- 📊 **Performance Metrics**: Measure response time, faithfulness, and relevancy
- 🔍 **Advanced Retrieval**: Hybrid search and reranking implementations
- 🧪 **Real-World Data**: Examples using Uber 10-K SEC filings
- ⚡ **Production-Ready**: Best practices for building scalable RAG systems

## 📁 Project Structure

```
llama-index-tutorials/
│
├── 📓 Notebooks/
│   ├── 01_setup_and_basics.ipynb              # LlamaIndex fundamentals
│   ├── 02_documents_and_chunking.ipynb        # Document processing
│   ├── 03_indexing_and_simple_queries.ipynb   # Basic indexing & queries
│   ├── 10_evaluatechunkSize.ipynb             # ⭐ Chunk size evaluation
│   ├── advanced_retrieval copy.ipynb          # Advanced techniques
│   ├── hybrid_search_and_reranking copy.ipynb # Hybrid search
│   └── Evaluating_the_Ideal_Chunk_Size_for_a_RAG_System_using_LlamaIndex.ipynb
│
├── 📂 data/
│   ├── 10k/                    # SEC 10-K filings (Uber 2021)
│   ├── documentation/          # Documentation files (e.g., spacy.md)
│   ├── research_papers/        # Research papers for experiments
│   └── sample_docs/            # Sample documents
│
├── 🐍 Python Files/
│   ├── main.py                 # Main application script
│   ├── test_bedrock_api_key.py # AWS Bedrock API testing
│   └── test_bedrock.py         # Bedrock integration tests
│
├── ⚙️ Configuration/
│   ├── pyproject.toml          # Project metadata & dependencies
│   ├── requirements.txt        # Python dependencies
│   ├── .env                    # Environment variables (not tracked)
│   └── .gitignore              # Git ignore rules
│
└── 📦 llmai_venv/              # Virtual environment (not tracked)
```

## 🚀 Getting Started

### Prerequisites

- **Python 3.8+** (Python 3.10+ recommended)
- **OpenAI API Key** (for GPT models)
- **Git** (for cloning the repository)
- Basic understanding of Python and machine learning concepts

### Installation

1. **Clone the repository**
   ```powershell
   git clone https://github.com/mohandeval/llama-index-tutorials.git
   cd llama-index-tutorials
   ```

2. **Create a virtual environment**
   ```powershell
   # Using Python venv
   python -m venv llmai_venv
   
   # Activate the virtual environment
   # On Windows PowerShell:
   .\llmai_venv\Scripts\Activate.ps1
   
   # On Windows Command Prompt:
   .\llmai_venv\Scripts\activate.bat
   
   # On macOS/Linux:
   source llmai_venv/bin/activate
   ```

3. **Install dependencies**
   ```powershell
   # Install all required packages
   pip install -r requirements.txt
   
   # Or using uv (faster alternative)
   uv pip install -r requirements.txt
   ```

### Environment Setup

1. **Create a `.env` file** in the project root:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   AWS_ACCESS_KEY_ID=your_aws_key_here  # Optional, for AWS Bedrock
   AWS_SECRET_ACCESS_KEY=your_aws_secret_here  # Optional
   ```

2. **Verify installation**
   ```powershell
   python -c "import llama_index; print('LlamaIndex installed successfully!')"
   ```

3. **Download sample data** (if not already present)
   - The notebooks will automatically download Uber 10-K data when run
   - Or manually place your documents in the `data/` folder

## 📚 Tutorials

### Beginner Level

1. **[01_setup_and_basics.ipynb](01_setup_and_basics.ipynb)**
   - Setting up LlamaIndex
   - Understanding core concepts
   - Your first RAG application

2. **[02_documents_and_chunking.ipynb](02_documents_and_chunking.ipynb)**
   - Loading documents
   - Text splitting strategies
   - Chunk size fundamentals

3. **[03_indexing_and_simple_queries.ipynb](03_indexing_and_simple_queries.ipynb)**
   - Creating vector indexes
   - Simple query engines
   - Basic retrieval

### Advanced Level

4. **[10_evaluatechunkSize.ipynb](10_evaluatechunkSize.ipynb)** ⭐ **Featured**
   - Comprehensive chunk size evaluation
   - Faithfulness & Relevancy metrics
   - Performance benchmarking

5. **[advanced_retrieval copy.ipynb](advanced_retrieval copy.ipynb)**
   - Advanced retrieval strategies
   - Custom retrievers
   - Query transformations

6. **[hybrid_search_and_reranking copy.ipynb](hybrid_search_and_reranking copy.ipynb)**
   - Hybrid search implementation
   - Reranking algorithms
   - Combining multiple retrievers

## 🔬 Key Experiments

### Chunk Size Evaluation Results

Based on experiments with Uber 10-K SEC filings:

| Chunk Size | Avg Response Time | Faithfulness | Relevancy | Balanced Score |
|------------|-------------------|--------------|-----------|----------------|
| 128        | 0.7958s           | 0.6000       | 0.6750    | 0.4265         |
| 256        | 0.7995s           | 0.6250       | 0.7500    | 0.4583         |
| 512        | 0.7482s           | 0.6500       | 0.7000    | 0.4714         |
| 1024       | 0.7719s           | 0.6750       | 0.8000    | 0.5031         |
| **2048**   | **0.6823s**       | **0.7000**   | **0.8500**| **0.5655** ⭐  |

**Key Findings:**
- ✅ Larger chunk sizes (2048) provide the best overall performance
- ✅ Improved faithfulness (fewer hallucinations)
- ✅ Higher relevancy scores
- ✅ Faster response times (counterintuitive but proven)

## 💡 Usage Examples

### Basic RAG Query

```python
from llama_index.core import SimpleDirectoryReader, VectorStoreIndex
from llama_index.llms.openai import OpenAI
import os

# Load documents
documents = SimpleDirectoryReader("./data/10k/").load_data()

# Create index
index = VectorStoreIndex.from_documents(documents)

# Query
query_engine = index.as_query_engine()
response = query_engine.query("What was Uber's revenue in 2021?")
print(response)
```

### Chunk Size Evaluation

```python
from llama_index.core import Settings
from llama_index.core.evaluation import FaithfulnessEvaluator, RelevancyEvaluator

# Configure chunk size
Settings.chunk_size = 2048

# Create evaluators
faithfulness = FaithfulnessEvaluator(llm=gpt4)
relevancy = RelevancyEvaluator(llm=gpt4)

# Evaluate responses
result = faithfulness.evaluate_response(response=response)
print(f"Faithfulness: {result.passing}")
```

### Using AWS Bedrock

```python
# Test Bedrock integration
from test_bedrock import test_bedrock_connection

result = test_bedrock_connection()
print(result)
```

## ⚙️ Configuration

### Key Parameters

- **chunk_size**: `2048` (recommended based on evaluation)
- **similarity_top_k**: `2` (default, adjust for more/fewer results)
- **LLM Model**: `gpt-3.5-turbo` for generation, `gpt-4o-mini` for evaluation
- **Embedding Model**: Default OpenAI embeddings

### Customization

Edit `Settings` in your notebooks:

```python
from llama_index.core import Settings

Settings.chunk_size = 2048
Settings.chunk_overlap = 20
Settings.llm = OpenAI(model="gpt-4", temperature=0)
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```powershell
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes** and commit
   ```powershell
   git commit -m "Add: your feature description"
   ```
4. **Push to your branch**
   ```powershell
   git push origin feature/your-feature-name
   ```
5. **Open a Pull Request** to the `development` branch

### Development Workflow

- **Development Branch**: Active development and testing
- **Staging Branch**: Pre-production testing
- **Main Branch**: Stable, production-ready code

## 🌿 Branches

This repository follows a three-branch strategy:

- **`main`**: Production-ready, stable code
- **`staging`**: Pre-release testing and validation
- **`development`**: Active development (default branch) ⭐

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **[LlamaIndex](https://www.llamaindex.ai/)** - The framework powering these tutorials
- **OpenAI** - For GPT models and embeddings
- **Jerry Liu** - Original LlamaIndex examples and documentation
- **Uber Technologies, Inc.** - SEC 10-K filings used as sample data

## 📞 Contact

**Mohan Deval**
- GitHub: [@mohandeval](https://github.com/mohandeval)
- Repository: [llama-index-tutorials](https://github.com/mohandeval/llama-index-tutorials)

## 🗺️ Roadmap

- [ ] Add more evaluation metrics (Context Precision, Context Recall)
- [ ] Implement RAG with multiple data sources
- [ ] Add support for local LLMs (Ollama, LlamaCPP)
- [ ] Create production deployment examples
- [ ] Add database integrations (PostgreSQL, MongoDB)
- [ ] Implement advanced query transformations

---

⭐ **Star this repository** if you find it helpful!

📝 **Issues and suggestions** are always welcome!
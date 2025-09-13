# Microsoft GraphRAG Setup Guide (with uv)

This guide explains how to set up and run **Microsoft GraphRAG** on Ubuntu, Windows, or macOS using [uv](https://docs.astral.sh/uv/) as the package manager.

---

## Prerequisites

- Python 3.10 – 3.12
- [uv](https://docs.astral.sh/uv/getting-started/installation/) installed
- OpenAI or Azure OpenAI API key

---

## Installation

### 1. Create a Project Directory

```bash
mkdir graphrag_demo
cd graphrag_demo
````

### 2. Create a Virtual Environment

```bash
uv venv
```

Activate the environment:

**Ubuntu / macOS**

```bash
source .venv/bin/activate
```

**Windows (PowerShell)**

```powershell
.\.venv\Scripts\activate
```

### 3. Install GraphRAG

```bash
uv pip install graphrag
```

---

## Usage

### 1. Prepare Input Data

Create an `input` folder and place text files inside:

```bash
mkdir -p ragtest/input
```

Example (download a sample text):

```bash
curl https://www.gutenberg.org/cache/epub/24022/pg24022.txt -o ragtest/input/book.txt
```

### 2. Initialize a Workspace

```bash
graphrag init --root ragtest
```

This creates:

* `.env` → add your API key here
* `settings.yaml` → adjust models, chunk size, and other settings

### 3. Build the Index

```bash
graphrag index --root ragtest
```

### 4. Run a Query

```bash
graphrag query --root ragtest --method global --query "What are the main themes in this text?"
```

---

## References

* [GraphRAG Documentation](https://microsoft.github.io/graphrag/get_started/)
* [GraphRAG GitHub](https://github.com/microsoft/graphrag)
* [uv Documentation](https://docs.astral.sh/uv/)
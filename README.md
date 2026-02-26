# ChromaDB Local

Local vector storage exploration using [ChromaDB](https://docs.trychroma.com/) and OpenAI embeddings, driven by a Jupyter notebook.

## Prerequisites

- Python 3.12+
- [1Password CLI](https://developer.1password.com/docs/cli/get-started/) (`brew install 1password-cli`)
- 1Password desktop app with **Settings → Developer → Integrate with 1Password CLI** enabled

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Copy the example env file and set your 1Password secret reference pointing to your OpenAI API key:

```bash
cp .env.example .env
```

Edit `.env` and replace the placeholder with your actual `op://vault/item/field` reference.

## Usage

```bash
jupyter notebook main.ipynb
```

The notebook will:

1. Retrieve your OpenAI API key from 1Password via biometric unlock
2. Initialize a persistent ChromaDB client (data stored in `./chroma_data/`)
3. Get or create a vector collection for experimentation

## Project Structure

```
main.ipynb        # Main notebook — all code lives here
.env.example      # Template for 1Password secret reference
chroma_data/      # Persistent ChromaDB storage (gitignored)
requirements.txt  # Python dependencies
```

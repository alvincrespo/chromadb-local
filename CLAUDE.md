# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A Jupyter notebook project exploring local vector storage with ChromaDB and OpenAI embeddings. The main entrypoint is `main.ipynb`. There is no build system, test suite, or linter — this is a notebook-driven exploration project.

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Copy `.env.example` to `.env` and set `OP_SECRET_REF` to your 1Password secret reference (`op://vault/item/field`) pointing to your OpenAI API key.

## Running

```bash
jupyter notebook main.ipynb
```

## Key Dependencies

- **chromadb** — Local persistent vector database (data stored in `./chroma_data/`)
- **openai** — For embeddings
- **python-dotenv** — Loads `OP_SECRET_REF` from `.env`
- **1Password CLI** (`op`) — Retrieves the OpenAI API key at runtime via biometric unlock (requires 1Password desktop app with CLI integration enabled)

## Git Filters

`nbstripout` is configured as a git filter (see `.gitattributes`) to strip notebook outputs before committing. It is installed as a pip dependency via `requirements.txt`.

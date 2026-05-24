# nanoGPT (Wizard of Oz)

A minimal, character-level Generative Pre-trained Transformer (GPT) implementation in PyTorch, inspired by Andrej Karpathy's `nanoGPT` and *Let's build GPT from scratch* lecture. 

This repository trains a decoder-only transformer language model on the full text of *The Wonderful Wizard of Oz* to learn the character patterns, writing style, and structure of the classic book, enabling auto-regressive text generation.

---

## 📂 Repository Structure

*   **`nanoGPT.ipynb`**: Interactive Jupyter Notebook used for initial data exploration, vocabulary analysis, and implementing the character-level tokenizer.
*   **`train.py`**: The training script dedicated to holding the PyTorch model definition (transformer blocks, multi-head attention, positional embeddings) and the main training/validation loop.
*   **`wizard_of_oz.txt`**: The pre-training corpus containing the raw text of *The Wonderful Wizard of Oz*.

---

## 🛠️ Current State & Key Features

Currently, the project has established the foundation for text processing and tokenization inside the Jupyter notebook:

1.  **Dataset Preprocessing**:
    *   Reads and parses the raw text of `wizard_of_oz.txt` with UTF-8 encoding.
    *   Extracts all unique characters to build the model's vocabulary.
2.  **Character-Level Tokenizer**:
    *   Constructs integer-to-string (`int_to_string`) and string-to-integer (`string_to_int`) lookups.
    *   Implements basic `encode` and `decode` routines to map string inputs to integer token sequences and back.

---

## 🚀 Planned Model Architecture

The target architecture is a scaled-down version of GPT-2 containing:
*   **Token & Positional Embeddings**: Map token indices to high-dimensional spaces alongside their positional coordinates.
*   **Multi-Head Causal Self-Attention**: Allow tokens to look back at previous tokens in the sequence without looking forward into the future (using a lower-triangular causal mask).
*   **Feed-Forward Networks (MLP)**: Project attention representations to a higher dimension, apply a non-linearity (e.g., ReLU or GELU), and project back.
*   **Residual Connections & Layer Normalization**: Ensure stable gradient flow during backpropagation across multiple transformer blocks.
*   **Auto-regressive Generation**: Generate new characters one at a time by sampling from the model's output logits.

---

## ⚙️ Getting Started

### Prerequisites
Make sure you have Python 3 and PyTorch installed. You can install PyTorch using:
```bash
pip install torch
```

### Running the Notebook
Open and execute the cells in `nanoGPT.ipynb` to inspect the tokenization process:
```bash
jupyter notebook nanoGPT.ipynb
```

# nanoGPT

A simple character-level language model trained on the Tiny Shakespeare dataset, following Andrej Karpathy's "Let's build GPT" tutorial series.

## Contents

- `bigram.py` — A PyTorch implementation of a bigram language model.
- `nanoGPT.ipynb` — Step-by-step notebook walking through the same model.
- `input.txt` — Training data (Tiny Shakespeare).
- `wizard_of_oz.txt` — Additional text data.

## Requirements

- Python 3.x
- PyTorch

```bash
pip install torch
```

## Usage

Run the bigram model:

```bash
python bigram.py
```

Or open the notebook:

```bash
jupyter notebook nanoGPT.ipynb
```

The model learns to predict the next character given the previous one and generates Shakespeare-like text after training.

# Attention-Based Neural Machine Translation: English to Pig Latin

## Overview
This project implements an attention-based neural machine translation (NMT) model to translate words from English to Pig Latin. The goal is to train a model that learns the rules of Pig Latin implicitly from (English, Pig Latin) word pairs using character-level networks. This project demonstrates the capacity of NMT models to handle translation tasks that involve character rearrangement.

## Pig Latin Translation Rules
1. If the first letter of a word is a consonant, move the letter to the end of the word and add "ay":
    - Example: `team` → `eamtay`
2. If the first letter is a vowel, leave the word unchanged and add "way":
    - Example: `impress` → `impressway`
3. Treat some consonant pairs, such as "sh", as a block and move them to the end together:
    - Example: `shopping` → `oppingshay`

## Data
The dataset consists of pairs of words {(s(i), t(i))} where the source s(i) is an English word, and the target t(i) is its translation in Pig Latin. The dataset is composed of unique words from the book "Sense and Sensibility" by Jane Austen, and consists of 6387 unique (English, Pig Latin) pairs.

## Features
- **Data Preparation**: Pairs of words grouped based on the lengths of the source and target for mini-batch processing.
- **Encoder-Decoder Model**: Utilizes gated recurrent units (GRUs) for encoding and decoding sequences.
- **Attention Mechanism**: Implements scaled dot-product attention to focus on relevant input tokens.
- **Transformer Decoder**: Simplified transformer decoder using layers of attention modules.
- **Attention Visualizations**: Visualizes attention weights to gain insights into model behavior.

## Dependencies
- Python
- Numpy
- Scipy
- PyTorch

## Implementation Details

### 1. Scaled Dot-Product Attention
Implements the scaled dot-product attention mechanism to compute attention weights and context vectors.

### 2. Causal Scaled Dot-Product Attention
Extends scaled dot-product attention to include a causal mask, preventing the model from attending to future time steps.

### 3. Transformer Decoder
Uses layers of attention modules, including self-attention and encoder-decoder attention, to solve the translation problem. Implements residual connections and ReLU activations for improved optimization.

### 4. Training the Model
Trains the attention-based NMT model using character-level sequences from the dataset. Evaluates the model using training and validation loss curves.

### 5. Attention Visualizations
Visualizes the attention weights generated for input tokens at each decoder step to understand where the model focuses while producing each output token.

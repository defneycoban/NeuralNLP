# Neural NLP Projects

## Overview
This repository contains two neural network-based nlp projects: an Attention-Based Neural Machine Translation (NMT) model for translating English to Pig Latin, and a Neural Dependency Parser. Both projects leverage advanced neural network architectures and techniques to perform nlp tasks.

## Projects

### 1. Attention-Based Neural Machine Translation: English to Pig Latin
**Description**: This project implements an attention-based neural machine translation (NMT) model to translate words from English to Pig Latin. The model learns the rules of Pig Latin implicitly from (English, Pig Latin) word pairs using character-level networks.

**Features**:
- Data preparation and tokenization
- Encoder-decoder architecture with GRUs
- Scaled dot-product attention mechanism
- Transformer decoder with self-attention and encoder-decoder attention
- Training and evaluation using loss curves
- Attention visualizations to understand model behavior

### 2. Neural Dependency Parser
**Description**: This project implements a neural-network-based dependency parser aimed at maximizing performance on the Unlabeled Attachment Score (UAS) metric. The parser uses a transition-based approach to build dependency parses incrementally, with a neural network classifier deciding the appropriate transition at each step.

**Features**:
- Transition-based parsing with SHIFT, LEFT-ARC, and RIGHT-ARC transitions
- Neural network classifier for transition prediction
- Minibatch parsing for efficient transition prediction
- Training and evaluation using UAS
- Implementation of scaled dot-product attention for parsing tasks.

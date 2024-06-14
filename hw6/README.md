# Neural Dependency Parser

## Overview
This project implements a neural-network-based dependency parser, aimed at maximizing performance on the Unlabeled Attachment Score (UAS) metric. A dependency parser analyzes the grammatical structure of a sentence, establishing relationships between head words and their modifiers. This implementation uses a transition-based parser that incrementally builds a parse one step at a time, utilizing a neural network classifier to decide the appropriate transition at each step.

## Features
- **Transition-Based Parsing**: Utilizes a stack, buffer, and list of dependencies to build partial parses.
- **Neural Network Classifier**: Trained to predict the next transition for a given parse state.
- **Minibatch Parsing**: Implements efficient parsing by predicting transitions for multiple sentences simultaneously.
- **Evaluation Metrics**: Uses the Unlabeled Attachment Score (UAS) to measure parsing accuracy.

## Dependencies
- Python
- Numpy
- Scipy
- PyTorch

## Implementation Details

### 1. Transition-Based Parsing
The parser applies the following transitions to build dependency parses:
- **SHIFT**: Removes the first word from the buffer and pushes it onto the stack.
- **LEFT-ARC**: Marks the second item on the stack as a dependent of the first item and removes the second item from the stack.
- **RIGHT-ARC**: Marks the first item on the stack as a dependent of the second item and removes the first item from the stack.

### 2. Neural Network Classifier
The neural network classifier is trained to predict the next transition based on the current state of the stack, buffer, and dependencies:
- **Input Features**: Extracted from the current parse state.
- **Embedding Layer**: Looks up embeddings for each feature.
- **Hidden Layer**: Applies a ReLU activation function.
- **Output Layer**: Uses a softmax function to predict the next transition.

### 3. Minibatch Parsing
Implements a minibatch parsing algorithm for efficient transition prediction:
- Processes multiple sentences simultaneously.
- Updates partial parses based on predicted transitions.
- Continues until all sentences are fully parsed.

### 4. Training and Evaluation
The model is trained using the Penn Treebank dataset annotated with Universal Dependencies:
- **Training**: Trains the model to minimize cross-entropy loss.
- **Evaluation**: Measures parsing accuracy using the Unlabeled Attachment Score (UAS).

## Usage
1. **Clone the Repository**:
    ```sh
    git clone <repository-url>
    cd neural-dependency-parser
    ```
2. **Install Dependencies**:
    ```sh
    pip install -r requirements.txt
    ```
3. **Train the Model**:
    ```sh
    python run.py
    ```
4. **Evaluate the Model**:
    ```sh
    python run.py --evaluate
    ```

## Results
The neural dependency parser achieves high accuracy on the parsing task, demonstrating the effectiveness of neural networks for dependency parsing. The model's performance can be further improved by fine-tuning hyperparameters such as hidden layer size, learning rate, and number of epochs.

## Conclusion
This project provides a comprehensive implementation of a neural-network-based dependency parser. By leveraging transition-based parsing and neural network classifiers, the parser achieves high accuracy in identifying grammatical relationships within sentences.

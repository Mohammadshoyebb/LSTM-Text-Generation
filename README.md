# LSTM Text Generation

This repository demonstrates the implementation of an LSTM (Long Short-Term Memory) model for text generation using TensorFlow and Keras. Below is a detailed breakdown of the implementation:

## Overview

### 1. Dataset Preparation

The text data used for training is sourced from Nietzsche's writings, which is downloaded and processed. The corpus is converted to lowercase for uniformity.

### 2. Sequence Generation

Sequences of fixed length (`maxlen`) are generated from the text data with a step size of 3. Each sequence serves as input (`x`) to predict the next character (`y`). This prepares the data for training the LSTM model.

### 3. Data Vectorization

Characters in the sequences are one-hot encoded into binary arrays (`x`) suitable for LSTM input. The output (`y`) is also one-hot encoded representing the next character prediction task.

### 4. Model Definition

The LSTM model is defined using TensorFlow's Keras API:
- An LSTM layer with 128 units processes the input sequences.
- A Dense layer with softmax activation predicts the probability distribution over characters.

### 5. Model Compilation

The model is compiled with categorical crossentropy loss and RMSprop optimizer.

### 6. Text Generation Loop

A loop runs for a specified number of epochs (`NUM_EPOCHS`), during which:
- The model is trained for one epoch on the training data (`x`, `y`).
- A random seed text is selected from the corpus.
- Text generation is performed at different temperatures (0.2, 0.5, 1.0, 1.2) to control the randomness of predictions.

## Conclusion

This README.md provides an overview of implementing an LSTM model for text generation using TensorFlow and Keras. It covers dataset preparation, sequence generation, data vectorization, model definition, training, and text generation. The provided implementation serves as an introduction to using LSTMs for generating text based on learned patterns from existing text data.

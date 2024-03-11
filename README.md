# Make More: Character-Level Language Model for Name Generation

## Project Overview

This is my implementation of a character-level language model designed to generate unique, name-like strings. I implemented this with the help of [Andrej Karpathy's makemore series on YouTube](https://www.youtube.com/watch?v=PaCmpygFfXo&ab_channel=AndrejKarpathy).
Using a dataset comprising approximately 32,000 names sourced from public domains, the model learns the statistical structure of character sequences to create new, plausible names.

## How It Works

Make More employs a bi-gram character-level model, treating each name in the dataset as a sequence of character-level examples. The model predicts the likelihood of each character following the preceding one, based on the statistical patterns learned from the training data.

### Model Training

The training process involves:

1. Reading and preprocessing the names from `names.txt`.
2. Breaking down each name into sequences of characters and constructing bi-grams (pairs of consecutive characters).
3. Counting the occurrences of each bi-gram across the dataset to construct a frequency matrix.
4. Normalizing these counts to convert them into probabilities that reflect how likely a character is to follow another.

### Name Generation

Once trained, the model generates names by:

1. Starting with an initial character or a sequence of characters.
2. Using the model to predict the next character based on the probabilities learned during training.
3. Repeating this process, appending each new character to form a complete name until a stopping condition (such as reaching a maximum length or encountering an end-of-sequence marker) is met.
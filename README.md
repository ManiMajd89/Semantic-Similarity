# Semantic-Similarity
This Python script builds semantic descriptors from text files and evaluates the semantic similarity between words using cosine similarity. It includes functions to preprocess text, construct word context vectors, and compare words for similarity. Additionally, it allows testing word association accuracy against a test dataset. The script is a powerful tool for exploring semantic relationships in natural language processing tasks.

Authors: Mani Majd , Eric Huang

Credits: ESC180 project 3

## Features

### Core Functionality
- **Semantic Descriptor Construction**:
  - Builds semantic descriptor vectors for words based on their co-occurrence in sentences.
  - Handles large text files and constructs vectors efficiently using dictionaries.
- **Cosine Similarity Calculation**:
  - Measures the closeness of meanings between two words using vector similarity.
  - Accounts for sparse vectors by focusing on non-zero entries.
- **Synonym Prediction**:
  - Predicts the synonym with the highest semantic similarity for a given word.
- **TOEFL Synonym Test Evaluation**:
  - Evaluates system accuracy by comparing predictions against correct answers in a test file.

---

## How It Works

### Semantic Descriptor
A **semantic descriptor** vector represents the context of a word based on its co-occurrence with other words in sentences. For example:
- Given the text: I am a sick man. I am a spiteful man. I am an unattractive man.
- The semantic descriptor for `"man"` is:
{"i": 3, "am": 3, "a": 2, "sick": 1, "spiteful": 1, "an": 1, "unattractive": 1}

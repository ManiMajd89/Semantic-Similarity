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
```python
{"i": 3, "am": 3, "a": 2, "sick": 1, "spiteful": 1, "an": 1, "unattractive": 1}

Cosine Similarity

The semantic similarity between two words is calculated using cosine similarity, which measures how similar two vectors are by finding the cosine of the angle between them.

Formula

[
\text{sim}(u, v) = \frac{u \cdot v}{|u| |v|}
]

Where:
	•	( u \cdot v ): Dot product of ( u ) and ( v ).
	•	( |u| ): Magnitude (length) of vector ( u ).
	•	( |v| ): Magnitude (length) of vector ( v ).

Simplified Calculation

With semantic descriptors (stored as dictionaries):
	•	( u \cdot v ): Sum of the products of shared keys.
	•	( |u| ): Square root of the sum of squares of the values in ( u ).
	•	( |v| ): Square root of the sum of squares of the values in ( v ).


## Workflow

Step 1: Preprocess Text
	•	Input: A corpus of text files.
	•	Process:
	1.	Split the text into sentences.
	2.	Remove punctuation and convert words to lowercase.
	3.	Tokenize each sentence into words.

Step 2: Build Semantic Descriptors
	•	Count co-occurrences of words within sentences.
	•	Create a dictionary for each word where:
	•	Keys: Words co-occurring in the same sentence.
	•	Values: Count of co-occurrences.

Step 3: Compute Cosine Similarity
	•	Compare the vectors of two words:
	•	The given word.
	•	Each potential synonym.

Step 4: Select the Best Match
	•	For a given word ( w ) and a list of choices ([s_1, s_2, s_3, s_4]):
	•	Calculate ( \text{sim}(w, s_i) ) for each ( s_i ).
	•	Choose the synonym ( s_i ) with the highest similarity.

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

## Core Functions:
1. norm(vec):
   - Computes the Euclidean norm of a vector.

2. cosine_similarity(vec1, vec2):
   - Calculates the cosine similarity between two word vectors.

3. build_semantic_descriptors(sentences):
   - Constructs semantic descriptors from tokenized sentences by tracking word co-occurrences.

4. build_semantic_descriptors_from_files(filenames):
   - Reads and preprocesses text from input files, then calls build_semantic_descriptors to generate
     descriptors.

5. most_similar_word(word, choices, semantic_descriptors, similarity_fn):
   - Finds the word most similar to the input word from a list of choices.

6. run_similarity_test(filename, semantic_descriptors, similarity_fn):
   - Runs a similarity test by comparing the most similar word predictions to the expected results
     in the input test file.

## Usage:
1. Ensure you have the required text files and test datasets.
2. Uncomment the main function and specify filenames as needed:
    filename = "test.txt"
   
    semantic_descriptors = build_semantic_descriptors_from_files(["war_and_peace.txt", "swanns_way.txt"])
   
    print(run_similarity_test(filename, semantic_descriptors, cosine_similarity))

Example Input:

- Training Text Files: Large text files such as war_and_peace.txt and swanns_way.txt.
  
- Test Dataset: A file like test.txt with the format:
    word1 correct_choice choice1 choice2 choice3

Example Output:

Accuracy: 85.0%

## Installation:
1. Clone the repository:
   
    git clone https://github.com/<your-username>/semantic-similarity-analyzer.git
   
3. Navigate to the project directory:
   
    cd semantic-similarity-analyzer
   
5. Ensure Python is installed (version 3.7+ recommended).
   
7. Install required packages (if any).

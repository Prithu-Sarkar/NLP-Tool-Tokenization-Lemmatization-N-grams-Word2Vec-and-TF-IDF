Core NLP Text Processing and Feature Extraction Techniques

This document provides a concept-focused explanation of Tokenizer, Lemmatizer, N-grams, Word2Vec, and TF-IDF, including their types and examples, presented in a structured and comparative format for easy understanding and revision.

| Aspect           | Description                                                                      |
| ---------------- | -------------------------------------------------------------------------------- |
| **Definition**   | Splits text into smaller units called **tokens** (words, subwords, or sentences) |
| **Purpose**      | Converts raw text into machine-readable units                                    |
| **Types**        | Word Tokenizer, Sentence Tokenizer, Subword Tokenizer                            |
| **Example Text** | “NLP is interesting”                                                             |
| **Output**       | `["NLP", "is", "interesting"]`                                                   |
| **Used In**      | All NLP pipelines                                                                |

2. Lemmatizer

| Aspect                       | Description                                                   |
| ---------------------------- | ------------------------------------------------------------- |
| **Definition**               | Converts words into their dictionary or base form (**lemma**) |
| **Purpose**                  | Reduces inflectional forms while preserving semantic meaning  |
| **Depends On**               | Part-of-Speech (POS) tagging                                  |
| **Example Words**            | running, better, cars                                         |
| **Output**                   | run, good, car                                                |
| **Difference from Stemming** | Lemmatization produces real words; stemming may not           |


3. N-grams

| Aspect               | Description                                      |
| -------------------- | ------------------------------------------------ |
| **Definition**       | Continuous sequence of **N words or characters** |
| **Purpose**          | Captures context and word order                  |
| **Types**            | Unigram, Bigram, Trigram                         |
| **Example Sentence** | “I love football”                                |

| Type        | Output                 |
| ----------- | ---------------------- |
| **Unigram** | I / love / football    |
| **Bigram**  | I love / love football |
| **Trigram** | I love football        |

4. Word2Vec

| Aspect          | Description                                       |
| --------------- | ------------------------------------------------- |
| **Definition**  | Converts words into **dense numerical vectors**   |
| **Purpose**     | Captures semantic meaning and similarity          |
| **Output Type** | Vector (e.g., 300-dimensional)                    |
| **Key Idea**    | Similar words have similar vector representations |
| **Example**     | king − man + woman ≈ queen                        |
| **Advantage**   | Captures meaning rather than just word frequency  |


Word2Vec Types
| Type          | Explanation                                     | Example        |
| ------------- | ----------------------------------------------- | -------------- |
| **CBOW**      | Predicts target word from surrounding context   | context → word |
| **Skip-Gram** | Predicts surrounding context from a target word | word → context |


5. TF-IDF (Term Frequency–Inverse Document Frequency)

| Component                            | Meaning                                         |
| ------------------------------------ | ----------------------------------------------- |
| **TF (Term Frequency)**              | How often a word appears in a document          |
| **IDF (Inverse Document Frequency)** | How rare a word is across all documents         |
| **TF-IDF**                           | Measures the importance of a word in a document |

| Type       | Formula Idea                                     | Example                    |
| ---------- | ------------------------------------------------ | -------------------------- |
| **TF**     | Term count / total words                         | football appears 3 times   |
| **IDF**    | log(total documents / documents containing term) | Rare word → higher value   |
| **TF-IDF** | TF × IDF                                         | Common + rare → high score |


Example Dataset

Documents

D1: football football match

D2: football match

D3: cricket match

| Word     | TF (D1) | IDF    | TF-IDF |
| -------- | ------- | ------ | ------ |
| football | High    | Medium | High   |
| match    | Medium  | Low    | Low    |
| cricket  | Low     | High   | Medium |

6. Combined Comparison Summary

| Technique  | Output Type    | Captures Meaning | Uses Frequency | Order Sensitive |
| ---------- | -------------- | ---------------- | -------------- | --------------- |
| Tokenizer  | Tokens         | No               | No             | No              |
| Lemmatizer | Base words     | Yes              | No             | No              |
| N-grams    | Word sequences | Partial          | Yes            | Yes             |
| Word2Vec   | Dense vectors  | Yes              | No             | Partial         |
| TF-IDF     | Sparse vectors | No               | Yes            | No              |

7. Practical NLP Pipeline Flow

| Step              | Technique  |
| ----------------- | ---------- |
| Text Cleaning     | Tokenizer  |
| Normalization     | Lemmatizer |
| Context Capture   | N-grams    |
| Semantic Meaning  | Word2Vec   |
| Feature Weighting | TF-IDF     |



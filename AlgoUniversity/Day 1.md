# AI Bootcamp – Day 1 Notes

## 1. Core Definitions

| Term | Meaning |
|---|---|
| **Artificial Intelligence (AI)** | Mimics human cognitive functions (thinking, learning, reasoning). The broadest umbrella term. |
| **Machine Learning (ML)** | A subset of AI that predicts outcomes by finding patterns in data. |
| **Deep Learning (DL)** | A subset of ML using neural networks (inspired by the brain) to solve more complex problems that simple ML struggles with. |
| **Data Science** | Using AI/ML techniques to solve real-world problems using data. |

**Hierarchy:** `AI ⊃ ML ⊃ DL`, with Data Science as the applied practice of using these tools on real data.

---

## 2. Why AI? Who Uses It?

- AI is used across research, business operations, and large-scale events.
- Widely adopted by major companies (e.g., **Amazon**) for tasks like recommendations, logistics, forecasting, etc.
- **"Food of AI" = Data.** AI/ML models need data to learn — without data, there's nothing to train on.

---

## 3. What Does AI/ML Actually Do?

- It **understands patterns** hidden in data.
- It works on data to **identify structure/relationships** that aren't obvious to a human at a glance.

### Without AI — the old way (rule-based code)
```
if age > 18 and degree == "BTech":
    hire = True
```
**Problem:** This works for a few simple rules, but it doesn't scale.
- Real-world data has thousands of variables and exceptions.
- Writing manual `if-else` rules for "Big Data" becomes a **"big problem"** — too complex and rigid.

**AI's advantage:** Instead of hand-writing rules, AI *learns* the patterns directly from data.

---

## 4. Understanding a "Model"

**Flow:** `Input → Model → Output`

- A **model** = a collection of **parameters** (numbers), often represented mathematically (e.g., using **λ / weights**).
- The model takes an input, and using knowledge gained from past data, predicts an output.

### What is "Training"?
- Training = the process of **learning the right parameters** from historical/past data.
- **Parameters ≈ Knowledge.** You can loosely think of parameters like **neurons** — each one holds a small piece of learned information.
- Once trained, the model can generalize this learned knowledge to make predictions on **new, unseen data**.

### Why Matrices in AI?
- Data, weights, and computations are represented as **matrices** (grids of numbers).
- Matrix operations allow massive amounts of computation to be done **in parallel**, which is much **faster** than doing calculations one at a time — critical for AI at scale.

---

## 5. Types of Learning in ML

| Type | Description |
|---|---|
| **Supervised Learning** | We have the **answers** (labels) along with the data. The model learns the mapping between input patterns and known output labels. |
| **Unsupervised Learning** | We do **not** have answers/labels. The model must find hidden structure or groupings in the data on its own. |

---

## 6. NLP (Natural Language Processing)

Key concepts introduced:

- **Tokenization**: Breaking text into smaller units (words/sub-words), then converting them into **tokens**.
  - Each word/token can be **mapped to an integer** (a numeric ID) so the model can process it mathematically.
- **Vectors**: Numeric representations of words/tokens (embeddings) that capture meaning.
- **Stemming**: Reducing words to their root/base form (e.g., "running" → "run").
- **Skip-gram**: A technique (used in Word2Vec) to learn word vectors by predicting surrounding words from a given word.
- **Transformers**: The modern architecture (attention-based) that powers most current NLP/LLMs — replaced older sequence models for handling context better.

---

## 7. Other Topics Mentioned (to expand later)

- **Multimedia AI**: AI applied beyond text — images, audio, video.
- **RAG (Retrieval-Augmented Generation)**: A technique where a model retrieves relevant external information/documents before generating a response, improving accuracy and reducing hallucination.

---

## Quick Recap Summary
- **AI** = mimicking human intelligence
- **ML** = pattern-based prediction
- **DL** = neural networks for complex problems
- **Data Science** = applying AI/ML to solve real-world problems
- **Model** = input → parameters (learned knowledge) → output
- **Training** = learning parameters from past data
- **Supervised** = labeled data | **Unsupervised** = unlabeled data
- **NLP basics** = tokenization → vectors → transformers

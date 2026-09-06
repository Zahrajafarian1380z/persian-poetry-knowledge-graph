# Persian Poetry Knowledge Graph

A demo system for extracting key concepts from Persian poetry and analyzing their semantic and structural relationships using a multilayer network approach.

## 📌 Overview

This project presents a computational approach to the analysis of Persian poetry by combining statistical keyword extraction, semantic representations, and network analysis.

The system receives Persian poetry as direct text input or a `.txt` file and identifies important keywords based on a composite scoring method. The extracted concepts are then represented through a multilayer semantic network.

The system also provides an optional literary-style analysis based on predefined stylistic vocabulary associated with four major Persian literary styles:

- Iraqi Style (سبک عراقی)
- Khorasani Style (سبک خراسانی)
- Indian Style (سبک هندی)
- Contemporary Poetry (شعر معاصر)

## 🔬 Methodology

The extraction pipeline combines three main components:

### 1. TF-IDF

TF-IDF is used to measure the statistical importance of words within the input poetry.

### 2. Co-occurrence Network

A word co-occurrence graph is constructed to identify structural relationships between words that frequently appear near each other.

PageRank is then applied to identify structurally important concepts.

### 3. ParsBERT Semantic Representation

The system uses the Persian language model **ParsBERT** to generate contextual word representations.

Cosine similarity is calculated between word embeddings to identify semantic relationships between extracted concepts.

PageRank is subsequently applied to the semantic network.

### 4. Composite Ranking

The final importance score of each candidate keyword is calculated by combining:

- TF-IDF score: 30%
- Co-occurrence PageRank: 35%
- ParsBERT semantic PageRank: 35%

A style-based modifier is also applied according to the selected literary style.

## 🧠 Technologies

- Python
- ParsBERT
- Hugging Face Transformers
- PyTorch
- TF-IDF
- NetworkX
- PageRank
- Scikit-learn
- Pandas
- Matplotlib
- Gradio

## 📊 Output

The system provides two main outputs:

1. A ranked table of extracted keywords and their scores
2. A visual network representing the relationship between the selected literary style, extracted concepts, and their importance scores

Users can also determine the number of keywords displayed in the final result.

## 🚀 Running the Demo

Install the required dependencies:

```bash
pip install -r requirements.txt

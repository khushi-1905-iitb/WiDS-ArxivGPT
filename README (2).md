# ArxivGPT: Build a Research Assistant on Your Own Vector Search Engine
**WiDS 6.0 · 6 weeks · Mentor: Khushi Bansal (IIT Bombay)**

Over six weeks you will build a working AI search engine from scratch. You will start by turning text into vectors (embeddings), write your own vector index, benchmark it against production libraries (FAISS, HNSW), and finally put an LLM on top to answer questions with citations to real arXiv papers.

Everything runs on **free Google Colab**. No GPU or paid API is needed.

---

## Roadmap

| Week | Topic | Deliverable |
|---|---|---|
| 1 | Embeddings: turning meaning into vectors | Notebook: "find similar papers" with cosine similarity |
| 2 | Brute-force nearest-neighbour search | Your own `search()` function + speed-vs-data-size plot |
| 3 | IVF: your first vector index (k-means based) | Your own IVF index + recall-vs-speed plot |
| 4 | Production indexes: FAISS and HNSW | Benchmark table: recall, latency, memory |
| 5 | Retrieval-Augmented Generation (RAG) | LLM that answers questions with citations |
| 6 | App + evaluation | Gradio demo + short report + presentation |

---

## Week 1: Embeddings

### Goal
Understand what an embedding is, why similar meanings end up close together, and how to measure "closeness".

### Learn (≈3 hours)
1. **Python + NumPy refresher**: NumPy quickstart — https://numpy.org/doc/stable/user/quickstart.html
2. **Vectors, dot product, cosine similarity**: 3Blue1Brown, *Essence of Linear Algebra*, chapters 1 and 9 (YouTube)
3. **What are embeddings?**: Google ML Crash Course, Embeddings — https://developers.google.com/machine-learning/crash-course/embeddings
4. **Word vectors, intuitively**: Jay Alammar, *The Illustrated Word2vec* — https://jalammar.github.io/illustrated-word2vec/
5. **Vector embeddings in practice**: Pinecone Learn — https://www.pinecone.io/learn/vector-embeddings/
6. **Sentence embeddings library**: Sentence-Transformers quickstart — https://www.sbert.net/docs/quickstart.html

### Dataset
arXiv metadata (titles + abstracts) on Kaggle — https://www.kaggle.com/datasets/Cornell-University/arxiv
Use a **subset of 20,000 abstracts** this week; we will scale up to ~100k later.

### Assignment
In a Colab notebook:
1. Load 20k arXiv abstracts (title + abstract + category).
2. Embed them with the `all-MiniLM-L6-v2` model from sentence-transformers.
3. Write your own `cosine_similarity(a, b)` in NumPy and check it against `sklearn`.
4. Write `most_similar(query_text, k=5)` that returns the 5 closest papers to any text you type.
5. **Explore:** try 5 different queries. When do the results make sense? When do they fail?
6. **Visualise:** project 2,000 embeddings to 2D with PCA (or UMAP), colour by arXiv category, and describe what you see.

### Submit
Your notebook + a short write-up (half a page) answering:
- What does "close" mean for two embeddings?
- One query where search worked well, and one where it failed. Why?

---

*Resources for Weeks 2–6 will be added before each week begins.*


```markdown
# 🧠 Pinecone Vector Database with Hugging Face Embeddings

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github.com/your-username/pinecone-vector-db-tutorial/blob/main/Pincone_draft.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Embeddings-orange)](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2)
[![Pinecone](https://img.shields.io/badge/Pinecone-Vector%20DB-green)](https://www.pinecone.io/)

---

## 📌 Overview

A **beginner-friendly** tutorial that demonstrates how to build a production-ready vector database using:

- 🔤 **Hugging Face Embeddings** (`all-MiniLM-L6-v2`)
- 🗄️ **Pinecone Vector Database** (cloud-hosted)
- 📄 **PDF Text Extraction** (using `pypdf`)
- 🔍 **Semantic Similarity Search** foundation

This notebook is perfect for anyone starting with **Retrieval-Augmented Generation (RAG)** systems.

---

## ✨ What You'll Learn

| # | Topic | Description |
|---|-------|-------------|
| 1 | **Text Embeddings** | Convert text into 384-dimensional numerical vectors |
| 2 | **Semantic Similarity** | Measure how similar two texts are using cosine similarity |
| 3 | **Pinecone Setup** | Create and manage a cloud-based vector database |
| 4 | **Vector Storage** | Upload embeddings with metadata to Pinecone |
| 5 | **Data Retrieval** | Foundation for fast semantic search |

### Architecture Overview
```
Text → Hugging Face Embedding Model → Vector → Pinecone Database → Semantic Search → Most Relevant Text
```

---

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/pinecone-vector-db-tutorial.git
cd pinecone-vector-db-tutorial
```

### 2. Open in Google Colab
Click the **Open In Colab** badge above, or upload the notebook manually.

### 3. Add Your Pinecone API Key (🔐 SECURE)

#### **Option A: Google Colab Secrets (Recommended)**
1. In Colab, click the **🔑 Secrets** icon in the left sidebar
2. Add a new secret named `PINECONE_API_KEY`
3. Paste your Pinecone API key as the value
4. Run the notebook

#### **Option B: Environment Variables (Local)**
```bash
# Create .env file
echo "PINECONE_API_KEY=your-api-key-here" > .env

# Add .env to .gitignore (IMPORTANT!)
echo ".env" >> .gitignore
```

> ⚠️ **Never hardcode your API key in the notebook!** Your key is already secured in this repository.

---

## 📖 Notebook Structure

```
┌─────────────────────────────────────────────────────┐
│ 📝 Title & Architecture Overview                   │
├─────────────────────────────────────────────────────┤
│ 📦 Install Required Libraries                      │
│     - sentence-transformers                        │
│     - pinecone                                     │
│     - pypdf                                        │
├─────────────────────────────────────────────────────┤
│ 📚 Import Libraries                                │
├─────────────────────────────────────────────────────┤
│ 🔤 Load Hugging Face Embedding Model               │
│     Model: all-MiniLM-L6-v2 (384-dim)              │
├─────────────────────────────────────────────────────┤
│ 🧪 Test: First Embedding Generation                │
├─────────────────────────────────────────────────────┤
│ 📊 Calculate Semantic Similarity                   │
│     → Score: 0.877 (Very Similar)                  │
├─────────────────────────────────────────────────────┤
│ 🔐 Connect to Pinecone (Secure)                    │
├─────────────────────────────────────────────────────┤
│ 🗄️ Create / Connect to Pinecone Index              │
│     Name: student-vector-db                        │
│     Dimension: 384                                 │
│     Metric: cosine                                 │
├─────────────────────────────────────────────────────┤
│ 📄 Create Sample Documents (5 AI/ML topics)        │
├─────────────────────────────────────────────────────┤
│ 🔢 Convert Documents → Embeddings                  │
│     Shape: (5, 384)                                │
├─────────────────────────────────────────────────────┤
│ 📦 Prepare Records for Upload                      │
│     Format: id, values, metadata                   │
├─────────────────────────────────────────────────────┤
│ ⬆️ Upload Vectors to Pinecone                      │
│     ✅ Successfully uploaded!                      │
├─────────────────────────────────────────────────────┤
│ ✅ Summary & Next Steps                            │
└─────────────────────────────────────────────────────┘
```

---

## 🛠️ Installation (Local)

If running locally instead of Colab:

```bash
# Install dependencies
pip install -q -U sentence-transformers pinecone pypdf scikit-learn

# Run the notebook
jupyter notebook Pincone_draft.ipynb
```

---

## 🔒 Security Best Practices

| ✅ DO | ❌ DON'T |
|-------|----------|
| Use Colab Secrets for API keys | Hardcode API keys in code |
| Add `.env` to `.gitignore` | Commit `.env` files |
| Clear cell outputs before committing | Leave sensitive outputs |
| Use environment variables | Print tokens or keys |

**Your notebook already follows these practices!**

---

## 📊 Sample Outputs

### Embedding Generation
```python
Input: "Python is a programming language"
Output: [-3.53708379e-02, 3.81649956e-02, ...] # 384 numbers
```

### Similarity Score
```
Sentence 1: "I love programming in Python."
Sentence 2: "Python is my favorite programming language."
Similarity: 0.8776
```

### Pinecone Upload
```
✅ Connected to Pinecone successfully!
✅ Pinecone index already exists.
✅ Vectors uploaded to Pinecone successfully!
```

---

## 📁 Repository Structure

```
pinecone-vector-db-tutorial/
├── Pincone_draft.ipynb          # Main tutorial notebook
├── README.md                    # This file
├── LICENSE                      # MIT License
├── .gitignore                   # Ignore secrets and cache
└── requirements.txt             # Python dependencies
```

---

## 📦 Dependencies

```txt
sentence-transformers>=2.2.0
pinecone>=5.0.0
pypdf>=3.0.0
scikit-learn>=1.0.0
numpy>=1.24.0
```

---

## 🚀 What's Next?

After completing this tutorial, you can:

| Feature | Difficulty | Description |
|---------|------------|-------------|
| **Semantic Search** | ⭐ Easy | Query the database with natural language |
| **PDF Processing** | ⭐⭐ Medium | Extract and embed entire documents |
| **Full RAG System** | ⭐⭐⭐ Advanced | Combine with LLM for Q&A |
| **Document Chunking** | ⭐⭐ Medium | Split long documents effectively |
| **Hybrid Search** | ⭐⭐⭐ Advanced | Combine keyword + vector search |

---

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

---

## 📄 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- **[Hugging Face](https://huggingface.co/)** – For `sentence-transformers` and embedding models
- **[Pinecone](https://www.pinecone.io/)** – For the vector database service
- **[Google Colab](https://colab.research.google.com/)** – For free GPU/CPU resources

---

## ⭐ Show Your Support

If this tutorial helped you:
- ⭐ Star the repository
- 🍴 Fork it
- 🐦 Share it on social media

---

**Made with ❤️ by yashfa waseem**

---

## 📝 Quick Commands Reference

```python
# Load embedding model
from sentence_transformers import SentenceTransformer
model = SentenceTransformer("sentence-transformers/all-MiniLM-L6-v2")

# Generate embedding
embedding = model.encode("Your text", convert_to_numpy=True)

# Connect to Pinecone
from pinecone import Pinecone
pc = Pinecone(api_key=PINECONE_API_KEY)
index = pc.Index("your-index-name")

# Upload vectors
index.upsert(vectors=records)

# Query (add this in your next step!)
results = index.query(vector=query_vector, top_k=3)
```

```

---

## 🎯 **Final Steps Before Pushing**

```bash
# 1. Clear notebook outputs
jupyter nbconvert --clear-output --inplace Pincone_draft.ipynb

# 2. Create .gitignore
cat > .gitignore << EOF
.env
*.env
.ipynb_checkpoints/
__pycache__/
*.pyc
.cache/
.DS_Store
EOF

# 3. Initialize git
git init
git add .
git commit -m "Add Pinecone vector database tutorial with HF embeddings"

# 4. Create repo on GitHub and push
git remote add origin https://github.com/your-username/pinecone-vector-db-tutorial.git
git branch -M main
git push -u origin main
```

---

# 🎬 Movie Recommendation System (MRS)

A hybrid **Movie Recommendation System** built using **Streamlit**, **scikit-surprise (SVD)**, and **TF-IDF content similarity**.  
This dashboard allows users to explore personalized movie recommendations powered by both **content-based** and **collaborative filtering** models.

---

## 🚀 Features
- 🎥 **Hybrid Recommendation Engine** combining:
  - **Collaborative Filtering (SVD)** for personalized suggestions.
  - **Content-Based Filtering (TF-IDF)** for similar movies.
- 🧠 Interactive **Streamlit Dashboard** for visualization.
- 📊 Caching using Streamlit for efficient performance.
- 🖼️ Poster fetching using **OMDb** and **TMDb APIs**.
- 🧾 Environment management via `.env` file.

---

## 🧩 Tech Stack

| Component | Library |
|------------|----------|
| UI Dashboard | Streamlit |
| Machine Learning | Scikit-Surprise (SVD), Scikit-learn |
| Data Handling | Pandas, NumPy |
| API Requests | Requests |
| Caching & Env | Streamlit Cache, python-dotenv |
| Image Handling | Pillow (PIL) |

---

## 📂 Folder Structure

```
MRS_DS&ML/
├── app.py
├── data/
│   └── clean/
│       ├── movies.csv
│       ├── ratings.csv
├── src/
│   └── models/
│       ├── svd_model.pkl
│       ├── tfidf_vectorizer.pkl
│       ├── tfidf_matrix.npz
│       └── movie_idx_map.pkl
├── assets/
│   ├── placeholder.png
│   └── posters/
├── .env
├── requirements.txt
└── README.md
```

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/movie-recommendation-system.git
cd movie-recommendation-system
```

### 2️⃣ Create Virtual Environment
```bash
conda create -n surprise_env python=3.10
conda activate surprise_env
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ Add Your API Keys
Create a `.env` file in the project root with the following:

```
OMDB_API_KEY=your_omdb_api_key
TMDB_API_KEY=your_tmdb_api_key
HYBRID_ALPHA=0.7
```

---

## ▶️ Run the App
```bash
streamlit run app.py
```

Then open your browser at:  
👉 **http://localhost:8501/**

---

## 🧮 Model Details

### Content-Based Model
- Uses TF-IDF vectorization on movie genres and tags.
- Computes similarity with **cosine similarity**.

### Collaborative Filtering Model
- Based on **SVD (Singular Value Decomposition)**.
- Trained on user ratings from `ratings.csv`.

### Hybrid Model
- Combines both models:
  - Final score = α * Collaborative + (1 - α) * Content
  - `HYBRID_ALPHA` is configurable in `.env`.

---

## 🖼️ Poster Fetching

Posters are fetched automatically using:
- **OMDb API** (primary source)
- **TMDb API** (fallback)
- Local caching for improved speed

---

## 🧠 Example Usage

```python
print("Content-Based Recommendations for 'Toy Story (1995)':")
print(recommend_content(1, top_n=10))
```

Or explore interactively via the **Streamlit dashboard**.

---



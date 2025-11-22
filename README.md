# 🎬 Movie Recommender System

A content-based movie recommender system that suggests movies similar to a user's selection. It analyzes movie content (plot, genre, cast, and crew) using Natural Language Processing (NLP) and Machine Learning to generate recommendations.

![Image](https://github.com/user-attachments/assets/19fc01d2-c1dd-4dbf-b25e-e9f2f0649614)


## 🚀 Overview

This project implements a **Content-Based Filtering** system. Unlike collaborative filtering (which relies on user ratings), this system recommends items based on the similarity of item attributes.

The model processes the TMDB 5000 Movie Dataset, vectorizes the text data, and calculates cosine similarity to find the nearest neighbors for a given movie.

## ✨ Key Features

* **Data Preprocessing:** Cleans and structures raw data (handling JSON columns for Genres, Keywords, Cast, and Crew).
* **Feature Engineering:** Combines movie overviews, genres, keywords, top 3 actors, and directors into a unified "tags" column.
* **NLP Pipeline:**
    * **Stemming:** Uses NLTK's `PorterStemmer` to reduce words to their root form.
    * **Vectorization:** Uses Scikit-Learn's `CountVectorizer` to convert text tags into numerical vectors (5000 features).
* **Similarity Metric:** Calculates **Cosine Similarity** to measure the angle between movie vectors.
* **Interactive Web App:** Built with **Streamlit** to display movie posters and titles dynamically.

## 🛠️ Tech Stack

* **Language:** Python
* **Web Framework:** Streamlit
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (CountVectorizer, Cosine Similarity)
* **NLP:** NLTK (PorterStemmer)
* **API:** The Movie Database (TMDB) API (for fetching posters)

## ⚙️ Project Workflow

1.  **Data Ingestion:** Merging `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`.
2.  **Preprocessing:** extracting relevant information from JSON columns using `ast.literal_eval`.
3.  **Model Building:**
    * Constructing the `tags` for every movie.
    * Vectorizing the tags.
    * Calculating the similarity matrix.
4.  **Deployment:** The model and data are serialized using `pickle` (`movie_dict.pkl`, `similarity.pkl`) and loaded into the Streamlit app.

## 🔧 How to Run Locally

### 1. Clone the Repository
```bash
git clone https://github.com/bhumikafulari/movie-recommender-system.git
```

### 2. Install Dependencies
Create a requirements.txt file (or install manually):
```bash
pip install streamlit pandas numpy scikit-learn nltk requests
```

### 3. Setup API Key (Crucial Step)
The app fetches movie posters from TMDB. You need an API key.

1) Get a free API Key from TMDB  

2) Inside your project folder, create a folder named .streamlit.  

3) Inside that folder, create a file named secrets.toml.  

4) Add your key to the file:
```bash
  API_KEY = "your_tmdb_api_key_here"
```

### 4. Generate the Models (If .pkl files are missing)
If movie_dict.pkl and similarity.pkl are not present, run the Jupyter Notebook:  

1) Open Movies Recommendation System.ipynb.  

2) Run all cells to generate the pickle files.

### 5. Run the App
```bash
streamlit run app.py
```

## 📂 Dataset
The dataset used in this project is the TMDB 5000 Movie Dataset from Kaggle.  

tmdb_5000_movies.csv  

tmdb_5000_credits.csv

## 🤝 Contributing  

Contributions, issues, and feature requests are welcome!

## 📝 Author  

### Bhumika Santosh Fulari

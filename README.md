## 🎬 Movie Recommendation System
This project implements a Content-Based Movie Recommendation System using data from Kaggle. It allows users to search for a movie and returns 9 similar movies based on their content features.

#### 📁 Datasets Used
tmdb_5000_movies.csv

tmdb_5000_credits.csv

Both datasets are sourced from [The Movie Database (TMDB)] and contain information on over 5,000 movies including their cast, crew, genres, keywords, and more.

## 📊 How It Works
This system uses content-based filtering — it recommends movies based on the similarity of movie features rather than user ratings or behaviors.

### 🛠️ 1. Data Preprocessing
The two datasets are merged using a common identifier (e.g., movie title or ID).

Unnecessary or redundant columns are dropped to clean the dataset.

Key features such as overview, genres, keywords, cast, and crew are extracted and combined into a new column called tags.

Text normalization techniques (e.g., lowercasing, stemming, and removal of stop words) are applied to ensure consistency in the data.

The tags column serves as the basis for generating movie recommendations.

### 🧠 2. Vectorization
Bag of Words (BoW) technique is used for feature extraction from text.

The tags column is tokenized, and the most frequent words are selected to create a vocabulary.

Each movie is then represented as a vector in this high-dimensional word frequency space.

Stop words (e.g., "and", "the", "of") are removed to retain only meaningful content.

Scikit-learn’s CountVectorizer is used for efficient text vectorization.

### 📐 3. Similarity Calculation
Cosine similarity is used to compute the distance between movie vectors.

Cosine similarity measures the angle between vectors, making it effective for high-dimensional, sparse data such as text.

For any given movie input, the 9 most similar movies (based on cosine distance) are returned as recommendations.

### 💡 Example Use Case
You search for:

🎥 "Batman Begins"

And get recommendations such as:

The Dark Knight, Batman, The Dark Knight Rises, Batman v Superman: Dawn of Justice

### 📦 Libraries Used
pandas – Data manipulation

numpy – Numerical computations

scikit-learn – Vectorization and similarity calculations

nltk – Text preprocessing 

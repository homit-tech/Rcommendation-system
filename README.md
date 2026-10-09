# Rcommendation-system
A content-based movie recommendation system built with Python, pandas, and scikit-learn. Uses the TMDB 5000 dataset to suggest similar movies based on overview, genres, keywords, and cast, ranked by cosine similarity.
# Movie Recommendation System

A content-based movie recommender that suggests similar movies based on overview, genres, keywords, and cast — built using the TMDB 5000 Movie Dataset.

## How it works

1. Merges movie metadata and credits from two TMDB datasets.
2. Extracts and cleans genres, keywords, and top cast members from nested JSON fields.
3. Combines overview, genres, keywords, and cast into a single `tags` field per movie.
4. Vectorizes tags using `CountVectorizer` (bag-of-words).
5. Computes cosine similarity between all movie vectors.
6. Given a movie title, returns the 5 most similar titles by similarity score.

## Dataset

- [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) (Kaggle)
- `tmdb_5000_movies.csv` — budget, genres, keywords, overview, popularity, etc.
- `tmdb_5000_credits.csv` — cast and crew

## Tech stack

- Python, pandas, NumPy
- scikit-learn (`CountVectorizer`, `cosine_similarity`)
- NLTK (`PorterStemmer`)

## Usage

```python
recommend('Avatar')
```

Returns the top 5 movies most similar to the given title.

## Known limitations

- Dataset is a fixed 1916–2017 snapshot and doesn't include every film (e.g. some mainstream titles are missing).
- Search is currently case- and whitespace-sensitive on exact title match.
- Director/crew data is parsed but not yet used in similarity scoring.

## Roadmap

- [ ] Case-insensitive and fuzzy title search
- [ ] Switch to TF-IDF for better signal weighting
- [ ] Include director in similarity scoring
- [ ] Streamlit app with poster images via TMDb API
- [ ] Evaluate against a hand-picked test set

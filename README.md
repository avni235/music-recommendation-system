# 🎵 Music Recommender System

This project implements a simple **Music Recommender System** using TF-IDF vectorization and cosine similarity to recommend songs based on textual metadata like artist name, composer, and lyricist.

## 📁 Dataset Used

The following CSV files are used (from the KKBOX dataset):

- `members.csv` – User/member information (not used in this implementation)
- `sample_submission.csv` – Sample structure for submission (not used here)

## ⚙️ Preprocessing Steps

- Merged `train.csv` with `songs.csv` on `song_id`.
- Dropped unnecessary columns like `song_length` and `language`.
- Cleaned textual columns (`artist_name`, `composer`, `lyricist`) by removing special characters like `|` and `/`.

## 🧠 Model Logic

1. **TF-IDF Vectorization**  
   Combined text features (`artist_name`, `composer`, `lyricist`) into a single string column.
   
2. **Cosine Similarity**  
   Used `cosine_similarity()` from `sklearn.metrics.pairwise` to compute similarity between songs.

3. **Recommendation Function**  
   - `recommend(song_name)` returns a list of top 5–10 songs most similar to the input song based on metadata.

## 🧪 Example

```python
recommend('La La La')
```

**Output:**
```
Flashlight  
切歌  
你那麼愛她  
Panda  
You Don’t Have To Be Together To Love  
Rather Be (feat. Jess Glynne)  
Everglow  
Lion Heart  
Lion Heart  
```

## 🛠 Requirements

- pandas
- scikit-learn

Install using:

```bash
pip install pandas scikit-learn
```

## 📌 Notes

- This is a **content-based recommender**, so recommendations are based purely on song metadata.
- The similarity matrix is based on TF-IDF of combined metadata (not audio content or user behavior).

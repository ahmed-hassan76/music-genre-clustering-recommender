# Music Genre Clustering & Recommendation System  
### Mini Project 3 – Data Mining (CSEN 911)

This project applies **K-Means clustering** on Spotify music data to group similar music genres based on core audio features.  
It also builds a **genre recommender system** that suggests similar sub-genres for music exploration.

The notebook includes exploratory analysis, preprocessing, model building, cluster interpretation, evaluation, and a bonus recommendation function.

---

## 📌 Project Objectives

1. Perform data preprocessing (cleaning, outlier handling, scaling).
2. Analyze music feature relationships and answer the required analytical questions:
   - Top factors affecting song popularity.
   - Most/least popular genres.
   - Most strongly correlated audio features.
   - Frequency of genre category words.
   - Additional visualization highlighting new insights.
3. Build, optimize, and justify a **K-Means clustering model**.
4. Interpret each cluster’s characteristics and sample genres.
5. Evaluate clustering using Silhouette, Calinski-Harabasz, and Davies-Bouldin scores.
6. Implement a **genre recommendation function** using the fitted clustering model.

---

## 📊 Dataset Overview

- Contains Spotify subgenres and numeric audio features.
- Key feature columns used for clustering:
  - `tempo`
  - `energy`
  - `acousticness`
  - `danceability`
  - `instrumentalness`
- Popularity values used for correlation analysis but *not* for clustering.

---

## 🔧 Data Preprocessing

- Handled missing values.
- Detected and clipped outliers using **1st–99th percentile winsorization**.
- Verified impact through before/after statistics and boxplots.
- Scaled numerical features using **StandardScaler**.

---

## 🤖 Clustering Model

### **K-Means (K=2)**  
K was selected through:

- **Elbow method** (clear bend at K=2)  
- **Silhouette analysis** (highest score at K=2)

Model parameters:
```python
kmeans = KMeans(
    n_clusters=2,
    init='k-means++',
    n_init=20,
    max_iter=300,
    random_state=42
)
## 🎨 Cluster Interpretation

Clusters were interpreted visually using:

- PCA 2D projection  
- Cluster mean feature plots  
- Top genre-word frequencies  
- Random samples from each cluster  

These visual and statistical insights helped determine the musical characteristics of each cluster  
(e.g., high-energy modern genres vs. more acoustic/low-energy genres).

---

## 🧪 Model Evaluation

Metrics used:

- Silhouette Score  
- Calinski–Harabasz Index  
- Davies–Bouldin Index  

Evaluation supported the selection of **K = 2**, showing clear separation and reasonable internal cohesion across the clusters.

---

## 🛠️ Technologies Used

- Python  
- Pandas  
- NumPy  
- Matplotlib & Seaborn  
- Scikit-learn  
- Jupyter Notebook
## 👤 Author
- **Ahmed Hassan**

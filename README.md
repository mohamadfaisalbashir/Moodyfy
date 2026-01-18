🎵 Moodyfy: Mood & Audio-Based Music Recommendation System
Moodyfy is an intelligent music recommendation system that uses Machine Learning to identify the mood of a song and provide recommendations for similar songs based on audio characteristics (such as tempo, energy, and danceability). This project combines Supervised Learning (Mood Classification) and Unsupervised Learning (Clustering & Similarity Search) approaches.

📖 Overview
This system works through three main stages:
1.  **Mood Classification:** Predicts whether a song falls into the Happy, Sad, Calm, or Energetic category.
2.  **Pattern Analysis:** Groups songs with similar audio characteristics.
3.  **Recommendations:** Provides song suggestions based on song title input or user mood.

📊 Dataset & Features
This project uses two main datasets:
1.  **data_moods.csv:** Training data with mood labels.
2.  **data.csv:** General Spotify song data (without mood labels) to be predicted and recommended.

Audio Features used: The model learns patterns from the following features:
* danceability, acousticness, energy, instrumentalness
* liveness, valence, loudness, speechiness, tempo

🚀 Methodology
The Moodyfy system workflow is as follows:

1. Preprocessing & EDA
* Data cleaning (removing duplicates and missing values).
* Correlation analysis between features using Heatmap.
* Feature standardization using StandardScaler.

2. Mood Classification (Random Forest)
* Using the Random Forest Classifier algorithm to train the model on data_moods.csv.
* The model predicts the mood for thousands of songs in data.csv.
* A screenshot of the classification report can be added.

3. Clustering (K-Means)
* Using the Elbow Method to determine the optimal number of clusters.
* Grouping songs based on audio feature similarity.
* Visualizing cluster results using PCA (Principal Component Analysis).

4. Recommendation System (KNN)
* Using K-Nearest Neighbors (KNN) with Cosine Similarity.
* Searching for the closest songs (neighbors) based on audio feature vectors.

🛠 Technology Used
1.  **Python:** Main programming language.
2.  **Pandas & NumPy:** Data manipulation and analysis.
3.  **Scikit-Learn:** ML algorithms (Random Forest, K-Means, KNN, PCA, StandardScaler).
4.  **Matplotlib & Seaborn:** Data visualization.
5.  **Yellowbrick:** Visualization for cluster evaluation (Elbow Method).

💻 How to Use
Run the Python script or notebook. The program has two interaction modes at the end:
1. Recommendations Based on Song Title
Enter the title of a song you like, and the system will search for songs with the most similar audio characteristics.
```bash
Input: "Shape of You"
Output: 5 5 Recommended songs that are similar in sound.
```

2. Recommendations Based on Mood
Enter your mood (Happy, Sad, Calm, Energetic). The system will:
1. Filter songs with that mood.
2. Take a random song sample.
3. Search for other song recommendations similar to the sample.
```bash
Input: “Energetic”
Output: 5 recommended songs with an energetic tone.
Precision@K: 0.8 (Example of recommendation accuracy metric)
```

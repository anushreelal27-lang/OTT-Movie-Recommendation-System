# OTT-Movie-Recommendation-System
A Content-Based Movie Recommendation System built using Python, Pandas, NLP, Scikit-Learn, Matplotlib, and Seaborn using the TMDB 5000 Movies Dataset.
This project recommends movies similar to a selected movie by analyzing movie metadata such as:

Genres
Keywords
Cast
Crew
Overview

The project also includes exploratory data analysis and visualization using Matplotlib and Seaborn.

📌 Project Overview

The goal of this project is to build a movie recommendation engine that suggests similar movies based on movie content instead of user ratings.

The recommendation system uses:

Natural Language Processing (NLP)
Count Vectorization
Cosine Similarity

to calculate similarity between movies.

🛠 Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-Learn
NLTK
Pickle
📂 Dataset Used

TMDB 5000 Dataset:

tmdb_5000_movies.csv
tmdb_5000_credits.csv

Dataset contains:

Movie titles
Genres
Cast
Crew
Keywords
Overview
Ratings
Popularity
Revenue
Budget
⚙️ Project Workflow
1. Data Collection

Loaded movie and credits datasets using Pandas.

movies = pd.read_csv('tmdb_5000_movies.csv')
credits = pd.read_csv('tmdb_5000_credits.csv')
2. Data Merging

Merged both datasets using the movie title.

movies = movies.merge(credits,on='title')
3. Data Cleaning

Performed:

Null value handling
Duplicate removal
Column filtering
4. Feature Engineering

Created tags using:

Overview
Genres
Keywords
Cast
Crew

Example:

movies['tags'] = movies['overview'] + movies['genres'] + movies['keywords'] + movies['cast'] + movies['crew']
5. Text Processing

Applied:

Lowercasing
Tokenization
Stemming using PorterStemmer
6. Vectorization

Used CountVectorizer to convert text into vectors.

cv = CountVectorizer(max_features=5000, stop_words='english')
7. Similarity Calculation

Used cosine similarity to calculate similarity between movies.

similarity = cosine_similarity(vectors)
8. Recommendation Function

Built a recommendation function that returns top 5 similar movies.

recommend('Avatar')
📊 Data Visualization

The project includes visualizations using Matplotlib and Seaborn.

Implemented Visualizations
1. Most Common Words Bar Plot
Shows frequently occurring words in movie tags.
2. Tags Length Distribution
Distribution of number of words in movie tags.
3. Histogram of Tags
Visualizes tag frequency distribution.
4. Similarity Heatmap
Heatmap showing similarity between movies.
5. Similar Movies Bar Plot
Displays similarity scores for recommended movies.
6. Vocabulary Frequency Plot
Shows top vectorized vocabulary words.
7. KDE Plot
Density distribution of tag lengths.
8. Boxplot of Tag Length
Detects outliers in movie tags.
9. Scatterplot of Similarity Scores
Shows distribution of similarity scores.
10. Similarity Decay Line Plot
Displays decline in similarity scores across ranked movies.
📈 Libraries Used for Visualization
import matplotlib.pyplot as plt
import seaborn as sns
🧠 NLP Techniques Used
Tokenization
Stemming
Vectorization
Cosine Similarity
📦 Model Serialization

Saved processed data using Pickle.

pickle.dump(new_df.to_dict(), open('movie_dict.pkl','wb'))
pickle.dump(similarity, open('similarity.pkl','wb'))
🚀 Example Recommendation

Input:

recommend('Avatar')

Output:

John Carter
Guardians of the Galaxy
Star Trek
The Avengers
Aliens
📌 Key Learnings
Data preprocessing
NLP fundamentals
Recommendation systems
Feature engineering
Cosine similarity
Data visualization
Working with large datasets
📷 Sample Visualizations

You can add screenshots of:

Heatmaps
Histograms
Bar graphs
Similarity plots

inside a /screenshots folder.

Example:

![Heatmap](screenshots/heatmap.png)
📁 Project Structure
OTT-Recommendation-System/
│
├── tmdb_5000_movies.csv
├── tmdb_5000_credits.csv
├── OTT_Program.ipynb
├── movie_dict.pkl
├── similarity.pkl
├── screenshots/
├── README.md
▶️ How to Run
Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn nltk
Run Jupyter Notebook
jupyter notebook

Open:

OTT_Program.ipynb
🔮 Future Improvements
Streamlit Web App
Poster Recommendation
TMDB API Integration
Hybrid Recommendation System
User-based collaborative filtering
🤝 Contributing

Contributions and suggestions are welcome.

📜 License

This project is for educational and learning purposes.

⭐ If you like this project

Give it a ⭐ on GitHub.

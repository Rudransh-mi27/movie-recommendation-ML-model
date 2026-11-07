Movie Recommendation System
A beginner-level content-based movie recommendation system built
with Python and the TMDB 5000 Movies and Credits datasets.

The notebook recommends movies based on similarities in their plot
overview, genres, keywords, top three cast members, and director.
Project Overview
This project follows a simple content-based filtering approach:
1. Load the movies and credits datasets using Pandas.
2. Merge the datasets using the movie title.
3. Keep the columns needed for recommendations.
4. Remove rows with missing values and duplicate rows.
5. Extract genre names, keywords, the first three cast members, and
   director names from the JSON-like columns.
6. Combine the extracted information and movie overview into a single
   tags field.
7. Convert text to lowercase and apply Porter stemming.
8. Use CountVectorizer to convert tags into numerical vectors.
9. Calculate movie-to-movie similarity using cosine similarity.
10. Return the five most similar movies for a given movie title.
Technologies Used
- Python
- Jupyter Notebook
- Pandas
- NLTK (PorterStemmer)
- Scikit-learn
  - CountVectorizer
  - cosine_similarity
Dataset
The notebook uses two CSV files from the TMDB 5000 Movie Dataset:
- tmdb_5000_movies.csv
- tmdb_5000_credits.csv
Place both files in a folder named data in the project directory. The
datasets are not included in this repository; obtain them separately
from the dataset provider.

Expected project structure:
movie-recommendation-system/
├── data/
│   ├── tmdb_5000_movies.csv
│   └── tmdb_5000_credits.csv
├── MyFirst_ML.ipynb
├── requirements.txt
└── README.md
Getting Started
1. Clone the repository
git clone <your-repository-url>
cd movie-recommendation-system
2. Create and activate a virtual environment (recommended)
python -m venv .venv
macOS/Linux:
source .venv/bin/activate
Windows:
.venv\Scripts\activate
3. Install dependencies
pip install pandas nltk scikit-learn jupyter
You can also create a requirements.txt with:
pandas
nltk
scikit-learn
jupyter
Then install with:
pip install -r requirements.txt
4. Set the dataset paths
In the first notebook cell, use paths relative to the project directory:
movies = pd.read_csv("data/tmdb_5000_movies.csv")
credits = pd.read_csv("data/tmdb_5000_credits.csv")
This replaces the machine-specific file paths used during initial
development.
5. Run the notebook
jupyter notebook
Open MyFirst_ML.ipynb and run the cells from top to bottom.
Example
The notebook currently runs:
recommend("Avatar")
The recommendation function prints the five most similar movie titles,
excluding the input movie itself.

The title must currently match a movie title in the dataset exactly.
Core Concepts
Content-based filtering
The system recommends movies using information about each movie rather
than user ratings or viewing history.
CountVectorizer
CountVectorizer converts the text in the tags column into numerical
word-count vectors, using up to 5,000 features and removing English stop
words.
Cosine similarity
Cosine similarity compares the movie vectors. Movies with more similar
tag vectors receive higher similarity scores and are ranked closer to
the input movie.
Porter stemming
Porter stemming reduces words to their stem before vectorization,
helping related word forms be treated more similarly.
Current Limitations
- Recommendations depend on the metadata available in the dataset.
- The movie title lookup is case-sensitive and requires an exact
  match.
- The notebook prints movie titles only; it does not currently show
  similarity scores.
- This is a content-based system, not a collaborative-filtering
  system.
- The current notebook is a prototype and does not include a web
  interface or API.
Possible Improvements
- Handle unknown movie titles gracefully.
- Make title search case-insensitive.
- Display similarity scores alongside recommendations.
- Add exploratory data analysis and visualizations.
- Build an interactive interface using Streamlit.
- Compare content-based recommendations with other recommendation
  approaches.
Learning Outcomes
Through this project, I practised:
- Loading, merging, and cleaning datasets with Pandas.
- Extracting useful information from structured text fields.
- Text preprocessing and stemming.
- Feature extraction with CountVectorizer.
- Measuring similarity with cosine similarity.
- Building a basic content-based recommendation system.
Project type: Beginner Machine Learning
Area: Recommendation Systems / Natural Language Processing (NLP)
Notebook: MyFirst_ML.ipynb

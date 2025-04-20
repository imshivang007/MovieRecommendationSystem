# Movie Recommender System

This project is a Movie Recommender System built using Python and Streamlit. It recommends movies based on content similarity using movie metadata such as genres, keywords, cast, and crew.

## Features

- Content-based movie recommendation using cosine similarity.
- Fetches movie posters dynamically from The Movie Database (TMDB) API.
- Interactive web app interface built with Streamlit.
- Easy to use dropdown to select a movie and get top 5 recommendations with posters.

## Installation

1. Clone the repository.

2. Create and activate a virtual environment (optional but recommended):

```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the project root and add your TMDB API key:

```
TMDB_API_KEY=your_api_key_here
```

You can get an API key by creating an account on [TMDB](https://www.themoviedb.org/).

## Usage

Run the Streamlit app locally:

```bash
streamlit run app.py
```

This will open a web interface where you can select a movie from the dropdown and get 5 recommended movies with their posters.

## Data and Recommendation Approach

- The project uses the TMDB 5000 movies and credits datasets (`tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`).
- Movie metadata such as genres, keywords, cast (top 3), and crew (director) are processed and combined into tags.
- These tags are vectorized using `CountVectorizer` and cosine similarity is computed between movies.
- The recommendation is based on the highest cosine similarity scores.
- The processed movie list and similarity matrix are saved as pickle files (`movie_list.pkl` and `similarity.pkl`) used by the app.

## Deployment

The project includes deployment configuration for platforms like Heroku:

- `setup.sh` configures Streamlit server settings.
- `Procfile` defines the command to run the app:

```
web: sh setup.sh && streamlit run app.py
```

## Environment Variables

- `TMDB_API_KEY`: Your TMDB API key for fetching movie posters.

## License

This project is open source and available under the MIT License.

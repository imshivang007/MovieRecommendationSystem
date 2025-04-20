# Movie Recommender System

This is a Movie Recommender System web application built using Streamlit. The app allows users to select a movie and get recommendations for similar movies along with their posters fetched from The Movie Database (TMDB) API.

## Features

- Select a movie from a dropdown list.
- Get 5 recommended movies based on similarity.
- View movie posters fetched dynamically from TMDB.
- Simple and interactive user interface using Streamlit.

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd Movie Recommendation System
```

2. Create and activate a virtual environment (optional but recommended):

```bash
python -m venv venv
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate
```

3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

4. Obtain a TMDB API key by creating an account at [TMDB](https://www.themoviedb.org/).

5. Create a `.env` file in the project root and add your TMDB API key:

```
TMDB_API_KEY=your_api_key_here
```

## Usage

Run the Streamlit app locally with:

```bash
streamlit run app.py
```

This will open the app in your default web browser. Select a movie from the dropdown and click "Show Recommendation" to see recommended movies.

## Deployment

This app is deployed on [Render](https://render.com).

You can access the live app here: [https://movierecommendationsystem-4r0a.onrender.com](https://movierecommendationsystem-4r0a.onrender.com)

The deployment uses the following setup:

- `setup.sh` configures the Streamlit server for Render.
- `Procfile` runs the setup script and starts the Streamlit app.

## Project Structure

- `app.py`: Main Streamlit application code.
- `movie_list.pkl`: Pickled movie list data.
- `similarity.pkl`: Pickled similarity matrix for recommendations.
- `tmdb_5000_credits.csv` and `tmdb_5000_movies.csv`: Original datasets used for building the model.
- `requirements.txt`: Python dependencies.
- `setup.sh`: Streamlit server configuration for deployment.
- `Procfile`: Deployment command for Render.
- `.env` (not included): Environment variables including TMDB API key.

## Notes

- Make sure to keep your TMDB API key secure and do not share it publicly.
- The recommendation system uses a precomputed similarity matrix for fast recommendations.

## License

This project is open source and available under the MIT License.

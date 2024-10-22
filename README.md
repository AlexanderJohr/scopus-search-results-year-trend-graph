# Scopus Search Results Year Trend Graph

## Overview
This script retrieves publication counts from the Scopus API for specified search terms and plots the results as a time series graph, showing the number of publications per year for each search term. It caches results in a CSV file to avoid redundant API calls and allows for updating and visualizing publication trends over time.

## Features
- Retrieves publication counts for search terms via the Scopus API.
- Caches retrieved data to a CSV file to optimize API usage.
- Supports year-based querying (2005–2022).
- Filters out terms with extremely high or low publication counts.
- Visualizes the publication trends in a line chart, which can be saved as both PNG and PDF.

## Prerequisites
- Python 3.6 or higher
- `requests` library for making API requests
- `matplotlib` for plotting publication data
- `csv` for caching data locally

## Repository Structure

- `LICENSE`: License file for the repository.
- `publication_counts.csv`: CSV file to cache publication counts.
- `scopus-search-results-year-trend-graph.py`: Main script to fetch data and generate the trend graph.
- `search_terms.py`: Contains the list of search terms.

## Setup

Clone the repository:
```sh
git clone https://github.com/yourusername/scopus-search-results-year-trend-graph.git
cd scopus-search-results-year-trend-graph
```

### API Key
You will need a Scopus API key to run this script. Replace the value of `API_KEY` with your own key:
```python
API_KEY = 'your_scopus_api_key_here'
```

### Dependencies
Install the required Python libraries using pip:
```bash
pip install requests matplotlib
```

### Search Terms
The search terms should be stored in a separate Python file named `search_terms.py`. The file should define a list called `SEARCH_TERMS`, e.g.:
```python
SEARCH_TERMS = ['artificial intelligence', 'machine learning', 'data science']
```

### CSV Cache
The script uses a CSV file (`publication_counts.csv`) to store the retrieved publication data for future use, reducing the need for repeated API calls. If no such file exists, it will be created after the first run.

## Running the Script
To execute the script and retrieve the publication data, run the following command:
```bash
python scopus-search-results-year-trend-graph.py
```

The script will:
1. Retrieve publication counts for each search term from 2005 to 2022.
2. Cache the results in `publication_counts.csv`.
3. Generate a line plot showing the publication trends over time.
4. Save the plot as both `publication_trend.png` and `publication_trend.pdf`.

## Output
The script will generate the following outputs:
1. `publication_counts.csv` – A CSV file containing cached publication counts for all search terms across the specified years.
2. `publication_trend.png` and `publication_trend.pdf` – Line charts visualizing the publication trends for each search term.

## Usage Notes
- The script filters out terms with either very high publication counts (over 35,000) or very low counts (below 195) for clearer visualization.
- If there are any issues with the API call (e.g., network issues), the script will handle the error and move on to the next term/year.
  
## Customization
You can modify the following variables to fit your requirements:
- `yearRange`: Adjust the range of years for which publication data is retrieved.
- `SEARCH_TERMS`: Define the search terms in the `search_terms.py` file.
- `API_KEY`: Replace with your own Scopus API key.

# Spotify Playlist Data Analysis

![Spotify Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/168px-Spotify_logo_without_text.svg.png)

> A data pipeline and analytics project using PySpark and Spotipy to analyze Spotify playlist data

## 📋 Overview

This project processes and analyzes Spotify playlist data through a comprehensive data pipeline:

- **Data Processing**: Loads and transforms nested playlist data using PySpark
- **Feature Enrichment**: Fetches audio features for tracks via Spotify API
- **Analysis**: Identifies popular tracks and performs basic audio feature analytics

## 🛠️ Technologies

- **PySpark**: For distributed data processing
- **Spotipy**: Python library for Spotify API integration
- **Google Colab**: Runtime environment with seamless Google Drive integration
- **Multithreading**: For efficient API calls
- **Matplotlib**: For data visualization

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- Google account with Google Drive access
- Spotify Developer account and API credentials

### Dependencies

```bash
pip install pyspark spotipy urllib3==1.26 requests matplotlib pandas google-colab oauth2client
```

### Setup Instructions

1. **Clone the Repository** (if applicable):
   ```bash
   git clone <your-repo-url>
   cd <your-repo-directory>
   ```

2. **Prepare Google Drive**:
   - The notebook will prompt you to mount your Google Drive
   - Ensure these directories exist:
     - `/content/gdrive/MyDrive/BDA_Final_Project/`
     - `/content/gdrive/MyDrive/BDA_Final_Project/uri_feats/`

3. **Configure Spotify API**:
   - Create a Spotify Developer account at [developer.spotify.com](https://developer.spotify.com/)
   - Create a new application to obtain Client ID and Client Secret
   - Replace the placeholder credentials in the notebook:
     ```python
     auth_manager = SpotifyClientCredentials(
         client_id='YOUR_CLIENT_ID',
         client_secret='YOUR_CLIENT_SECRET'
     )
     ```

## 📊 Project Workflow

1. **Environment Setup**: Install libraries and mount Google Drive
2. **Data Preparation & Storage**:
   - Process initial dataset
   - Slice data into multiple JSON files
   - Copy files to Google Drive
3. **Spark Initialization & Data Loading**:
   - Initialize SparkSession
   - Load JSON data into Spark DataFrames
4. **Data Transformation**:
   - Flatten nested playlist and track data
   - Combine DataFrames
5. **Audio Feature Extraction**:
   - Collect unique track URIs
   - Manage previously fetched data
   - Fetch new audio features using multithreading
6. **Analytics**:
   - Calculate track popularity
   - Create visualizations

## 📁 Output Files

The project generates several files in Google Drive:

- **`filtered[1-8].json`**: Sliced raw data
- **`uris.json`**: List of unique track URIs
- **`feats1.json`**: Batched audio features from Spotify API


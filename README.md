# GDELT-Data-Engineering-Pipeline-
A Python-based data engineering pipeline for automatically discovering, downloading, extracting, and processing the latest GDELT Events, Mentions, and GKG datasets.

The project focuses on building a modular ETL workflow that retrieves newly published GDELT data without relying on hardcoded dataset URLs

## Project Overview
The GDELT Project provides large-scale datasets containing information about global events, news coverage, and knowledge graph data.

This project demonstrates how to build a Python ETL pipeline that:

1. Checks the GDELT lastupdate.txt file for the latest available datasets.
2. Dynamically identifies the required GDELT files.
3. Downloads the datasets as ZIP archives.
4. Extracts the raw data from the ZIP files.
5. Loads the extracted data into Pandas.
6. Prepares the data for further transformation and analysis.

## 🛠️ Technologies Used

Python

Pandas

Requests

REST/HTTP

ZIP/CSV processing

Jupyter Notebook

## ▶️ Running the Pipeline

Run the main pipeline from the project root:

python src/pipeline.py

The pipeline will:

1. Connect to the GDELT data repository
2. Discover the latest files
3. Download the selected datasets
4. Extract the ZIP archives
5. Load the data into Pandas
6. Display information about the processed datasets

## 🔄 Pipeline Workflow
GDELT lastupdate.txt
        ↓
Discover Latest Files
        ↓
Download ZIP Files
        ↓
Extract ZIP Archives
        ↓
Load CSV Data
        ↓
Pandas DataFrame
        ↓
Transform / Analyse

## 📊 Datasets

The pipeline is designed to work with three major GDELT datasets:

Events: Contains structured information about events reported in global news.

Mentions: Contains information about news mentions associated with GDELT events.

GKG: The GDELT Global Knowledge Graph dataset containing information extracted from news content.

## ⚙️ Dynamic File Discovery

Instead of hardcoding individual GDELT download URLs, the pipeline uses the GDELT lastupdate.txt file to identify the latest available files.

This makes the pipeline more flexible as new datasets are published.

The pipeline retrieves the metadata and identifies the relevant files before downloading them.

## 🔧 Key Components

#### config.py

Stores project configuration such as:

GDELT base URL
Raw data directory
Processed data directory
Log directory
Request timeout

#### latest_file.py

Retrieves and parses GDELT's lastupdate.txt file to identify the latest available datasets.

#### downloader.py

Handles downloading GDELT ZIP files using Python requests.

#### extract.py

Extracts the contents of downloaded ZIP archives.

#### transform.py

Loads extracted GDELT data into Pandas for further processing and transformation.

#### pipeline.py

Coordinates the different stages of the ETL workflow.

# Movie Recommendation System

This project is a movie recommendation system that consists of two main components: a Python part for data preprocessing, model training, and recommendation generation, and a Go part that provides an API for fetching recommendations.

## Table of Contents

- [Overview](#overview)
- [Structure](#structure)
- [Setup](#setup)
- [Usage](#usage)
- [License](#license)

## Overview

The movie recommendation system uses collaborative filtering to generate movie recommendations for users. The system is divided into two parts:

1. **Python Part**: Handles data preprocessing, model training, recommendation generation, and evaluation.
2. **Go Part**: Provides a REST API to fetch recommendations for users.

## Structure

    recSystem/
    │
    ├── python/
    │   ├── Dockerfile
    │   ├── requirements.txt
    │   ├── preprocess.py
    │   ├── main.py
    │   ├── database.py
    │   ├── similarity.py
    │   ├── recommendations.py
    │   ├── README.md
    │   └── tests/
    │       ├── test_database.py
    │       ├── test_integration.py
    │       ├── test_preprocess.py
    │       ├── test_recommendations.py
    │       └── testt_similarity.py
    ├── go/
    │   ├── Dockerfile
    │   ├── go.mod
    │   ├── go.sum
    │   ├── main.go
    │   ├── handlers.go
    │   ├── handlers_test.go
    │   └── README.md
    │
    └── data/
        ├── movies.csv
        ├── ratings.csv
        ├── train_ratings.csv
        ├── test_ratings.csv
        └── recommendations.db
        

## Setup

### Prerequisites

- Docker
- Python 3.x
- Go 1.18 or higher

### Python Part

1. Navigate to the Python directory:
```bash
cd python
```

2. Install the required Python packages:
```bash
pip install -r requirements.txt
```

3. Run the preprocessing script:
```bash
python preprocess.py
```

4. Run the main script to train the model and generate recommendations:
```bash
python main.py
```

### Go Part

1. Navigate to the Go directory:
```bash
cd go
```

2. Build the Docker image:
```bash
docker build -t recommendations-api .
```

3. Run the Docker container:
```bash
docker run -p 8080:8080 recommendations-api
```

## Usage

### Fetch Recommendations

You can fetch movie recommendations for a user by sending a GET request to the API.

Example:
```bash
curl http://localhost:8080/recommendations/1/5
```

## License
This project is licensed under the MIT License.
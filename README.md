
# Song Recommendation System

This is a song recommendation app that suggests songs based on search criteria such as artist, genre, and recommends songs on various song properties.
This project consists of Flask application for the backend API, React for client side application.

## Index

- [Features](#features)
- [Running with Docker](#running-with-docker)
- [Running without Docker](#running-without-docker)
- [How to use](#how-to-use)
- [API Documentation](#api-documentation)
- [Model](#model)

## Features

- Recommend songs based on the search.
- Recommend similar songs based on the song.

## Running app on local machine

To run the project locally, there are 2 methods, with docker and without docker.

### Running with docker

To run the project with docker, make sure you have [Docker](https://docs.docker.com/get-docker/) and [Git](https://git-scm.com/downloads) installed on your system. 

Step 1: Clone the project

```bash
  https://github.com/A-k-sha-y/JTP_Project.git
```

Step 2: Navigate to JTP_Project directory

```bash
  cd JTP_Project
```

Step 3: Start the project using docker compose

```bash
  docker-compose up --build
```

Step 4: To access the application, go to your browser and type `http://localhost:3000` in the address bar.

Step 5: Exit the application.

```bash
  docker-compose down
```

### Running without docker

Make sure you have installed [Node](https://nodejs.org/en/download), [Python](https://www.python.org/downloads/),and [Git](https://git-scm.com/downloads) on your system.

Step 1: Clone the project

```bash
  https://github.com/A-k-sha-y/JTP_Project.git
```

Step 2: Navigate to JTP_Project/server directory

```bash
  cd JTP_Project/server
```

Step 3: Install the python dependencies

```bash
  pip install -r requirements.txt
```

Step 4: While in server directory, start the server.

```bash
  flask run
```

Step 5: Open a new terminal and navigate to musicrecommender directory

```bash
  cd JTP_Project/musicrecommender
```

Step 6: Install the required packages using npm

```bash
  npm install
```

Step 7: Run the application

```bash
  npm start
```

Step 8: To access the application, go to your browser and type `http://localhost:3000` in the address bar.

## How to use

Step 1: Open a browser and type `localhost:3000` in the Address bar.

![Home](https://raw.githubusercontent.com/A-k-sha-y/JTP_Project/master/screenshots/Home.png)

Step 2: Click on the Login Button at the top right, and either login in, or create a new account.

![Login](https://raw.githubusercontent.com/A-k-sha-y/JTP_Project/master/screenshots/Login.png)

Step 3: Search by typing the song or artist name in the search bar and after clicking on search it will show you the search results.  

![SearchResult](https://raw.githubusercontent.com/A-k-sha-y/JTP_Project/master/screenshots/Searching.png)

Step 4: Once you click on the play, The application will show you the similar songs!

![Recommendation](https://raw.githubusercontent.com/A-k-sha-y/JTP_Project/master/screenshots/Recommendation.png)
![Recommendation](https://raw.githubusercontent.com/A-k-sha-y/JTP_Project/master/screenshots/Recommendation2.png)

## API Documentation

1. -POST /search
- Takes input from searchbar
- Searches songs according to input using similarity
- Returns the response JSON

2. -POST /recommend
- Takes information of the current song which is playing
- Uses the trained model on the dataset, to predict similar songs to the current one
- Returns the response JSON

3. -GET /top_track
- Fetches the top 5 songs according to popularity from the dataset
- Returns the response JSON

4. -GET /top_artist
- Fetches the top 4 artist from the dataset
- Returns the response JSON

## Flow Diagrams

### /Search
![Home](https://raw.githubusercontent.com/A-k-sha-y/JTP_Project/master/screenshots/Search_flow.png)

### /Recommend
![Recommend](https://raw.githubusercontent.com/A-k-sha-y/JTP_Project/master/screenshots/Recommend_flow.png)

  
## Model 
[Training Notebook](Model.ipynb)

This model differs from traditional recommendation engines by focusing on song features rather than user interactions. It utilizes Nearest Neighbor models to calculate similarities between songs based on their features. To improve search accuracy, it incorporates fuzzywuzzy logic.

The model is trained on Spotify Tracks Dataset with around 1,14,000 data points [Kaggle](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)

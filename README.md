# Making Sence of Genre
UMBC DATA 601 Fall 2020

This project is an utilizes the [Spotify Web API](https://developer.spotify.com/documentation/web-api/). exploring, analysing, modeling genre by using  different audio features from 13 different Spotify genres. The report and modeling can be found in Technical Notebook.ipynb.  All the song data was collected from the Spotify Web API Code and API calls for data collection are found in the importSpotifyData.ipynb, and detailed EDA can be found in spotifyGenreEDA.ipynb.

![spotify_genre](https://images.ctfassets.net/lnhrh9gqejzl/3F0ITbsO5qg24wy84a66kw/d29a47af6903a17fb74eb5c8fa76ea49/Genres_Dance_Pop_Every_Noise.jpg?w=1280)

# Goals

This assingment has both two types of goals:

- Learn how to implment the Spotify Web Api, by building a script that can query n number of playlists given a catigory, and save that track data to disk. 
- Use EDA concepts, including but not limited to, distributions, data summaries, and visualizations to explore the differences between the tracks in each spotify category.

# Motivation & Background

Music genre is an incredibly difficult classification question as the lines that separate one style of music from another are never definitive. There is always going to be songs and artist that bend and twist genre, eventually shaping their work into wholly new and original genres.

The inspiration for this project came from another tool that used the spotify web API. [Every Noise](http://everynoise.com/) is an ongoing project that is logging and visualizing the spotify genre space. As of November 2020 there are 5,068 unique genres within the Spotify track library, and the number is always growing. The tool provides a wonderfully exciting way to explore both mainstream and fringe genres and builds a playlist for each and every genre it logs.  [This Link](https://open.spotify.com/playlist/69fEt9DN5r4JQATi52sRtq?si=_xSevsMHTh6QEOnPmQdAGw) will take you to a playlist generate by the Every Noise Project, where every genre has one song; over 350 hours of music. 

Similar projects and tutorials references on the Spotify Web API and python data science
- [Every Noise](http://everynoise.com/) an ongoing project mapping and cataloging every single spotify genre
- https://medium.com/@maxtingle/getting-started-with-spotifys-api-spotipy-197c3dc6353b Shows how to implment the Spotipy python package to acess the Spotify Web API and save the results to a pandas data frame.
- https://www.kaggle.com/nicapotato/top-spotify-tracks-2019-eda/execution An example of EDA on spotify feature data 
- https://www.kaggle.com/aniruddhachoudhury/classify-song-genres-from-audio-data-model Refrenced for testing and comparing moddle results 


# Table of Contents

- Data: Includes data
	+ spotify_df.csv : a .csv of the dataset 
	+ spotify_df.pkl : a python pickle saved spotify dataframe element 
- Notebooks
	+ importSpotifyData.ipynb: Quering, cleaning, and saving the data from the Spotify Web API 
	+ spotifyGenreEDA.ipynb: detailed EDA of the dataset 
	+ Technical Notebook.ipynb: Notebook containing the report and modeling 
	
# Software Requirements & Usage

- Packages Used: 
	+ [Spotipy](https://spotipy.readthedocs.io/en/latest/#): A Python library for the [Spotify Web API](https://developer.spotify.com/documentation/web-api/)
	+ [getpass](https://pymotw.com/2/getpass/#module-getpass): A Python library to hide spotify web API credentials 
	+ [pickel](https://docs.python.org/3/library/pickle.html): used to save the spotify dataframe to disk
	+ [pandas](https://pandas.pydata.org/docs/)
	+ [matplotlib](https://matplotlib.org/3.3.3/contents.html)
	+ [seaborn](https://seaborn.pydata.org/)
	+ [scikit-learn](https://scikit-learn.org/stable/)

# Dataset

If you want a local copy of the data, please go to `Notebooks` folder and run getSpotifyData.ipynb notebook. You will need a spotify account and have a spotify client ID and client secret. To find this look at your [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/applications) The dataset contained in this repo was pulled on Thu 19 Nov 2020 05∶13∶29 PM EST. Running this code will create a potentially different dataset of tracks.

[Spotipy](https://github.com/plamere/spotipy) is a python wrapper for the [Spotify Web API](https://developer.spotify.com/documentation/web-api/).  From this Using Every Noise, a large playlist (of up to 1300 songs) for each genre was, quiered in the and saved to a large data frame. The folloing features were collected and saved to the spotify_df.csv 

- track_id : a spotify primary key; unique for each track
- artist: name of artist
- album: name of album
- trackName: title of track
- acousticness: A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.
- danceability: Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable. 
- duration_ms: The duration of the track in milliseconds.
- energy: a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. 
- instrumentalness: Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context.
- key: The estimated overall key of the track. Integers map to pitches using standard [Pitch Class notation](https://en.wikipedia.org/wiki/Pitch_class) 
- liveness: Detects the presence of an audience in the recording.
- loudness: The overall loudness of a track in decibels (dB). 
- mode: indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.
- speechiness: Speechiness detects the presence of spoken words in a track.
- tempo: BPM of track
- time_signature: An estimated overall time signature of a track. 
- valence: A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. 
- category_id: The Spotify Category ID of the track 
- popularity: The value will be between 0 and 100, with 100 being the most popular. The artist’s popularity is calculated from the popularity of all the artist’s tracks.


The Spotify Web Api provided the following Audio Features for each track [more info here](https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/)



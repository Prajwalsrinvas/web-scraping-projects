# Web Scraping from IMDB to find details of top 100 movies

Using selenium automation to:

1. Go to google.com.
2. Search for top 100 movies.
3. Click the imdb link at the top and get the list of details of 100 movies.
4. The user can enter a number between 1 to 100 and get the movie name.
5. Also the movie details are saved as a screenshot with the movie name as the image name.

![movie]("32. Interstellar (2014).png")

6. Details like name, rating, duration, genre, imdb rating, metascore, description, director, stars, votes and gross of all 100 movies is stored as a dataframe.
7. The dataframe containing all information of all 100 movies is also stored as a csv file.
8. Data analysis can be done using the data if wanted. An an example, directors who directed most movies in the top 100 list, along with the movies they directed is shown.


### Notes:
- For some movies, some data will be unavailable. So in such cases, we ignore that particular movie and move on to scrape data from the next movie.
- This could have also been done using BeautifulSoup (and might even be faster!), but I did it using selenium just as a learning experiment.

### Video Demonstration:
<div style="width:100%;height:0px;position:relative;padding-bottom:56.250%;"><iframe src="https://streamable.com/e/yrzzss" frameborder="0" width="100%" height="100%" allowfullscreen style="width:100%;height:100%;position:absolute;left:0px;top:0px;overflow:hidden;"></iframe></div>


# Web Scraping Elon Musk's tweets from twitter!

### [Video Demonstration](https://streamable.com/kud8mt)

Using selenium automation to:

- Go to twitter, enter username and password and click login.
- Wait for search bar to show up, enter 'Elon Musk' (or any person whose tweets you want to scrape) and click enter.
- Switch over to the 'people' tab so that only the twitter profiles are displayed and click on the first profile.
- Scrape tweets, time of tweet and number of replies, retweets and likes (only for the tweets whose <br> twitter handle matches the person's twitter handle) using BeautifulSoup.
- Store all the scraped data (367 tweets in this case) to a dataframe using pandas.
- The dataframe containing all details is also stored as a [csv file](https://github.com/Prajwalsrinvas/web-scraping-projects/blob/main/10.%20Twitter%20Scraper/elon%20musk's%20tweets.csv) for further use if needed.

### First 5 rows containing Elon's tweets:
![First 5 rows](https://github.com/Prajwalsrinvas/web-scraping-projects/blob/main/10.%20Twitter%20Scraper/fewrows.png)

### Note:
- Twitter does not have a 'next page' button or a 'see more' button that loads up more tweets.
- Instead it uses infinite scrolling i.e the more you scroll down the page, the more tweets are displayed (untill all tweets are shown).
- But unlike other websites which use infinite scrolling, once you scroll down in twitter, the previous tweets data is replaced by the new tweets data.
- In other sites, both old data and new data is available even if you scroll all the way down the page.
- Only tweets are included and retweets are skipped.
- The twitter API could have also been used (would be easier and faster too!) but I used selenium and BeautifulSoup instead, just as a learning experiment.



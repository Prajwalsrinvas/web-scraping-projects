# Web Scraping Data Scientist Jobs in Bangalore from indeed.com!

### [Video Demonstration](https://streamable.com/51mua6)

Using selenium automation to:

- Go to indeed.com, enter job role and job location and click enter.
- Scrape Job Title, Company, Location, Salary, Requirements, Date Posted, Remote, and Job Link from the page using BeautifulSoup.
- Go to the next page and repeat the process untill the last page is reached.
- Store all the scraped data (495 jobs in this case) to a dataframe using pandas.
- The dataframe containing all details is also stored as a [csv file](https://github.com/Prajwalsrinvas/web-scraping-projects/blob/main/11.%20Indeed%20Scraper/Data%20Scientist%20jobs%20in%20Bangalore.csv) for further use if needed.


### First 5 rows showing Data Scientist jobs in Bangalore:
![First 5 rows](https://github.com/Prajwalsrinvas/web-scraping-projects/blob/main/11.%20Indeed%20Scraper/fewjobs.png)


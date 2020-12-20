# Web Scraping from Nike to find details of all products that are on a sale

### [Video Demonstration](https://streamable.com/slbami)

Using selenium automation to:

- Go to the [page](https://www.nike.com/in/w/sale-3yaep) which displays all products currently on sale on nike.com.
- This website does not have a 'next page' button or a 'see more' button that loads up more products.
- Instead it uses infinite scrolling i.e the more you scroll down the page, the more products are displayed (untill all products are shown).
- The page is scrolled all the way down automatically using selenium so that all products are displayed.
- Details like Product name, Description, Colours, Price, Sale Price, Discount and Product Link of all products is scraped using BeautifulSoup 
  (313 products in this case) and stored as a dataframe using pandas.
- The dataframe containing all details is also stored as a [csv file](https://github.com/Prajwalsrinvas/web-scraping-projects/blob/main/8.%20Nike%20Scraper/nike%20sale%20data.csv)   for further use if needed.

### Note:
- For some products, some data will be unavailable. So in such cases, we ignore that particular product and move on to scrape data from the next product.



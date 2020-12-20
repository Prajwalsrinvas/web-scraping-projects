# Web Scraping from Union Los Angeles site to find details of all outerwear products 

### [Video Demonstration](https://streamable.com/cenelt)

Using selenium automation to:

- Go to the [page](https://store.unionlosangeles.com/collections/outerwear) which displays all outerwear products.
- This website does not have a 'next page' button or a 'see more' button that loads up more products.
- Instead it uses infinite scrolling i.e the more you scroll down the page, the more products are displayed (untill all products are shown).
- The page is scrolled all the way down automatically using selenium so that all products are displayed.
- Details like Product Name, Designer Name, Price, and Product Link of all products is scraped using BeautifulSoup 
  (99 products in this case) and stored as a dataframe using pandas.
- The dataframe containing all details is also stored as a [csv file](https://github.com/Prajwalsrinvas/web-scraping-projects/blob/main/9.%20Union%20Los%20Angeles%20Scraper/union%20los%20angeles%20data.csv) for further use if needed.
- Data analysis on the products can also be done.For example, I found out that the most expensive product was ['Varsity SB JKT (Wool)'](	https://store.unionlosangeles.com/products/varsity-sb-jkt-wool-1) which was $4,647!

### Note:
- For some products, some data will be unavailable. So in such cases, we ignore that particular product and move on to scrape data from the next product.



# GitHub jobs API 👔

- Learned to interact with the [GitHub jobs API](https://jobs.github.com/api) using python and the requests library.
- Explored different types of endpoints and responses of the API.
- The GitHub Jobs API allows you to search, and view jobs with JSON over HTTP.
- The API also supports pagination. /positions.json, for example, will only return 50 positions at a time.
- You can paginate results by adding a page parameter to your queries.Pagination starts by default at 0.

- Created a dataframe containing all (133) job listings.
- Some columns had data with html tags. The html tags were removed using [html.remove_tags](https://w3lib.readthedocs.io/en/latest/w3lib.html#w3lib.html.remove_tags) function from the [w3lib](https://w3lib.readthedocs.io/en/latest/w3lib.html) library.
- Exported jobs data as a [csv file](https://github.com/Prajwalsrinvas/web-scraping-projects/blob/main/12.%20API%20Projects/4.github%20jobs%20API/github_jobs_data.csv) for any further use.

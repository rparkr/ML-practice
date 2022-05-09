# Python Machine Learning Class

Files and data I created for my Machine Learning in Python course at Brigham Young University, taken Fall 2021.


---

🚧 This repo is still a work in progress as I update the files to make improvements and incorporate new techniques I've learned. 🚧


## Files in this repository
**Wikipedia Data Retrieval.ipynb**

Purpose: gather data on which to practice machine learning techniques.

This is the Jupyter notebook with my code to gather, process, and store data from Wikipedia.
It retrieves any number of randomly selected articles from Wikipedia and organizes data from those pages for further analysis.

**Wikipedia_data.csv**

I obtained this data through Wikipedia's API.
File contains 1035 records, each record describes a randomly selected article from Wikipedia.
There are about 23 columns describing each article, though not all articles have values in each column.
Also note that some columns contain multiple values in a single cell. These values are built as Python lists, 
and can be parsed to obtain the list of individual values.
* Page ID
* Title 
* URL 
* Page Views, last 60 days
* Description, local
* Description, Wikidata
* Alias
* Label 
* Size in Bytes
* Available languages count
* Categories
* Category URLs
* Page Image Name
* Page Image URL 
* Images
* Image URLs
* Location, Latitude
* Location, Longitude
* Location, Distance to BYU
* Location, Name
* Location, Type
* Location, Country
* Location, Region
* Location, Globe 

**Wikipedia_other_info.csv**

**⚠ NOTE ⚠, 2-Nov-2021: only the first ~200 records are properly processed.** The error likely relates to saving article text in a .csv file, where some commas are not escaped, so they are treated as delimeters and separate the article text between multiple columns.

Purpose: enhance data obtained through Wikipedia's API (Wikipedia_data.csv) with additional columns about each article in the dataset. 
I obtained this data using webscraping with Python's `requests` and `BeautifulSoup` libraries.
File contains 1035 records, each record describes the randomly selected Wikipedia articles from the Wikipedia_data.csv dataset.
Columns:
* Page ID
* Page URL
* Page Info URL
* Page text (i.e., the contents of the Wikipedia article)
* Redirects (the number of redirects to the page)
* Date created
* Last edited date
* Total edits
* Recent edits (in past 30 days)
* Recent authors (in past 30 days)
© 2021 GitHub, Inc.
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About

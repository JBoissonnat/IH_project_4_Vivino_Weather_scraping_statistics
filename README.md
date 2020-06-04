# Ironhack project 4 Vivino Weather scraping statistics

![GitHub Logo](https://lh3.googleusercontent.com/proxy/nzoUqGROtfLUFXp_oESuIMJ2ht8XGF2TA4--YwI2uQx2A5Nm4SLLcorsbXyDoS8tNFJ7eWay-1bgDUKTCTf-NZlPD-iAByFyK5X5GXOoCvSt8J7jWgr9UvZRXIVSOuAe)

### Project description
Group project

The goal in this project was to first scrap data from a database, and then get data from another database and use both together to make simple statistics about a subject. We choosed to work on french wine and vintages, and to get informations about wine quality/ratings from vivino*'s users and compare it with corresponding weather data (temperatures and precipitations).

To simplify our analysis, we choosed to work only on the 10 most frequent vintage area that we found when making scraping tests on the Vivino API. We also worked with bottles and weather data on the period 1998-2017. All of this was to make our 2 sources of data compatible, and because we couldn't scrap the whole vivino database mostly because of time limitations.

Steps of the project :
- Scrap data about bottles from the Vivino API
- Download the adequate weather data from the NCEI**
- Cleaning properly the 2 databases and join them to obtain a unique dataframe
- Getting an overview of the dataset
- A specific analysis on the Bordeaux vintage/station
  - Comparison of ratings and weather data
  - Hypothesis testing

* Vivino is a french websites that allows any users to rate any bottle of wine. The website then provides informations for these bottles on overall quality and other aspects.
** US Gouvernemental Website National Centers for Environmental Information (NCEI)

### Libraries

- pandas
- requests
- json
- time
- matplotlib
- numpy
- seaborn
- scipy

### Code details

OPEN A JUPYTER INSTANCE TO BE ABLE TO READ THE .ipynb FILE HERE ON GITHUB

- The scraping of Vivino uses the API ; lines of code within a loop that call the data for a given number of pages and store it dictionnaries in a dataframe. A function is used to unravel properly the dictionnaries and their content (information about the bottles).
Also every bottle get duplicated 12 times because the weather data is monthly
- A common column between the 2 database is created, and the dataframes are merged on it.
- Columns are cleaned and formated in the new dataframe
  - 4 columns related to vivino ; domain, rating, appelation, region
  - 7 columns related to weather ; station, CLDD (cooling days), HTDD (heating days)
  - 2 time columns ; year and month
- plots for the data exploration are mostly histograms and lines plots and scatterplots made with matplotlib and seaborn
- Hypothesis testing are done with the scipy library, and check hypothesis on ratings and age

### Links

Source page : wine bottle data from vivino https://www.vivino.com/explore?e=eJzLLbI11jNVy83MszVXy02ssDU2UEuutHULUku2dQ0NUiuwNVRLT7MtSyzKTC1JzFHLT7ItSizJzEsvjk8sSy1KTE9Vy7dNSS1OVisviY4FKgZTRgDL1Bz4

weather data from NCEI https://www.ncdc.noaa.gov/cdo-web/

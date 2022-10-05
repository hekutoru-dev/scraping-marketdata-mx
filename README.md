# scraping-marketdata-mx
Small project to scrape data from Mexico demographics information data

# Introduction

As a demographics project, it is required to get information from Mexico: zipcodes, neighborhoods, population and coordinates.

To complete and gather information, it is possible to get this information from public sites on the web. There is one site with some options to extract this information, so I have decided to test this site using web scraping techiniques.

The site is https://www.marketdatamexico.com/es/Estados

At first sight it we can see that the site has information about the 32 states of the Mexican Republic. For each site we have information about each district, and then there is information about each neighborhood.


### Scraping

To be able to perform this scraping we make use of the geckodriver found on https://github.com/mozilla/geckodriver

The information we'll be extracting is:

State, District and Neighborhood.

We'll get the states's name from the main page, which contains all the possible states name to consult.

![States Main](/assets/images/states_main.png)

From each neighborhood we require to get: zipcode, population.

By exploring each neighborhood we can see that all of the have a common structure on the population's info. Either they have the text "habitan alrededor de X personas" or "habitan unas X personas". We want to get this specific number to store on our database. So we'll make use of REGEX to get this information.

### Storage

The scraped information will be stored in a PostgreSQL database.



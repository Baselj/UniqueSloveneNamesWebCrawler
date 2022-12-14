# Read [ITIS](https://www.itis.si/) and create a list with unique Slovene names

![UniqueSloveneNamesWebCrawler](https://github.com/Baselj/UniqueSloveneNamesWebCrawler/blob/main/WebCrawl.jpg)

## Description

Read [Slovene phone book](https://www.itis.si/), insert cities name from [cities.txt](https://github.com/Baselj/UniqueSloveneNamesWebCrawler/blob/main/cities.txt) and list with unique Slovene names.

## Requirements

1. Python 3.10. or higher
2. Chrome browser with ChromeDriver to use with selenium browser automation tool (you need to find appropriate ChromeDriver for your Chrome browser)
3. Install requirements with pip install [requirements.txt](https://github.com/Baselj/UniqueSloveneNamesWebCrawler/blob/main/requirements.txt)

## How do I use it?

1. Script uses Selenium driver to control Chrome web browser, correct version of selenium driver for your Chrome web browser is required. 
2. Create a SeleniumDrivers folder and download latest driver from [ChromeDriver](https://chromedriver.chromium.org/downloads)
3. Required Python packages are documented in requirements.txt, see [instructions how to install packages](https://learn.microsoft.com/en-us/visualstudio/python/managing-required-packages-with-requirements-txt?view=vs-2022)

## Example

Example of name lists can be found in 
 - [Unique names seperated by new line](https://github.com/Baselj/UniqueSloveneNamesWebCrawler/blob/main/name.txt)
 - [Unique names seperated by ;](https://github.com/Baselj/UniqueSloveneNamesWebCrawler/blob/main/namecsv.txt)
 - [All names and surnames](https://github.com/Baselj/UniqueSloveneNamesWebCrawler/blob/main/nameSurname.txt)

## Features

Script uses automated control of Chrome browser, it's designed for long term operation (24 hour of scraping)
 - It goes to Slovene phonebook website,
 - clicks persons buttton,
 - copies the name of the city from cities.txt and clicks search,
 - scrapes through all the pages by name,
 - stores the names in three files,
    - names.txt : unique Slovene names seperated by new line,
    - namecsv.txt : unique Slovene names seperated by ;,
    - nameSurname.txt : all scraped Slovene names and surnames seperated by new line,
 - due to memory issues with long term Chrome operation, some configurations changes were added to Chrome via Options() object as well as restart of the browser with cache clearing every half hour. The script can operate for 24+ hours without crashing,
 - if the browser crashes the script resumes work from the previous time (it keeps adding names and deleting cities already scraped)

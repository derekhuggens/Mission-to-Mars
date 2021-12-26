# Mission-to-Mars
Webscraping and Development with Splinter, BS4, Chrome Dev Tools, Flask and MongoDB.

## Dependencies Needed

### This project used the following dependencies:

#### `app.py` File for setting up Flask and PyMongo to connect to MongoDB and initialize the homepage `index.html` as `"/"` as well as the `"/scrape"` route that is made into a button on the homepage.

`from flask import Flask, render_template, redirect, url_for
from flask_pymongo import PyMongo
import scraping`

#### `scraping.py` File for initializing Splinter for automated browsing, BS4 for HTML scraping, and webdriver for browser commands. Four different functions were written to visit 4 websites, parse each websites' HTML into soup objects, get desired elements such as Mars news titles, Mars news paragraphs, feautured JPL image, Mars table facts, and Mars hemisphere image URLs and their titles. A final function, `def scrape_all()`, was written to run the previous four functions and store the returned data into a dictionary for MongoDB. This `def scrape_all()` function was used within `app.py` inside the `"/scrape"` Flask route to add information into the MongoDB `mars_data` database, and later coded into `index.html` as a button to run the HTML scraping code.

`from splinter import Browser
from bs4 import BeautifulSoup as soup
from webdriver_manager.chrome import ChromeDriverManager
import pandas as pd
import datetime as dt`


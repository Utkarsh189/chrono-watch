# chrono-watch
Table of Contents

•	Introduction

•	Installation

  o	Prerequisites
  
  o	Instructions
  
•	Usage

•	Customization

  o	Changing the Start URL
  
  o	Changing the Output Filename
  
•	Output Format

Introduction

Welcome to the Scrapy Chrono24 Watch Scraper project! This repository contains a Scrapy spider designed to extract watch details from chrono24.com and save the data in JSON format. Chrono24 is a popular platform for buying and selling watches, and this scraper enables you to collect watch information for various purposes, including analysis, building a watch collection database, or any other creative projects you have in mind.

Installation

Prerequisites

•	Python 3.6 or higher

•	Scrapy (install using pip install scrapy)
Instructions

Clone this repository to your local machine using Git:

git clone https://github.com/adil6572/chrono24-watch-scraper.git

cd chrono24-watch-scraper

Install the required Python packages:

pip install scrapy

Usage

To use the Chrono24 Watch Scraper, follow these steps:

Open the Scrapy spider configuration file (watch.py) and customize it as needed.
Run the scraper

scrapy crawl watch_detail_scraper

The scraped data will be saved in JSON format in the specified output file.

Customization

Changing the Start URL

To scrape a different page on Chrono24 or another website, open the spider's configuration file (watch.py) and change the start_urls list. Replace the default URL with the one you want to scrape:

start_urls = ['https://www.chrono24.com/patekphilippe/index.htm']  # Replace with your target URL

Changing the Output Filename

You can change the name of the output JSON file in the FEEDS setting. Open the spider's configuration file and update the FEEDS dictionary with your desired filename:

custom_settings = {
    'FEEDS': {
        'output.json': {  # Replace 'output.json' with your preferred filename
            'format': 'json',
            'overwrite': True,
        },
    },
}

Output Format

The scraped data will be saved in a JSON file with items structured as follows:

{
  "watch_id": "29315694",
  "watch_title": "A. Lange & Söhne Lange 1",
  "watch_price": "29950",
  "watch_details": {
    "Basic Info": {
      "Listing code": "HGC4U1",
      "Dealer product code": "4813572",
      "Movement": "Manual winding",
      "Case material": "Yellow gold",
      "Year of production": "Unknown",
      "Gender": "Men's watch/Unisex",
      "Location": "United States of America, Pennsylvania",
      "Price": "$29,950",
      "Availability": "Item is in stock"
    },
    "Caliber": {
      "Movement": "Manual winding",
      "Power reserve": "72 h"
    },
    "Case": {
      "Case material": "Yellow gold",
      "Water resistance": "3 ATM",
      "Crystal": "Sapphire crystal",
      "Dial": "Silver",
      "Dial numerals": "Roman numerals"
    },
    "Bracelet/strap": {
      "Bracelet color": "Brown",
      "Clasp": "Buckle"
    }
  }
}



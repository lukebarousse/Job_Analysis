# LinkedIn Job Posting Scraper
```
A collection of Jupyter Notebooks that:
    1) LinkedIn.ipynb - Scrape Job Postings from LinkedIn
    2) Job_Analysis.ipynb - Analyze scraped data
```
# ✨ Background

I was looking to better understand what skills where being requested of *entry-level data analysts* for the subscribers of my YouTube channel.  I felt the best place to start was LinkedIn job postings, so this is my start at this project.

[Check out this video for more](https://www.youtube.com/watch?v=Zcy-ND_4ydQ)

# 🛑 Disclaimer

NOTICE: The use of robots or other automated means to access LinkedIn without the express permission of LinkedIn is STRICTLY PROHIBITED.  
[More details here](https://www.linkedin.com/robots.txt)

IMPORTANT NOTE: LinkedIn will BLOCK you from searching if you are scraping too much data and/or you don't have permission. 

# 🏁 Overview

##  🤖 LinkedIn.ipynb - Job Scraper
Overview: This script scrapes LinkedIn job data.  Using a selenium web driver for chrome it launches a headless browser and then scrapes all the relevant job details.

NOTE: LinkedIn only allows you to view 40 pages of a particular search term.  Because of this you can only scrape 1000 jobs per search term

### To begin

Prerequisites: Python installed and environment established with packages from *requirements.txt* installed.

1) [Download your appropriate chromedriver](https://chromedriver.chromium.org/downloads) and save it to this repository.

2) Create a new file called *.env* with your login credentials, also saved to this repository.
```
LINKEDIN_USERNAME=email.address@mail.com
LINKEDIN_PASSWORD=password
```

3) Adjust your search criteria for what you want to search for in the .ipynb file
```
# Accepts a list of search keywords to analyze for
search_keywords = ['Data Analyst', 'Data Scientist', 'Data Engineer']

# Accepts one location.. if spaces in name use '%20'
search_location = "United%20States"

# only searches remote positions currently... need to update code for this to search non-remote
search_remote = "true" # filter for remote positions

# this is code to search for past 24 hours, you would have to look at the url to investigate other search periods
search_posted = "r86400" # filter for past 24 hours
```

4) Run "All Cells" on .ipynb  
    a) In the *log* directory, a *.log* file is created that capture the progress of the data scraping and reports any errors  
    b) in the *output* directory, a *.csv* fils is created for this date.  
    NOTE: Script deletes any *.csv* files that have the same date, so as written you can only run this script once per day.

##  📊 Job_Analysis.ipynb - CSV Compiler and Analyzer
Overview: This script analyzes your csv files in the *output* directory

Prerequisites: Have at least one *.csv* file in the output folder to analyze.

1) Modify code to your liking  
2) Run "All Cells" on this .ipynb
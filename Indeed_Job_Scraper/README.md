# Indeed_Job_Scraper

- Given the Skill and the Location, this script will scrape the Indeed website for the Jobs that match the skill and location provided by the User. The Number of Pages to Scrape the site is also given by the User.

- The matched jobs are then written to a CSV file at the file path given by the User.

- The Details of Jobs such as Job Name, Company Name, Location, Link to the Job, Date when the job was posted are shown in the CSV file.

  ![Indeed Job Scraper](https://raw.githubusercontent.com/Ram-95/Python_Applications/master/Indeed_job_scraper/Indeed_GIF.gif)

# Web Scraping Indeed.com for Job Listings:

  import requests
  
  from bs4 import BeautifulSoup
  
  url = "https://www.indeed.com/jobs?q=Python+developer"
  
  page = requests.get(url)
  
  soup = BeautifulSoup(page.text, 'html.parser')
  
'''Parse the job listings and store them in a data structure.'''
  
  job_listings = []
  
  Extract relevant information (job title, company, location, salary, etc.) from the HTML.
  
  Store the data in a Python data structure (e.g., a list of dictionaries).

# Storing Scraped Data in MongoDB:

   from pymongo import MongoClient

  client = MongoClient('mongodb://localhost:27017')
  
  db = client['your_database']
  
  collection = db['job_listings']

  Store the job listings in the MongoDB collection.

We can use the pymongo library to connect to a MongoDB database and store the scraped job listings. 

 # Creating a Django Admin Panel: [shell]

  django-admin startproject job_search_project
  
  Create a Django app for job listings:  [shell]
  
  python manage.py startapp job_listings 

# Calculating the Average Salary Using NumPy:

   import numpy as np

   Query the MongoDB database to retrieve salary data.

   Calculate the average salary.
   
   salaries = [job['salary'] for job in job_listings]  # Replace with actual salary data.
   
   average_salary = np.mean(salaries)



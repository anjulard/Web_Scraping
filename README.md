# Web_Scraping
Beautiful Soup: Build a Web Scraper With Python

## What is Web Scraping ?
Web scraping is a process of collecting data automatically from the Internet. This is a very useful process for research purposes. Imagine we need some latest data about a particular domain (e.g. Healthcare) to train an AI-based application. When we try to get the information manually, we might spend a lot of time clicking, scrolling, and searching, especially if we need large amounts of data from websites that are regularly updated with new content. Automatic Web Scraping is a better solution for this type of situations.

## Use Cases

- Market Researches
- Research and development applications
- E-Commerce Portals
- Social Media Analysis

## How to do Web Scraping

### Step 1 : Inspect the Data source
The first step is to select the website that you want to scrape. That should be the first step for any web scraping project. We need to understand the site structure to extract the information that’s relevant for our purpose. We can use "developer tool" to understand the website structure. Start by opening the site we want to scrape with our favorite browser. 

### Step 2 : Scrape HTML Content From a Page
First, you’ll want to get the site’s HTML code into your Python script so that you can interact with it. For this task, you’ll use Python’s requests library.

Create a virtual environment for your project before you install any external package. Activate your new virtual environment, then type the following command in your terminal to install the external requests library:

    $ python -m pip install requests
Then you can retrieve the HTML data of a particular web page using below code segment. Use your favorite IDE.

    import requests

    URL = "https://realpython.github.io/fake-jobs/"
    page = requests.get(URL)

    print(page.text)
  
  ### Step 3 : Parse HTML Code With Beautiful Soup
  Beautiful Soup is a Python library for parsing structured data. It allows you to interact with HTML in a similar way to how you interact with a web page using developer tools.
  
    python -m pip install beautifulsoup4
Then, import the library in your Python script and create a Beautiful Soup object:

    import requests
    from bs4 import BeautifulSoup

    URL = "https://realpython.github.io/fake-jobs/"
    page = requests.get(URL)
    soup = BeautifulSoup(page.content, "html.parser")
    
 Beautiful Soup allows you to find that specific HTML element by its ID:
 
    results = soup.find(id="ResultsContainer")
    
For easier viewing, you can prettify any Beautiful Soup object when you print it out.

    print(results.prettify())
    
Pass a Function to a Beautiful Soup Method:
In addition to strings, you can sometimes pass functions as arguments to Beautiful Soup methods. You can change the previous line of code to use a function instead:

    python_jobs = results.find_all(
        "h2", string=lambda text: "python" in text.lower()
    )

    
## Library used for web scrapping

- Selenium
    Selenium is an open-source automated testing library. It is used to check browser activities. To install this library, type the following command in your terminal.
    
    pip install selenium  
    
It is good to use the PyCharm IDE.

- Pandas
    
    Pandas library is used for data manipulation and analysis. It is used to extract the data and store it in the desired format.

- BeautifulSoup
    BeautifulSoup is a Python library that is used to pull data of HTML and XML files. It is mainly designed for web scrapping. 
    It works with the parser to provide a natural way of navigating, searching, and modifying the parse tree. The latest version of BeautifulSoup is 4.8.1.

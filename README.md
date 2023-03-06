# Scraping-a-website-with-Python-using-BeautifulSoup-and-Requests-libraries

First of all what is web scraping, In today’s competitive world, everybody is looking for ways to innovate and make use of new technologies. Web scraping (also called web data extraction or data scraping) is an automated process that extracts data from a website and exports it in a structured format. But before scraping a website in python we need to install the python it self and then we need to install and import some libraries which are Requests and BeautifulSoup using command prompt, anaconda prompt and more. To install them we use this command:

```py
#using command prompt
pip install requests BeautifulSoap
#using anaconda prompt
conda install requests BeautifulSoap
```

after we successfully install the libraries then we import them in order to use them for the web scraping:

```py
#importing the required libraries
import requests
from bs4 import BeautifulSoap
```

Request library enable us to get the content of the page as HTML while BeautifulSoap allows us to parse the HTML.

Normally anybody trying to scrape a website already have a link of the web site he/she is trying to scrape let assume am scraping this website: link here we are trying to scrape Daily Trust web page, we can create a BeautifulSoap objects so that we can use to navigate the content of the page as follows:

```py
url = 'https://dailytrust.com/promise-for-credible-governorship-election-is-medicine-after-death-atiku-tells-inec/'
response = requests.get(url)
soup = BeautifulSoap(response.content, 'html.parser')
soup.prettify()
```
The above program shows that we declared the url then we create response using the get method of request then we pass the content attribute of the response object to BeautifulSoap so that we can create a soap object that we can use to navigate through the content of the page. The prettify method is used to show the basic structure of the web page as this can help in locating the exact content needed.

lets follow the approach:
```py
paragraphs = soup.find_all('p')
print(soup.title)
for paragraph in paragraphs:
    if not paragraph.find_all('a'):
        print(paragraph.get_tech())
```
We declare a variable name paragraphs and then find all the p tags using find all method. As you can see soup object title attribute was printed and the next step I made is that I loop through each and every item in the paragraphs.

I print the title attribute of the soup object and then loop through each item in the paragraphs variable and print, this gives the entire content of the article. I discovered that the hyperlinked titles of related articles where included and I removed them by excluding all p tags that contained a tags.


Below is the output, giving the complete text of the article:[ Output](https://github.com/Mudacrixxz/Scraping-a-website-with-Python-using-BeautifulSoup-and-Requests-libraries./blob/main/Output.json)

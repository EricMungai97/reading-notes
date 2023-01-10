# Web Scraping

[Source](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)

`Web scraping` is a technique to automatically access and extract large amounts of information from a website.

**Things to Note When Web Scraping**

* Read through the website’s Terms and Conditions to understand how you can legally use the data

* Make sure you are not downloading data at too rapid a rate because this may break the website.

First thing you need to is locate the links to the files we want to download.

**Python Code**

Import the following libraries

```
import requests
import urllib.request
import time
from bs4 import BeautifulSoup
```

Create a url variable and assign it the url you want to scrape from.

```
url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```

Next, parse the HTML with `BeautifulSoup` to get a nice nested data structure

```
soup = BeautifulSoup(response.text, “html.parser”)
```

We then use the method .findAll to locate all of our `<a>` tags .

```
soup.findAll('a')
```

This codes give us every line of code that has an `<a>`

Next we extract the actual link we want

```
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]
```
We then use our urllib.request library to download the file path tou our computer. We provide request.urlretrieve with two parameters: file url and the filename.

```
download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])
```

We should include this line of code next to esnure we are not spamming the website with request.

`time.sleep(1)`

Example to download an entire set of data files with a for loop.

```
# Import libraries
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

# Set the URL you want to webscrape from
url = 'http://web.mta.info/developers/turnstile.html'

# Connect to the URL
response = requests.get(url)

# Parse HTML and save to BeautifulSoup object¶
soup = BeautifulSoup(response.text, "html.parser")

# To download the whole data set, let's do a for loop through all a tags
line_count = 1 #variable to track what line you are on
for one_a_tag in soup.findAll('a'):  #'a' tags are for links
    if line_count >= 36: #code for text files starts at line 36
        link = one_a_tag['href']
        download_url = 'http://web.mta.info/developers/'+ link
        urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:]) 
        time.sleep(1) #pause the code for a sec
    #add 1 for next line
    line_count +=1
```

[Source](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)

## How to web scrape without getting blocked

1.Respect Robots.txt

If it contains lines like the ones shown below, it means the site doesn’t like and does not want to be scraped.

`User-agent: *`

`Disallow:/`



2. Make the crawling slower, do not slam the server, treat websites nicely.

Make your spider look real, by mimicking human actions. Put some random programmatic `sleep calls` in between requests, add some delays after crawling a small number of pages and choose the lowest number of concurrent requests possible.

3. Do not follow the same crawling pattern.

Incorporate some random clicks on the page, mouse movements and random actions that will make a spider look like a human.

4. Make requests through Proxies and rotate them as needed.

Multiple requests coming from the same IP will lead you to get blocked, which is why we need to use multiple addresses. Create a pool of IPs that you can use and use random ones for each request. Along with this, you have to spread a handful of requests across multiple IPs.
There are several methods that can change your outgoing IP.
, VPNs, Free Proxies, Shared Proxies, Private Proxies etc.
   

5. Rotate User Agents and corresponding HTTP Request Headers between requests.

A user agent is a tool that tells the server which web browser is being used

The only way to make your User-Agent appear more real and bypass detection is to fake the user agent. Most web scrapers do not have a User Agent by default, and you need to add that yourself.

6. Use a headless browser like Puppeteer, Selenium or Playwright

7. Beware of Honey Pot Traps

`Honeypots` are systems set up to lure hackers and detect any hacking attempts that try to gain information. It is usually an application that imitates the behavior of a real system. Some websites install honeypots, which are links invisible to normal users but can be seen by web scrapers.

8. Check if Website is Changing Layouts

9. Avoid scraping data behind a login

10. Use Captcha Solving Services


## How websites detect and block webscraping

1. Unusual traffic/high download rate

2. Repetitive tasks performed on websites in the same browsing pattern.

3. Checking if you are a real browser.

4. Detection through honeypots.

## How to address this detection and avoid web getting blocked

Investigate the anti-scraping mechanisms used by the site and build the spider  accordingly.

## How to detect if a website has blocked or banned you

If any of the following signs appear on the site that you are crawling:

1. Captcha pages

2. Unusual content delivery delays

3. Frequent response with HTTP 404, 301 or 50x errors
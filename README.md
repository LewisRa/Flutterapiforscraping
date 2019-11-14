# Flutterapiforscraping

To run flask: 
python app.py

If you navigate to http://127.0.0.1:5000/, you will recieve 'Not Found:
The requested URL was not found on the server. If you entered the URL manually please check your spelling and try again.' page because there is no '/' url in this Flask app thus far.

If you navigate to http://127.0.0.1:5000/api/v1, you will recieve a 'Bad Request:
The browser (or proxy) sent a request that this server could not understand.' because Flask is expecting a query. 

Thus, to recieve the results you are looking for, navigate to http://127.0.0.1:5000/api/v1/?query=inspirational for example to recieve all  quotes from a "inspirational" search query on https://www.brainyquote.com

![](images/beforeJsonViewer.png)
## JSON Viewer
https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh?hl=en

chrome://extensions/

![](images/afterJsonViewer.png)

### Notes: 
1. An example of a URI is https://www.brainyquote.com while https://www.brainyquote.com/quotes/steve_jobs_416859?src=t_inspirational is a URL. Thus, every URL is a URI but not every URI is a URL. Because a URL is a form of identification, it belongs under a subset of URI, but URI's aren't always going to show where a resource can be found.
2. query = str(request.args['query']) takes "inspirational" string from http://127.0.0.1:5000/api/v1/?query=inspirational and stores it in the variable query.
3. Lines 14-17 replaces blank space in query with  a '+' sign. Thus, if query is 'Oprah Winfrey' this step makes it  'Oprah+Winfrey'
4. Line 19-21 turns 'inspirational' query from api url to https://www.brainyquote.com/search_results?q=inspirational 
5. Line 23 requests the https://www.brainyquote.com/search_results?q=inspirational source code into python.
6.(line 25) quotes_links = soup.find_all('a', {'class': 'b-qt'}) is used is extract the list of quotes link to each indiviual picture on page given text and attrs {} in page source code.
7. Every link in quotes_links the following code will run:

 quote_soup = BeautifulSoup(quote_content, 'html.parser') initalizes another BeautifulSoup Parser object to scrape each quote page.

'''<p class="bq_fq_a"><br>
<a href="/authors/steve-jobs-quotes" class="qa_416859 oncl_a">Steve Jobs</a><br>
</p><br>'''

'''<a href="/quotes/helen_keller_101301" class="b-qt qt_101301 oncl_q" title="view quote">The best and most beautiful things in the world cannot be seen or even touched - they must be felt with the heart.</a>'''
### Fix Photos

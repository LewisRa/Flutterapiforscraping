# Flutterapiforscraping

To run flask: 
python app.py

If you navigate to http://127.0.0.1:5000/, you will recieve 'Not Found:
The requested URL was not found on the server. If you entered the URL manually please check your spelling and try again.' page because there is no '/' url in this Flask app thus far.

If you navigate to http://127.0.0.1:5000/api/v1, you will recieve a 'Bad Request:
The browser (or proxy) sent a request that this server could not understand.' because Flask is expecting a query. 

Thus, to recieve the results you are looking for, navigate to http://127.0.0.1:5000/api/v1/?query=inspirational for example to recieve all  quotes from a "inspirational" search query on https://www.brainyquote.com

![](images/beforeJsonViewer.png)


https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh?hl=en

chrome://extensions/

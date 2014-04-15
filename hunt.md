##HTTP Response Scavenger Hunt

####Assignment

For this Lab you will be making HTTP requests in your terminal using **curl** and scavenging for data in the response you get back. **curl** is short for "Client for URL's" and is a tool that allows us to make HTTP requests in our terminal.  

___________________________________________

**Phase 1: Make a GET request to google**

In terminal:

`curl -v https://www.google.com`

Find your response header

  **1.** What status did you get back?  
  200 OK
  **2.** What content-type did you get back?  
  text/html
  **3.** What came after the key "Set-Cookie"?  
  Set-Cookie: PREF=ID=d1b1b8b9d123797b:FF=0:TM=1397598224:LM=1397598224:S=CVBAIfU4A7-Kh_In; expires=Thu, 14-Apr-2016 21:43:44 GMT; path=/; domain=.google.com
< Set-Cookie: NID=67=oaY8oOn6VOyd-7jUgP_yJFNsL1f-K7RXQLAKWtix-oVYd1mnWpPlekd6KEuyQpRHkfrfUfVDQm_db0rVP5DwAJVf-n21AVRiq8rJaUfqZ70aHpY3YZ8t4J_JF1yZ_nD8; expires=Wed, 15-Oct-2014 21:43:44 GMT; path=/; domain=.google.com; HttpOnly

  **4.** What date did this request come back on?  
  < Date: Tue, 15 Apr 2014 21:43:44 GMT
  **5.** What came after the key "Transfer-Encoding?"  
   Transfer-Encoding: chunked

Find your response body

  **1.** What was the first line in your response body?  
  <!doctype html><html itemscope="" itemtype="http://schema.org/WebPage" lang="en"><head>

_______________________________________________

**Phase 2: Make a GET request to the OMDBAPI**

In terminal:

`curl -v http://www.omdbapi.com`  

Find your response header

  **1.** What status did you get back?  
  HTTP/1.1 200 OK
  **2.** What content-type did you get back?  
  Content-Type: text/html; charset=utf-8
  **3.** What was your content length?  
  Content-Length: 11859
  **4.** What date did this request come back on?  
   Date: Tue, 15 Apr 2014 21:46:00 GMT

Find your response body

  **1.** What was the first line in your response body?  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">  

___________________________________________________

**Phase 3: Make a GET request to the OMDBAPI with parameters**

In terminal:  

`curl -v http://www.omdbapi.com/?s=Titanic`

Find your response header

  **1.** What status did you get back?  
  200 OK

  **2.** What content-type did you get back?
  text/html
  **3.** What was your content length?  
792
Find your response body
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

  **1.** Look at the data that came back. What data structures do these look like? 
  hash function that looks like area 

  **2.** What year did Titanic II come out?  
1997

_______________________________________________________________________

**Phase 4: Make a GET request to the OMDBAPI with different parameters**

Now search for one of your favorite movies.

`curl -v http://www.omdbapi.com/?t=<insert your favorite movie here>`

*If the title of your favorite movie has spaces, replace these with %20*  
i.e. `curl -v http://www.omdbapi.com/?t=the%20matrix` 

Find the response header  

  **1.** What was the Cache-Control? 
  no-cache 
  **2.** What value is after the key Expires?  
 -1

Find the response body

  **1.** What year was your favorite movie released? 
  1999 
  **2.** What was your favorite movie rated?  
Rate R
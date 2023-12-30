# Google Dorks



### Google hacking
Google hacking is using different google operators to refine search results.
Use of  a search engine, such as google, to locate a security vulnerability on the internet.

### Downloading Movie
```md
Movie+name -inurl:(htm|html|php|pls|txt) intitle:index.of "last modified" (mp4|wma| acc|avi)
```

### View Android Camera Photos:
```md
intitle:"Index of" "DCIM"
```

## Google Operators 
### Basic Operators
`+, -, ., *, "", |, OR`
### Advanced Operators
allintext:, allintilte:, allinurl:, cache:, define:, filetype:, info:, intext:, intitle:, inurl:, link:, phonebook:, related:, site:, numrange:

### Advanced Operators "Filetype"
find documents with specified extensions
examples:
    Ethical Hacking filetype:txt
    Networking filetype:ppt
    site:owasp.org filetype:pdf


### filtering Usernames and passwords
>Example:
    username password @facebook.com filetype:txt
    username password @gmail.com filetype:txt
    username password @yahoo.com filetype:txt
    username password @twitter.com filetype:txt

### Advanced Operators "Intitle"
`intitle: search_term`
find search term within the title of a webpage
Example:
    intitle: owasp
`Allintitle: search_term1 search_term2 search_term3`
find multiple search terms in the web pages with the title that includes all those words
these operators are specifically used to find the directory lists
Example:
    intitle: Index.of "parent directory"
    intitle: Index.of "movies"

### Hacking security cameras
```md
intitle:"IVISTA.main.page"
"please visit" intitle:"i-character console" copyright
"icodesystems"
intitle:"Live View / - AXIS | inurl:view/view.shtnl
```

### Advanced Operators "Inurl:"
`inurl:search_term`
find search term in url.
`allinurl: search_term1 search_term2 search_term3`
find multiple search terms in a url.
Examples:
    inurl: admin
    allinurl: admin login

### Hacking Printers
```md
inurl:websearch/mainframe.cgi
```

### hacking webcam
```md
inurl:main.cgilinksys
inurl:"viewframe?mode=motion"
inurl:view/index.shtml
inurl:"toshibaNetwork Camera" User Login
inurl:/view.shtml
```

### Advanced Operators "Intext"
`intext: search_term`
find search term in the text body of a document.
`allintext: search_term1 search_term2 search_term3`
find multiple search terms in the text body of a document.
Example:
    intext: Password
    allintext: Admininstrator login
    site:owasp.org intext:SQL

### Advanced Operators "cache:"
`Cache: URL`
Find the older version of website in google cache
sometimes, even the site has already been updated, the old information might be found in cache
Examples:
    cachedview.com
    web.archive.org

### Advanced operators "link:"
`link: URL`
find the web pages having a link to the specified url.
    Related: URL
find the webpages that are similar to the specified web page
    info: URL
present some information that google has about that web page
    define: search_term
provide a defination of the words gathered from various online sources

Examples:
    link: abc.com
    related: abc.com
    info: abc.com
    define: abc.com

### Want to see private information
`index.of.DCIMindex.of.backup`

### find only pakistani websites
`site:.pk admin login`

### google hacking database [GHDB]
`www.exploit-db.com`

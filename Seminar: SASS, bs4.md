# SASS, Web Scraping with BeautifulSoup

### What is SASS? 

-   Syntactically Awesome Style Sheets! 

    -    A program which provides a syntax known as .scss, which is an 

        extension of .css 

    -   More syntactic flexibility and precision 

    -   Variables, nesting, inheritance 

-   Browsers can’t understand .scss files, however, so to use them we need to convert them into .css files first using the sass program 



### Using SASS 

● In the terminal: `sass {filename}.scss {filename}.css`This converts the {filename}.scss file into a {filename}.css file that your browser can understand 

● Alternatively: `sass --watch {filename}.scss:{filename}.css` : This tells sass to “watch” for any changes to {filename}.scss and automatically update the corresponding {filename}.css file if necessary 



### Bootstrap

-   Free and open-source framework for sharing existing CSS

-   https://getbootstrap.com/docs/4.1/getting-started/introduction/

-   Very important to read through the documentation and play around with the CSS yourself

-   you can always rewrite the bootstrap sytle, and made tiny edits





# BeautifulSoup

### What is web scraping? 

The computer software technique of extracting information from websites 

-   unstructured data → structured data 
-   HTML → database/spreadsheet 



### What is BeautifulSoup? 

-   Python library for pulling data out of HTML and XML files 
-   Parses and breaks down a HTML page into a tree of objects



### BeautifulSoup objects 

-   Tag
    -   corresponds to HTML tag
    -   has a name
    -   has a dictionary of attributes

```python
soup = BeautifulSoup('<b id="boldest">Extremely bold</b>')
tag = soup.b
tag.name
# u'b'
tag['id']
# u'boldest'
tag.attrs
# {u'id': 'boldest'}
```

-   NavigableString - BeautifulSoup
-   Comment 



(Class_: 由于python中class是保留字)
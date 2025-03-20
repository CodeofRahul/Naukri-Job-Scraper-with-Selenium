# **Introduction to Selenium**

- Selenium is a web browser automation tool.
- It allows us to open browser of our choice and perform tasks as a human being would like:
    - Clicking buttons.
    - Entering information in forms.
    - Searching for information on web pages

Uses a web-driver package that can take control of the browser and mimic user-oriented actions.

## **Beautiful Soup vs Selenium**

**BeautifulSoup**

- A module that can be used for pulling data out of HTML and XML documents.
- Depends heavily on other libraries like requests or urllib for sending web requests.
- Dose not have a document parser; we need to choose one like, `html.parser`, 'HTML5lib'.
- It is difficult to scrap websites which return Java script code.
- It does not automate the web browser. It saves a copy of web page source and then does further processing

**Selenium**

- A tool developed for web application automated testing.
- Can send web requests on its own
- It comes with a parser.
- Loads JavaScript and can help access data behind JavaScript files as well.
- Faster that BeautifulSoup, while interacting with webpages.
- Comes handy when handling Java script featured websites.


## **Getting started with Selenium**

**Setup**

- **Selenium** - we need to install selenium package.

```python
pip install selenium
```

- **Selenium Drivers** - These web drivers enable python to control the browser for interactions.

    - The browser that you will use, chrome or Firefox, should be pre installed.
    - Check the version of your browser.
    - visit - `chromedriver.chromium.org/downloads`
    - Download the version of chromedriver that matches the version of your browser.
    - Keep a check of the path where the chromedriver is downloaded.

## **Locating Web Elements in Selenium**

Selenium offers a wide variety of functions to locate an element on the web page:

- **find_element_by_id**: Uses id to find an element.
- **find_element_by_name**: Uses name to find an element.
- **find_element_by_xpath**: Uses xpath to find and element.
- **find_element_by_tag_name**: Uses tag name to find an element.
- **find_element_by_class_name**: Uses value of class attribute to find an element.

There are other functions as well which help us locate elements on the web page.


## **XPath Syntax**

- **XPath known as the XML** path is a language that helps to query the XML documents. <br>
It consits of expression for a path along with certain conditions to locate a particular element.

- The basic format of Xpath is mentioned below:

![Xpath_Syntax](Images\Xpath_Syntax.png)

## **Types of XPaths**

- There are two types of XPath:
    - Absolute XPath
    - Relative XPath

- **Absolute XPath**: Begins with the single forward slash (/), means we select the element from the root node and go all the way down to the element needed.

```
/html/body/div[2]/div[1]/div/h4[1]/b/html[1]/body[1]/div[2]/h4[1]/b[1]
```

- **Relative XPath**: starts from the middle of the HTML structure. Starts with double forward slash (//) an can search elements anywhere on the webpage without writting the long absolute xpath.

```
//div[@class='featured-box columnsize1']//h4[1]//b[1]
```

## **XPath Functions**

**1) Basic Xpath**: XPath expression select nodes or list of nodes on the basis of attributes like ID, Name, Classname, etc. from the XML document like shown below:

```
XPath= //input[@name='uid']

XPath= //a[@href='http://google.com/']
```

**2) Contains()**: used when the value of any attribute changes dynamically, example, login information. It can find the element with partial text.

for finding 'submit' button where Type= 'submit':

```
XPath= //*[contains(@type, 'sub')]

XPath= //img[contains(@src, 'content')]
```

**3) Using OR & AND**: Here, two conditions are used, whether 1st condition OR 2nd condition should be true. Means any one condition should be true to find the element.

```
XPath= //*[@type='submit' or @name='btnReset']
```

in AND expression, two conditions are used, both condiitons should be true to find the element.
if fails to find element if any one condition is flase.

```
XPath= //input[@type='submit' and @name='btnlogin']
```

**4) starts-with()**: Used to find a web element whose value of an attribute changes on the refresh or on any other dynamic operaiton on the web page.
we mathch the starting text of the attribute to locate an element whose attribute has changed dynamically.

```
XPath= //img[starts-with(@src,'https')]
```

**5) text()**: Used with the text function to locate an element with exact text.

Here, it go anywhere inside the document, irrespective of the tag, but, it must contain a text whose value is Seach Google or type a URL. The asterisk(*) implies any tag with the same
value.

```
XPath= //*[text()='Search Google or type a URL']
```


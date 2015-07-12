============================================================
Building Your First Website: An Introduction to HTML and CSS
============================================================

What is HTML?
=============

* **HTML** or **Hyper Text Markup Language** is "a standardized system for tagging text files to achieve font, color, graphic, and hyperlink effects on World Wide Web pages" ~Google
* Basically, it's used to create the layout of your webpage out of fundamental building blocks.  HTML is the skeleton of your page.

.. note:: You can think of this like the floor plans to a house--where do all the rooms go?  How big are they?  What are their functions?  

What is CSS?
------------

* **CSS** or **Cascading Style Sheets** are "a style sheet language used for describing the look and formatting of a document written in a markup language." ~Google
* CSS is the colors, fonts, alignments, and other aesthetic elements of your webpage.

.. note::  CSS is what gives your HTML structure it's unique beauty--it's the paint color, the shades, the carpet, and so on.  

Now for the fun part!
=====================

.. note:: When an HTTP client (generally a Web browser) requests a URL that points to a directory structure instead of an actual Web page within the directory, the Web server will generally serve a general page, which is often referred to as a main or "index" page.  The traditional filename for such a page is index.html, but most modern HTTP servers offer a configurable list of filenames that the server can use as an index..

Boiler Plate
------------
There are a few tags that are essential to any HTML document


Doctype
-------

**<!DOCTYPE html>**  Declaring your document type will tell your browser which markup language you're using and allow it to parse everything correctly.  It's also case-sensitive!

HTML tag
--------

**<html>** The html tag signals the beginning of your webpage, and is the container for all other elements.  It's sometimes called the "root element"

Head tag
--------

**<head>** The head element is the container for all "head" elements. This provides metadata about your site such as the title, keywords, author, and links to any external pages.
	- <link type="text/css" src="styles.css" rel="stylesheet">
	- <title>Title of your site</title>
	- <meta content="Content" name="author OR keywords OR date, so on">

Body tag
--------
**<body>** The body element marks the beginning of the structure of our webpage

Some Other common tags
----------------------

- *<div>* Div's are the most common way to allocate a box for some use on your webpage.  Whether it's a menu, content, or any other part of your page, it's almost certainly wrapped in a div or two.  
- *<span>* Span's are used if you want to change a specific section of text.  ie. to make a sentence red, you'd use span.
- *<h1>, <h2>...<h6>* Headers, ranging from largest to smallest by default (but this can be overriden).  There can only be one <h1> tag per page. 
- *<p>* Paragraph tag, defines a paragraph
- *<a>* "Anchor" tag, defines a link to something--either a page within your site, an anchor on the page, or an external link.

Is there a tag for x?
---------------------

Probably!  W3schools has a reference page that can answer that question: http://www.w3schools.com/tags/default.asp

On the topic of w3schools: http://www.w3fools.com/

So what about the "styles.css"?
-------------------------------

* Cascading style sheets use Ids, classes, or the elements themselves to style each element of a webpage.  Styles include adding colors, fonts, circles, and other pretty things to your page.

Stylesheets
-----------
  
* CSS styles can be inserted any one of three ways: 
	* Inline
	* Internal Stylesheet
	* External Stylesheet

* External Stylesheets are ideal for most projects because they give you control over multiple elements at a time, allow you to use the same styles in multiple pages on your site, and generally keep your files clean.

Ids
---

If you only want to style one instance of something, use an id. For instance if you have a list, but want the first item to be in green, you would give that item an id.  

.. code-block:: css
	
  #firstlistitem{
	color: green;
	font-size: 24px;
  }

Classes
-------

If you want to style multiple instances of that thing, you would give it a class.  For instance, if you wanted the first three items to be green, you'd give them all a class.

.. code-block:: css
  
  .myparagraphs{
	color: green;
	font-size: 24px;
  }

Elements
--------
If you want all instances of that thing to have the style, you can refer to it by element type.  For instance, we'd define all list items within a div to be green.

.. code-block:: css
 
  li{
	color: green;
	font-size: 24px;
  }

On the subject of colors
------------------------

* There are a few ways to tell CSS what color you'd like to use:
  	* Naming the color
	* Using the first three numbers of the hex value
	* Using the full hex value for more complex or specific colors

	http://www.mathsisfun.com/hexadecimal-decimal-colors.html

.. code-block:: css
  
  #p{
	  color: black;
	  color: #000;
	  color: #000001;
  }

Let's add some CSS to our page!
===============================

HTML and CSS resources
----------------------

* **Mozilla Developer Network** https://developer.mozilla.org/en-US/docs/Web/HTML
* **Codecademy** http://www.codecademy.com/tracks/web
* **HTML.net** http://html.net/
* **A Beginner's Guide to HTML and CSS**  http://learn.shayhowe.com/html-css/

...And many more.  Google will know.


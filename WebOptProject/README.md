# Website Optimization Project

by Aaron Guidry


Introduction
------------

Welcome to the **Website Optimization Project** for the Udacity Front-End Web
Development NanoDegree!  In this file I outline the optimizations that I made
to improve the performance of the 2 websites specified in the project 
declaration:

* Cam's Portfolio (_index.html_)
* Cam's Pizzeria (_pizza.html_)



Getting Started
---------------

To view the **Cam's Portfolio** site, simply open the _**index.html**_ file 
located in the **root** directory in any moder web browser. Similarly, to view
the **Cam's Pizzeria** site, simply open the _**pizza.html**_ file located in 
the **/views** directory.

Browsers that have been verified to work:

* Chrome
* Firefox
* Microsoft Internet Explorer
* Microsoft Edge
* Opera


My Optimizations
-----------

#### HTML/CSS Optimization
* Optimized images using compression
* Switched font from _**Open Sans**_ to _**Arial**_ and remove link to prevent 
loading of web fonts 
* Added _**media**_ attribute to _**print.css**_ stylesheet link to prevent 
loading the file on screens
* Inlined _**style.css**_ inside _**index.html**_ and _**pizza.html**_ rather
than loading a separate css file
* Removed portions of styles within _**style.css**_ that were not needed in the
inline CSS moved inside the HTML
* Removed Google Analytics
* Minified _**bootstrap-grid.css**_ => _**bootstrap-grid.min.css**_ to reduce
the size of the file

#### Moving Pizzas
* Added _**will-change**_ entry to CSS for moving pizza class (_mover_)
* Reduced the number of moving background pizzas from **200** to **56** (7 rows
x 8 columns)
* Moved the document top calculation outside of the for loop within the
_**updatePositions**_ function
* Moved the _**querySelectorAll**_ function outside of the _**updatePositions**_
function and into the _**DOMContentLoaded**_ event listener so that the moving
pizza elements are only selected once after the document is loaded and not every
time _**updatePositions**_ is called
* Moved the _**items**_ variable, which holds the collection of 'moving
pizzas', outside of the _**updatePositions**_ function and into the global
scope so that it can be set a single time on document load and used repeatedly
in the _**updatePositions**_ function

### Resizing Pizzas
* Within the _**changePizzaSizes**_ function I moved the multiple 
_**querySelectorAll**_ calls into a single call outside of the for loop
* Moved the _**dx**_ and _**newwidth**_ calculations outside of the for loop 
since they will be identical for all pizzas
* Moved the check of _**offsetWidth**_ outside of the loop to prevent **Forced
Synchronous Layout (FSL)**










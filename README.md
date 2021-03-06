*Sorry for the mess, this README document is currently in progress ...*

#columnreader.js

This is JavaScript and simple CSS to display text in multiple columns, with horizonatal scrolling, that responds to the browser window or mobile device by displaying more or fewer columns as they fit. Quickly adjust the column width, height and gap between columns for your particular publication, and the scrolling function adjusts automatically.

Column Reader can be placed anywhere on an existing page, or on a page of its own. It is a division made up of three main elements, lined up left to right: the Back Navigation, the Page Frame, and the Ahead Navigation. 

To start, link to columnreader.css in the head of your HTML document:

```html
<head>
	<link rel="stylesheet" href="css/columnreader.css" />
</head>
```
Add two script elements at the bottom of your HTML document, just before the closing body tag. These establish the reading order of chapters split into multiple html files, and call the Column Reader scripts for rendering those files into columnd.

```html
<script type="text/javascript">
	//previous document in book, or comment out if none
	var pr = 'ch01.html'; 
	//next document in book, or comment out if none 
	var nx = 'ch03.html'; 
</script>

<script src="js/columnreader.js" type="text/javascript"></script>
```
Copy and paste the Column Reader where you want it in your HTML document. Replace "PUT YOUR TEXT HERE" with your text. Paragraphs images and other elemnets are all fine.

```html
<div id="columnreader">
	<div id="back" class="nav">
		<span class="step" id="stepback" title="Previous Page">&#8249;</span>
		<span class="jump" id="jumpback" title="Previous Chapter">&#171;</span>
	</div>
	<div id="pageframe">
		<div id="text">PUT YOUR TEXT HERE</div>
	</div>
	<div id="ahead" class="nav">
		<span class="step" id="stepahead" title="Next Page">&#8250;</span>
		<span class="jump" id="jumpahead" title="Next Chapter">&#187;</span>		
	</div>
</div>
```

###Adjusting the columns

By default, columns are set up with a width of 380px, a height of 560px and a gap between columns of 20px, but all these are easy to adjust in the columnreader.js file:

```js
// Change these to adjust your layout

var col = 380;  /* column width */
var ht = 560; /* column height */
var gap = 20;  /* gap between columns */
```

Also in the columnreader.js file, you can also specify a maximum number of columns to display, regardless of the available space. This example allows for up to 15 columns:

```js
// Delete numbers to set a maximum number of columns

var cols = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15];
```

Whereas this example would never display more than 3 columns:

```js
var cols = [1, 2, 3];
```

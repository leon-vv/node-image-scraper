Node Image Scraper
========================
Scrape images from the web easily.
Usage
------------------------
The image-scrape module provides a class which needs to be constructed with a url:
```JavaScript
var Scraper = require("image-scraper");

var scraper = new Scraper("http://www.nodejs.org");
```
The url can be changed easily:
```JavaScript
scraper.address = "http://www.npmjs.org";
```
The scraper object provides the .scrape() method.
The scrape method accepts one optional argument: a callback function.

This callback function can also be set using the .on() method.
```JavaScript
scraper.on("image", function(image){

	// Do something.	
});
```
The callback is called every time an image tag has been found,
the image object which is passed in consist of the following:
```JavaScript
// The attributes found in the image tag, which is parsed by [cheerio](https://npmjs.org/package/cheerio).
image.attributes;
// The basename of the image.
image.name;
// Absolute path to the folder the image will be saved to.
image.saveTo;
// Extension of the image file.
image.extension;
// The absolute URL of the image.
image.address;
// The URL of the page the image is scraped from.
image.fromAddress;
// Save the image.
image.save();
```
The default behaviour is to save the image in the current directory, with the name and extension found in the src attribute.

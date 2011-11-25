# ab.js - A/B Testing JavaScript Framework

![Logo](https://github.com/newzealandpaul/ab.js/raw/markdown-test/web/2.png)

Concept and Design by [Paul William](https://github.com/newzealandpaul)

Developed by [John Winter](http://www.aptonic.com) (john@aptonic.com)

## Usage

Copy ab.js into the js directory inside your web site root. Include in the pages head section with:

	<script type="text/javascript" src="js/ab.js"></script>

Directly after this include you can setup your A/B tests as follows:

	<script type="text/javascript">

	var myAbTest = new ABTest("example test", 1, 
	{
		first_variation : function() {
			document.getElementById("content").innerHTML = "This is a variation";
		},
		another_variation : function() {
			document.getElementById("content").innerHTML = "This is another variation";
		},
		control: function() { /* Empty function. */ }
	});

	</script>
	
You can have as many variation functions as you want.  
The first time the page loads, one of the variation functions will be selected at random and run.

A cookie will then be set so that each time the user loads the page they see the same variation.

There is nothing special about the control function, it is just another variation.   
Normally the control will just be an empty function.

A Google Analytics custom variable will be set called "abjs_{test name}"  
You can compare the performance of each variation in the Demographics -> Custom Variables section of
Google Analytics.

There is an example A/B test setup in example/test.html

## License

This code is released under the MIT License.

## Many Thanks 

* contentloaded() by [Diego Perini](https://github.com/dperini)
* isFunction() from [Underscore.js](http://documentcloud.github.com/underscore/)
* queryString() from [jquip](https://github.com/mythz/jquip)
* QUnit() from [jQuery](http://docs.jquery.com/QUnit)

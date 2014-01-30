---
title: Loading Amber
layout: default
permalink: "loading-amber.html"
parent: Overview
---

In this section we will learn how setup an `index.html` page to load
amber using [requirejs](http://requirejs.org).

#### Amber packages

Amber packages are AMD modules. AMD (Asynchronous Module
Definition) is a JavaScript API for defining modules and
dependencies to be loaded asynchronously.

Amber ships with [requirejs](http://requirejs.org), the most popular
AMD loader implementation.

Create an `index.html` file with the following contents:

{% highlight html %}
<!DOCTYPE html>
<html>
	<head>
	    <script
		  type='text/javascript'
		  src='./bower_components/amber/support/requirejs/require.min.js'>
	    </script>
	    <script
		  type='text/javascript'
		  src='./bower_components/amber/support/amber.js'>
	    </script>
	</head>
	<body>
	</body>
</html> 
{% endhighlight %}

In the next script we define how Amber packages are loaded. Amber
comes with several AMD modules, the default one being `amber/devel`.

```html
<!DOCTYPE html>
<html>
	<head>
	    <script
		  type='text/javascript'
		  src='./bower_components/amber/support/requirejs/require.min.js'>
	    </script>
	    <script
		  type='text/javascript'
		  src='./bower_components/amber/support/amber.js'>
	    </script>
	    <script type='text/javascript'>
		  require(['amber/devel'], function (amber) {
	  		amber.initialize();
		  });
	    </script>
	</head>
	<body>
	</body>
</html> 
```


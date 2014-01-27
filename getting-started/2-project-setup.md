---
title: Setting up the project
layout: default
permalink: "setting-up-project.html"
parent: Getting started
---

Now that the command-line tool `amber` is installed, the project can
be setup using bower.

### Bower

Bower is a package manager for the web. Amber can be install either by
running in the root directory of the new project:

```sh
bower install amber --save
```

or by adding in the root of the project a `bower.json` file like the
 following:

```json
{
    "name": "amber-todolist",
    "dependencies": {
        "amber": "~0.12.3"
    }
}
```

and evaluating
```sh
bower install
```

In both cases, Amber will be installed in a directory named `bower_components`.

### Loading Amber


In this section we will learn how setup an `index.html` page to load
amber using [requirejs](http://requirejs.org).

#### Amber packages

Amber packages are AMD modules. AMD (Asynchronous Module
Definition) is a JavaScript API for defining modules and
dependencies to be loaded asynchronously.

Amber ships with [requirejs](http://requirejs.org), the most popular
AMD loader implementation.

In the `index.html` page, both `requirejs` and `amber.js` are loaded
as any JavaScript file:

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
	</head>
	<body>
	</body>
</html> 
```

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


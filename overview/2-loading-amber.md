---
title: Loading Amber
layout: default
permalink: "loading-amber.html"
parent: Overview
next: "/overview/loading-packages.html"
---

In this section we will learn how setup an `index.html` page to load
amber using [requirejs](http://requirejs.org).

#### Amber packages

Amber packages are AMD modules. AMD (Asynchronous Module
Definition) is a JavaScript API for defining modules and
dependencies to be loaded asynchronously.

Amber ships with [requirejs](http://requirejs.org), the most popular
AMD loader implementation.

Create an `index.html` file with the following contents in the root folder of your project, next to the `bower_components` directory:

{% highlight html %}
<!DOCTYPE html>
<html>
    <head>
        <script
          type='text/javascript'
          src='bower_components/amber/support/requirejs/require.min.js'>
        </script>
        <script
          type='text/javascript'
          src='bower_components/amber/support/amber.js'>
        </script>
    </head>
    <body>
    </body>
</html> 
{% endhighlight %}

We can then modify our `index.html` page to load the `devel` -- short
for `development` -- distribution of Amber.

In the next script we define how Amber packages are loaded. Amber
comes with several AMD modules to load Amber; the default one -- the
one with support for application development and in-browser IDE --
being `amber/devel`.

{% highlight html %}
<!DOCTYPE html>
<html>
    <head>
        <script
          type='text/javascript'
          src='bower_components/amber/support/requirejs/require.min.js'>
        </script>
        <script
          type='text/javascript'
          src='bower_components/amber/support/amber.js'>
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
{% endhighlight %}

The last modification we make to the `index.html` page is to add a line after Amber's initialization to automatically popup Helios, its integrated development environment.

Here is our final version of `index.html`.


{% highlight html %}
<!DOCTYPE html>
<html>
    <head>
        <script
          type='text/javascript'
          src='bower_components/amber/support/requirejs/require.min.js'>
        </script>
        <script
          type='text/javascript'
          src='bower_components/amber/support/amber.js'>
        </script>
        <script type='text/javascript'>
          require(['amber/devel'], function (amber) {
            amber.initialize();

            // Popup Helios
            amber.popupHelios();
          });
        </script>
    </head>
    <body>
    </body>
</html> 
{% endhighlight %}

<p class="warning">
Most web browser will block popups by default. You may need to authorize the Helios popup.
</p>

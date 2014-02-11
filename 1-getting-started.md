---
title: Quick start guide
layout: default
permalink: "getting-started.html"
next: "overview.html"
---

Welcome to Amber! This super quick starting guide will get you up and
running with Amber.

## Installing Amber

<p class="note">
The <a href="overview.html">Overview</a> gives more informations about
the way Amber is shipped, how to install and load it.
</p>

To get Amber running, you will need [Bower](http://bower.io) and
[Node.js](http://nodejs.org). Install the command-line tools with
`npm` and Amber using bower:

{% highlight sh %}
# Install the CLI tools
sudo npm install -g amber

# Create the project structure
mkdir myproject
cd myproject/

# The project files will be stored in src/
mkdir src

# Install Amber as a dependency to our project
bower install --save amber
{% endhighlight %}

Create an `index.html` file loading Amber:

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
      require.config({
        paths: {
          'myproject': 'src', // mapping for our project files
        }
      });

      // Load Amber
      require(['amber/devel'], function (amber) {

        // Initialize Amber
        amber.initialize({
          // Configure the default AMD namespace for new packages
          "transport.defaultAmdNamespace": "myproject"
        });

        // Start the IDE
        amber.popupHelios();
      });
    </script>
  </head>
  <body>
  </body>
</html> 
{% endhighlight %}

Start the standalone webserver:

{% highlight sh %}
amber serve .
{% endhighlight %}

and open your web browser on
[http://localhost:4000](http://localhost:4000). Helios -- Amber's IDE
-- will open as a popup window. From there new packages will be
created with `mypackage` AMD namespace, and saved to the `src/`
folder.

![Helios](/images/helios.png)

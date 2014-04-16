---
title: Quick start guide
layout: default
permalink: "getting-started.html"
next: "overview.html"
---

Welcome to Amber! This super quick starting guide will get you up and
running with Amber.

[Sebastian Sastre](http://blog.flowingconcept.com/) made an
introductory video of Amber which explains how to get a running Amber
system.


<iframe width="640" height="430" src="//www.youtube.com/embed/iPkas6P4GRQ" frameborder="0" allowfullscreen="true"> </iframe>

## Installing Amber

<p class="note">
The <a href="overview.html">Overview</a> gives more informations about
the way Amber is shipped, how to install and load it.
</p>

To get Amber running, you will need
[Node.js](http://nodejs.org). Install the command-line tools with
`npm` and Amber using bower:

{% highlight sh %}
# Install the CLI tools
sudo npm install -g amber-cli

# Create the project structure
mkdir example-project
cd example-project/

# Create and initialixe a new Amber project
amber init
{% endhighlight %}

You will be asked several questions about your new project during the `amber init` phase. Be sure to set a default namespace for your project.

<p class="note">
If you have been using older versions of Amber, you may have <code>amber</code> installed globally instead of <code>amber-cli</code>. You need to remove it first: <code>sudo npm uninstall -g amber</code>.
</p>

Your project directory now includes Amber as a dependency (using [Bower](http://bower.io), but you don't have to care about this for now), along with several other files, including the index file `index.html`.

All you need to start working is to fire up the standalone amber webserver:

{% highlight sh %}
amber serve
{% endhighlight %}

and open your web browser on
[http://localhost:4000](http://localhost:4000). A button on the page will
open Helios -- the new IDE -- as a popup window. From there new packages will be
created with AMD namespace set during the `amber init` phase, and saved to the `src/`
folder.

![Helios](/images/helios.png)

<p class="warning"> Most web browser will block popups by default. You
may need to authorize the Helios popup and reload the page.</p>

---
title: Installing Amber
layout: default
permalink: "installing.html"
parent: Overview
next: "/overview/loading-amber.html"
---

### 1. The npm package

The npm package contains two command-line tools: `amber`, and `amberc`
(the command-line compiler).

The `amber` tool includes a server to run on localhost
and makes it easier to save packages to be committed on disk. It is a
very convenient way to get started.

`npm` is a package manager for [nodejs](http://nodejs.org), a
JavaScript runtime used to run JavaScript code outside of the web
browser.

`nodejs` and `npm` can either be
[downloadeded](http://nodejs.org/download) from the website, or
installed using Operating System specific package managers.

#### Installing nodejs on MacOS X and Windows

The easiest way to install `nodejs` on MacOS X and Windows is to
download the installer from the
[downloaded](http://nodejs.org/download) page.

For MacOS X users, nodejs can also be installed with [homebrew](http://brew.sh/):


{% highlight sh %}
brew install nodejs
{% endhighlight %}

#### Installing nodejs on Ubuntu

Ubuntu provides nodejs as well as npm in its repository.

{% highlight sh %}
sudo apt-get install nodejs npm
{% endhighlight %}

#### Installing the node amber package

Once nodejs and npm are installed, evaluate:

{% highlight sh %}
npm install -g amber
{% endhighlight %}

Ubuntu users will have to evaluate it with `sudo`:

{% highlight sh %}
sudo npm install -g amber
{% endhighlight %}


### 2. The bower component

The npm package doesn't provide the JavaScript files required to load
Amber in a page. This is instead provided by the bower package.

[Bower](http://bower.io) is a package manager for the web. It makes it
easy to manage dependencies in your application including
Amber. Unlike npm, Bower components are meant to be used inside the
web browser.


```sh
bower install amber --save
```

or by adding in the root of the project a `bower.json` file like the
 following:

{% highlight json %}
{
    "name": "amber-todolist",
    "dependencies": {
        "amber": "~0.12.3"
    }
}
{% endhighlight %}

and evaluating
```sh
bower install
```

In both cases, Amber will be installed in a directory named `bower_components`.


We will see in the next section how to setup a project using bower.

---
title: Installing Amber
layout: default
permalink: "installing.html"
parent: Getting started
next: "/getting-started/setting-up-project.html"
---

Amber is shipped both as

- a [npm module](https://npmjs.org/package/amber) for its command-line
  interface tool `amber` with a small server, compiler and REPL;
- a [bower](http://bower.io) component used as dependency for other
  projects.

### The command-line tool

Using the command-line tool `amber` is not required, as any webdav
server can serve amber files and allow packages to be committed, but
it is a very convenient way to get started. Also, the `npm` package
comes with a command-line compiler and a REPL.

`npm` is a package manager for [nodejs](http://nodejs.org), a
JavaScript runtime used to run JavaScript code outside of the web
browser.

`nodejs` and `npm` can either be
[downloaded](http://nodejs.org/download) from the website, or
installed using Operating System specific package managers.

#### Installing nodejs on MacOS X and Windows

The easiest way to install `nodejs` on MacOS X and Windows is to
download the installer from the
[downloaded](http://nodejs.org/download) page.

For MacOS X users, nodejs can also be installed with [homebrew](http://brew.sh/):

```sh
brew install nodejs
```

#### Installing nodejs on Ubuntu

Ubuntu provides nodejs as well as npm in its repository.

```sh
sudo apt-get install nodejs npm
```

#### Installing the node amber package

Once nodejs and npm are installed, evaluate:

```sh
npm install -g amber
```

Ubuntu users will have to evaluate it with `sudo`:

```sh
sudo npm install -g amber
```


### The bower component

The npm package doesn't provide the JavaScript files required to load
Amber in a page. This is instead provided by the bower package.

[Bower](http://bower.io) is a package manager for the web. It makes it
easy to manage dependencies in your application including
Amber. Unlike npm, Bower components are meant to be used inside the
web browser.

We will see in the next section how to setup a project using bower.

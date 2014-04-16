---
title: Overview
layout: default
permalink: "overview.html"
next: "overview/installing.html"
---

This guide will give you an overview of Amber, it's installation
process and setup.

### How to get Amber

Amber is shipped both as

- a [npm module](https://npmjs.org/package/amber-cli) `amber-cli` for its command-line
  interface tools `amber` and `amberc` providing a small server, a compiler and a REPL;
- a [bower](http://bower.io) component used as dependency for projects
  running in the browser.

We will see in the [next section](overview/installing.html) how
to install both components.

### How Amber manages files

Amber compiles to JavaScript. It saves each package file as
a JavaScript [asynchronous module definition](https://github.com/amdjs/amdjs-api/wiki/AMD)
containing the compiled JavaScript code of the package.

For convenience, Amber also saves the Smalltalk source code
of each package in a separate `.st` file.

In the next sections we will learn how to install Amber, load and save
packages from/to disk and fire up the development environment.

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

- a [npm module](https://npmjs.org/package/amber) for its command-line
  interface tool `amber` with a small server, compiler and REPL;
- a [bower](http://bower.io) component used as dependency for other
  projects.

We will see in the [next section](overview/installing.html) how
to install both components.

### How Amber manages files

Amber compiles to JavaScript. It saves each package file as
a [requirejs](http://requirejs.org) JavaScript module containing the
compiled JavaScript code of the package.

Amber also saves -- for convenience -- the Smalltalk source code of
each package in a separate `.st` file.

In the next sections we will learn how to install Amber, load and save
packages disk and fire up the development environment.

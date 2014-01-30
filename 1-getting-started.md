---
title: Getting started
layout: default
permalink: "getting-started.html"
next: "getting-started/installing.html"
---

This guide will take you through the installation and setup of Amber
to be used in a project.

To get started with Amber and its setup and environment, we will
create a simple TODO list application with Amber.

### Some words about Amber's IDE

![Helios, Amber's IDE](/images/helios.png)

Unlike many other web languages/frameworks, Amber provides a fully
integrated development environment that runs directly in the web
browser.

The IDE makes it possible to edit code live and interact with running
objects. When served with a DAV server or the builtin amber server, it
is also possible to commit changes to disk, freeing the developer from
the edit/save/reload development cycle.

### Saved files

Amber saves packages files as [requirejs](http://requirejs.org)
JavaScript modules containing the compiled code of Amber
packages.

Amber also saves for convenience the Smalltalk source code in separate
`.st` files.

In the next sections we will learn how to install Amber, load packages and
fire up the development environment.

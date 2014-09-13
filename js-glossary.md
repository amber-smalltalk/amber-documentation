---
title: JS ecosystem glossary
layout: default
permalink: "js-glossary.html"
parent: Overview
---

### What is `bower`?

Bower is dependency management tool for client-side web packages. Each packages can specifies its production dependencies and its development-only dependencies by name and semver version expression. Package dependencies are specified in `bower.json` file. Bower, when asked to install dependencies, looks for dependencies of the project and for dependencies of dependencies all way down, unifies version constraints and then installs all dependencies from all levels of the hierarchy in flat manner (side-by-side) into directory `bower_components`.

### Where is `bower` used in Amber?

Amber itself is a client-side web package, so Amber itself is a bower package and uses bower to manage its own client-side dependencies (jQuery and others).

Amber web project (a client-side web project that uses Amber) is encouraged to use bower to manage its dependencies as well, listing Amber itself as one of them. Default projects (the ones created by `amber init`) do just that.




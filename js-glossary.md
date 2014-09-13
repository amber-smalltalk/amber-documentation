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

### What is `grunt`?

Grunt is build system for JS ecosystem. In root directory of the project, grunt looks for `Gruntfile.js` which defines tasks to be done and binds them together, similarly as `Makefile` did for `make` build system for UNIX. Grunt is installed via npm and must be installed in three parts: `grunt` - the runtime, installed as development dependency of the project, `grunt-xxx-yyy` - modules with reusable tasks, also as development dependency of the project, and `grunt-cli`, the CLI command that drives the runtime using `Gruntfile.js`, which should be installed globally.

### Where is `grunt` used in Amber?

Amber itself and default Amber projects (the ones created by `amber init`) both contain `Gruntfile.js` and they include `grunt` and accompanying grunt task modules as development dependencies. In Amber project, grunt is used to recompile Smalltalk source to JavaScript files from CLI, as well as running the tests from CLI. In Amber itself, grunt is used for the same, plus a few bookkeeping tasks.



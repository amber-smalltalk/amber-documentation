---
title: JavaScript ecosystem glossary
layout: default
permalink: "javascript-glossary.html"
parent: Overview
---


### What is `bower`?

Bower is a dependency management tool for client-side web packages. Each package can specify its production dependencies and its development-only dependencies by name and semver version expression. Package dependencies are specified in a `bower.json` file. Bower, when asked to install dependencies, looks for dependencies of the project and for dependencies of dependencies all the way down, unifies version constraints and then installs all dependencies from all levels of the hierarchy in flat manner (side-by-side) into directory `bower_components`.


### Where is `bower` used in Amber?

Amber itself is a client-side web package, so Amber itself is a bower package and uses bower to manage its own client-side dependencies (jQuery and others).

An Amber web project (a client-side web project that uses Amber) is encouraged to use bower to manage its dependencies as well, listing Amber itself as one of them. Default projects (the ones created by `amber init`) do just that.


### What is `grunt`?

Grunt is a build system for the JavaScript ecosystem. In the root directory of the project, grunt looks for a file called `Gruntfile.js`. This defines tasks to be done and binds them together, similarly to what a `Makefile` does for the `make` build system in UNIX. Grunt is installed through the npm package manager and must be installed in three parts:
- `grunt` - the runtime, installed as development dependency of the project, 
- `grunt-xxx-yyy` - modules with reusable tasks, also as development dependency of the project, and
- `grunt-cli`, the CLI command that drives the runtime using `Gruntfile.js`, which should be installed globally.


### Where is `grunt` used in Amber?

Amber itself and default Amber projects (the ones created by `amber init`) both contain `Gruntfile.js` and they include `grunt` and accompanying grunt task modules as development dependencies. In an Amber project, grunt is used to recompile Smalltalk source to JavaScript files from the command line (CLI), as well as running the tests from CLI. In Amber itself, grunt is used for the same, plus a few bookkeeping tasks.


### What is `grunt-init`?

Grunt-init is a create-project-from-a-template tool, spawned from `grunt` to be a standalone tool. It defines an API. The templates themselves are created as isolated `npm` packages, which the `grunt-init` CLI command can use. In template modules, you define the skeleton of the project, a set of questions to ask when the project is created and the way they are included in the skeleton. The result is, by running `grunt-init` with a specific template, you answer a few questions, and a project is created for you base on the answers.

### Where is `grunt-init` used in Amber?

It is used internally as first part of `amber init`. It uses the `grunt-init-amber` template.

### What is `node`?

Node.js is a project running JavaScript (using Google's V8 engine) in a server environment.This allows for complex transforms,such as shortening multicharacter variable names or using a shorter syntex   In addition to the V8 engine itself, it includes libraries for writing servers in async-io manner. More and more server parts of the web applications are being written in Node.js as it is straightforward to write performant web server using it, and JavaScript is a higher level language compared to languages used to write server apps before.

### Where is `node` used in Amber?

Nearly everywhere, except the case of Amber itself or an Amber project running in the browser. All the tools mentioned in this page run in `node` - they are server-side / CLI tools written in JavaScript. Amber itself uses some CLI tooling (`amber-cli` package in `npm`) itself - `amber` command as a general tool and `amberc` as cli compiler. Those, too, are JavaScript, so they run in `node` (the former is Amber code compiled to JavaScript; the latter is native JavaScript). Amber also exports helper node libraries as `amber-dev` package in npm. And last but not least, you can compile Amber package(s) and bundle them into CLI executable for `node` - which is now `amber` tool itself is created.

### What is `npm`?

It stands for "node package manager" and is a dependency management tool for server-side / CLI JavaScript packages (that is, those to be run in `node`). Each package can specify its production dependencies and its development-only dependencies by name and semver version expression. Package dependencies are specified in a `package.json` file. When asked to install dependencies, `npm` looks for dependencies of the project and installs them into the directory `node_modules`, while doing the same for the dependencies itself, the result being a deep tree of dependencies - this way the same module could appear several times (even hundreds of times), but always as a local dependency of its parent - this way, version clashes are avoided.

### Where is `npm` used in Amber?

First, `npm` is used to install all the tools mentioned here (except `node` and itself), and it is also used to install Amber CLI tool from the `amber-cli` package. Second, Amber itself and Amber projects contain `package.json` files which list the development dependencies needed for the supporting tooling to work (`grunt`, `amber-dev` and others). Third, `amber` itself is a `npm` package, for server-side projects that want to use it from `node`, not from browser.


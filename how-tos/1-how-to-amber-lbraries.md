---
title: How to create, publish and use Amber libraries
layout: default
parent: How-to's
permalink: "how-to-amber-libaries.html"
next: "how-to-next.html"
---

People can visit [bower](http://bower.io/search/) and find JavaScript libraries to solve the most diverse problems and empower their applications with lots of cool things. 

Amber Smalltalk allows easy integration of these libraries. But besides using third party JavaScript libraries, your Amber application can use your own Amber libraries.

In this guide you'll see how to create, publish and use Amber libraries.

### How to create an Amber library?

1. Run `amber init` in an empty directory; same as to start a new Amber project.
answer the questions to get your project scaffolded (see tips about naming your library below)
2. Run `git init` to make the directory a git repository.
3. Add `config.js` and `the.js` into `.gitignore` because a library has no need to commit them in your git repo.
4. Evaluate `amber serve`.
5. Point your browser to hit Amber's endpoint which would be [http://localhost:4000](http://localhost:4000) unless you had specified a different one.
6. Start developing your library using Amber and the IDE as with any normal Amber code
commit your packages from the IDE.
7. Version your project with: `git commit -am "I've made this Amber library and this version rocks!"`.

### Tips about naming your Amber library

When you create a new Amber project, one of the things you need to answer is the name of the project. In this case you will be deciding about the name of your new library. Also, you define the namespace of the library. This namespace is important because it is used by requirejs to locate and properly load the code in your project. 

After the library is published, the namespace can not be changed anymore since it would break other people's code. Therefore, it is e essential to come up with a good name at library creation time. Keep in mind that the namespace you define has to be the same as the one in the  “paths” section of the `local.amd.json` file in the root of your project. 

### How to publish your Amber library?

1. Once your library is ready for consumption by a wider audience, push your repository to a publicly accessible git repository e.g. GitHub, Bitbucket, GitLab or any other public git repository.
2. Choose the version you will publish. To make it public, bower requires that you use valid Semantic Versioning. For example, version `0.x.y` for pre-production stages and `x.y.z` with `x>=1` when that library is used in production and cares about backwards compatibility. For more about semantic versioning read here: [http://semver.org/](http://semver.org/).
3. Then, either go with next three steps:
- Edit the bower.json file and make sure you are defining the version number you want to publish. e.g.: "version": "0.9.2".
- Commit those changes.
- Tag that commit with the semver version you want to publish. For example, if you want to tag your last master commit as 0.9.2 then you do `git tag 0.9.2` in your master branch.
4. Or, do the aforementioned three steps in one convenient command by using  `bower version 0.9.2 -m “Release 0.9.2”`. See [here](http://bower.io/docs/api/#version) for more details about that.
5. Finally, push the tag to the public repository to make the new version available to the world. Following our example here, if you want to publish that 0.9.2 commit on your local master after tagging it, you just push it with `git push origin 0.9.2`.

And here comes the best part. Because you did all that with your Amber library, anyone can install it quite easily using one single command thanks to the bower.io package management system.

This is the command to register your library in bower:

`bower register [lib-name] [git endpoint]`

e.g.:

`bower register amber-awesome-trick git@github.com/amberguy/amber-awesome-trick.git`

###A couple of tips about publishing in bower

- The registration is a one-time operation. If you registered your library already, you just tag and push the new version.
- Regarding the naming of your Amber libraries: as long as the name is not taken in the bower repository, you can name your Amber library however you want. It is advisable to prefix it with `amber-`. For example, if you write a D3 wrapper you can publish it as `amber-d3`. If you create code to use three.js, your library will be easier to find if it is named `amber-threejs` and so on.
- The `bower.json` file has a section named `keywords`, for Amber libraries, we suggest that you tag it like this `"keywords": [ "Amber","Smalltalk","AnyAdditionalTagYouWant" ]`, when you do that, it gets listed when people search for [http://bower.io/search/?q=amber](http://bower.io/search/?q=amber) or [http://bower.io/search/?q=smalltalk](http://bower.io/search/?q=smalltalk).

### How to use your Amber library in Amber projects?

You have published your library in bower, great! Congratulations! Now, how do you use it in other Amber projects? This is the easy part:

1. You bring the library into the directory tree of the project with bower.
2. Configure `deploy.json` and `devel.json` so your app knows what to load.
3. Use grunt to prepare the code you need for using it.
4. Start using it!

Here are the commands:

1. To install the library in your app you do: `bower install lib-name --save`.
2. Edit `deploy.js` to setup the list of packages from the library that your app needs, for example: `amber-d3/AmberD3-View` and `amber-d3/AmberD3-Core` and any other package that your app might be using from that library.
3. Rebuild the development infrastructure by running: `grunt devel`.
4. Reload your app. All the classes from the packages you listed in point 2 can now load as expected and are present and accessible from your IDE.

### Conclusion

That's how you do Amber libraries, publish them for reuse and load them into other Amber apps. 

The bower repository is extremely popular these days and a source of great libraries for many people building application frontends or html5-based applications.

Additionally, getting your Amber-based software there will make fellow Amber programmers able to do even more powerful things with their software. 

Have you made some Amber libraries?

Please announce the libraries you publish on the Amber mailing list so that people know it was added to our growing catalogue of Amber libraries.

And see what others Amber users have published [here](http://bower.io/search/?q=amber).
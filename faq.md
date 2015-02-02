---
title: FAQ
layout: default
permalink: "faq.html"
parent: Overview
---

#### How do I start a new Amber project?

You can see the steps [described here](/getting-started.html) which are basically:

1. `npm install -g amber-cli`
2. `mkdir newProjectDir`
3. `cd newProjectDir`
4. `amber init`
5. `amber serve`

And visit [http://localhost:4000](http://localhost:4000)

Here is also a terminal screencast doing just that:

<iframe src="http://showterm.io/457dc8b24df38d67e421d#fast" width="640" height="480"></iframe>


#### How do I get back the Helios IDE after I have closed it?

Press this sequence of keys: Shift, Shift, Ctrl, Shift.
A dialog should appear with "Legacy IDE" and "Helios IDE" buttons. 

In case the above did not work, evaluate the following in the JavaScript console:

`require('amber/helpers').popupHelios()`

    
#### What version is the Amber website running?

1.    Open IDE at [http://amber-lang.net/](http://amber-lang.net/).
2.    Go to the Workspace tab.
3.    Print or inspect the expression ``Smalltalk version``.

#### How do I install the latest Amber version?

For the **latest stable**, go for

`npm -g install amber-cli`

If you want the **latest prerelease**, go for

`npm -g install amber-cli@bleedingedge`

Note that bleedingedge will *not* install the stable version even if it is newer.

If you want to be sure which version is latest and which one is bleedingedge use:
`npm info amber-cli` and you will find them in the `dist-tags` section.

#### How do I update Amber?

1. ``npm install -g amber-cli``  will get it fixed for all new projects and 

2.  ``npm update`` in every project dir will fix it for current projects

3. `bower install` in every project dir will fix it for current projects


#### What does the caret ^ do in front of a versionnumber?

``^0.14.1`` is a shortcut for ``>=0.14.1 <0.15.0``. 
Contrary to a common misconception, package.json / bower.json do not show the version that is installed, but instead they describe what interval of versions is required for installation itself.


#### How do I get the text value of an input field?

If you have `<input id="field1" ...`, the way to get its value is `'#field1' asJQuery val`.

#### How can I 'call' JavaScript functions from my Amber code? 

To allow you to use JavaScript from your Amber code, Amber uses a proxy that will route Smalltalk messages as JavaScript calls as transparent as possible. For example, _all_ JavaScript methods in jQuery are available to you this way:

**Without arguments**: 

`'#element-id' asJQuery hide`
`'#element-id' asJQuery show`

**With one argument**: 

`'#element-id' asJQuery attr: 'data' put: 'some-value'`

**With many arguments**:

`aQuery.sampleFunc(a,b,c);` translates to `aQuery sampleFunc: a andThis: b andThat: c.`

In the previous examples, the `put:` and the ``andThis:andThat:`` part of the Smalltalk selector can be named any way you want. For JavaScript functions the names in that part of the keyword are ignored. Amber  needs only the first part of the selector matching the JavaScript function name.

#### Where can I find more questions and answers?

You can try the [wiki](https://github.com/amber-smalltalk/amber/wiki/FAQ) or join the Amber's chat group [here](https://gitter.im/amber-smalltalk/amber).



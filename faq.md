---
title: FAQ
layout: default
permalink: "faq.html"
parent: Overview
---

#### Q: How do I start a new Amber project?

A: You can see the steps [described here](/getting-started.html) which are basically:

1. `npm install -g amber-cli`
2. `mkdir newProjectDir`
3. `cd newProjectDir`
4. `amber init`
5. `amber serve`

And visit [http://localhost:4000](http://localhost:4000)

Here is also a terminal screencast doing just that:

<iframe src="http://showterm.io/457dc8b24df38d67e421d#fast" width="640" height="480"></iframe>


#### Q: How do I get back the Helios IDE after I have closed it?

Press this sequence of keys: Shift, Shift, Ctrl, Shift.
A dialog should appear with "Legacy IDE" and "Helios IDE" buttons. 

In case the above did not work, evaluate the following in the JavaScript console:

`require('amber/helpers').popupHelios()`

    
#### Q: What version is the amber website running?

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

2.  ``npm update amber-dev`` in every project dir will fix it for current projects

3. `bower install` in every project dir will fix it for current projects


#### How do I get the text value of an input field?

If you have a field with an id of #field1, the way to get it's value is `'#field1' asJQuery val`.

Note: _All_ JavaScript methods in jQuery are available to you this way.

Multi parameter functions are then mapped like:

`aQuery.sampleFunc(a,b,c);`

 `aQuery sampleFunc: a andThis: b andThat: c.`

The ``andThis:andThat:`` part can be any selectors. The only thing that matters for JavaScript and Amber is the first part of the keyword selector which has to match the JavaScript function name.


#### Where can I found more questions and answers?

You can try the [wiki](https://github.com/amber-smalltalk/amber/wiki/FAQ) or join the Amber's chat group [here](https://gitter.im/amber-smalltalk/amber).



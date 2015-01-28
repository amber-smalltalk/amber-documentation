---
title: FAQ
layout: default
permalink: "faq.html"
parent: Overview
---

#### Q: How do I start a new Amber project?

A: You can see the steps [described here](/getting-started.html) which are basically:

{% highlight sh %}
npm install -g amber-cli
mkdir newProjectDir
cd newProjectDir
amber init
amber serve
{% endhighlight %}

And visit `http://localhost:4000`

Here is also a terminal screencast doing just that:

<iframe src="http://showterm.io/457dc8b24df38d67e421d#fast" width="640" height="480"></iframe>


#### Q: How do I get back the Helios IDE after I have closed it?

Press this sequence of keys: Shift, Shift, Ctrl, Shift.
A dialog should appear with "Legacy IDE" and "Helios IDE" buttons. 

In case the above did not work, evaluate the following in the JavaScript console:

    require('amber/helpers').popupHelios()

    
### Q: What version is the amber website running?

1.    Open IDE at http://amber-lang.net/.
2.    Go to Workspace tab.
3.    Print-it ``Smalltalk version``.
4.    

### How do I install the latest Amber version?

'Latest' often means the 'latest stable'. If this is the case go for

      npm -g install amber-cli

If you mean really the prereleases, 

      npm -g install amber-cli@bleedingedge 

should install the last prerelease (but not the stable version even if it is newer).

Use `npm info amber-cli` to find out which version is latest and which one is bleedingedge, if you are unsure.


### How do I update Amber?

-  ``npm install -g amber-cli``  will get it fixed for all new projects and 

-  ``npm update amber-dev`` in every project dir will fix it for current projects


### How do I get the text value of an input field?

Assuming I have a field with an id of #field1, how do I get the text value of it?

Answer:

   '#field1' asJQuery val

Note:

All Javascript methods in jQuery are available to you this way.

Multi parameter functions are then mapped like:

    aQuery.sampleFunc (a,b,c);

    aQuery sampleFunc: a and: b and: c.

The ``and:`` can be whatever. The only thing that matters is the first part of the keyword selector which has to match the function name.



### More questions and answers 

On the wiki
https://github.com/amber-smalltalk/amber/wiki/FAQ


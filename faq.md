---
title: FAQ
layout: default
permalink: "faq.html"
parent: Overview
---

### Q: How do I get back the Helios IDE after I have closed it

Press this sequence of keys: Shift, Shift, Ctrl, Shift.
A dialog should appear with "Legacy IDE" and "Helios IDE" buttons. 

In case the above did not work, evaluate the following in the JavaScript console:

    require('amber/helpers').popupHelios()

    
### Q: What version is the amber website running?

1.    Open IDE at http://amber-lang.net/.
2.    Go to Workspace tab.
3.    Print-it ``Smalltalk version``.

As an alternative evaluate

      Smalltalk version
      
in a workspace

### More questions and answers 

On the wiki
https://github.com/amber-smalltalk/amber/wiki/FAQ


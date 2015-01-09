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

A: Evaluate the following in the JavaScript console:

    require('amber/helpers').popupHelios()

---
layout: post
title: What is virtualenv?
date:   2016-04-04
tag: virtualenv
---


While developing apps in django we using a tool called virtualenv , most of us wondering that what is it and what it do . 
So as the name suggest it allows to create some virtual environments. Each can have a different version of Python, and a different sets of libraries.

I am learning this Django framework and virtualenv helps me in various ways in developing apps under django framework.

### Why do we need virtualenv ?

Normally you can create and use Python programs without that, but using virtualenv can help a lot.

Such virtual environment provides many possibilities such as:

1. On production servers it allows to run applications created for different Python versions.

2. On testing servers it allows to perform many tests including:
  
   * Testing the installer script if that really installs all necessary libraries with checking their versions.
  
   * Testing applications using different set of libraries.
  
   * Checking if upgrade of a library won’t cause errors.



### Installation 

 There are a number of ways to install virtualenv on your system. 


 {% highlight ruby %}
$ sudo apt-get install python-virtualenv

$ sudo easy_install virtualenv

$ sudo pip install virtualenv

{% endhighlight %}



###  What did Virtualenv do?

* Packages installed here will not affect the global Python installation. 

* Virtualenv does not create every file needed to get a whole new python environment

* It uses links to global environment files instead in order to save disk space end
speed up your virtualenv. 

* Therefore, there must already have an active python environment installed on your
system.



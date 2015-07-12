Dr. Jekyll and Mr. Pelican
==========================

A comparison of Static site Generators

What even *is* a static site generator?
---------------------------------------

.. .. figure:: static/jekyll.png
    :width: 50pc
    :align: center

.. .. raw:: html

..     <br>
    
.. .. figure:: static/whatevenis.jpeg
    :width: 50pc 
    :align: center


I asked the all-knowing guru Google this very question, and 
found there wasn't an explicit definition of what a static
site generator is. A static site is easy to define -- one that
doesn't run any code, server or client side.  That is to say
that there are only html, CSS, and perhaps some purely-aesthetic
javascript files (for things like expandable menus).  Then
we can say that an Static site *generator* is a tool that takes content and 
generates a static site.

Ok, so what makes a good SSG?
-----------------------------

.. .. figure:: static/rst.png
    :align: right

.. .. figure:: static/class-act.png
    :align: left
    :width: 30pc
    
.. .. figure:: static/theme.jpg
    :align: center
    :width: 30pc


Well, it depends on what you want from your static site generator.
Is your favorite language python?  Pelican might be 
the thing for you.  Does everything you use need to be open 
source?  Free of cost?  Work with Windows?  How are you deploying your site?
There are a lot of factors that go
into choosing the right SSG.  I chose to focus on some of 
the factors I really care about in comparing Pelican to Jekyll:

* How well does it work with Github, and/or how easy is it to publish?
* Does it support restructured text?
* How easy is themeing?  How customizable is it?

I've included some other important points in this slide deck,
but these are some of the things I prioritize in my comparison.

What do other people think?
---------------------------

.. .. figure:: static/high-five.png
    :align: left
    :width: 50pc


.. .. figure:: static/windows-dinosaur.jpg
    :align: right
    :width: 50pc


Who cares?  Obviously I'm the expert here. 

I kid. According to the promising site `slant.co <http://www.slant.co/topics/330/~what-are-the-best-static-site-generators>`_:

* Code highlighting (pygments)
* Working with Windows
* Import existing blogs
* User friendly

Things that Jekyll does well:
-----------------------------

* Plays well with Github
* Excellent for blogs
* User friendly if you don't want to mess with HTML/CSS
* Widely used -- every issue has been solved by someone on Stack Overflow
* Written in Ruby

.. figure:: _static/stack-overflow.jpg
    :align: center

The Cons:
---------

* Doesn't work well with Windows (I guess?)
* Configuring to non-default settings is non-trivial, and can sometimes require plug-ins for basic things (ie. list of posts in a category)


Things that Pelican does well:
------------------------------

* Easy to theme
* Easy to use for a site that isn't a blog
* Excellent documentation, but very little web presence
* Tons of settings, very customizable
* Written in Python

.. figure:: _static/customize_keyboard_key.png
    :align: center

The Cons:
---------
* Non-trivial to use with github (see OSU Security club site)

Things that both do well:
-------------------------

* Work out of the box, relatively easy set up
* Nice default themes
* Open source, on github, and accept pull requests
* Make projects easy to maintain
* Development servers
* Work with Sass and ReStructured text

.. .. figure:: _static/sass-ass.jpg
    :align: center
    :height: 200px


This is obviously a pretty long list -- there are lots of 
things that both SSGs do well.  

Things that neither do well:
----------------------------

* Easy for non-computer people
* No graphical user interface. 
* Need to know (or learn) a markup lang
* Non-trivial to include dynamic content

.. nextslide::

.. figure:: _static/tech_support.png
    :width: 60pc
    :align: center

The Conclusion:
---------------

* Well, what do you know; there are pros and cons to both of them!
* Again, it depends on what your priorities are
* But there are other options...

.. figure:: _static/summary.jpg
    :align: center

Other SSGs:
-----------

Listed according to beauty of website

* `Hugo <http://gohugo.io/>`_ -- Go
* `Vaseman <http://about.asika.tw/vaseman/>`_ -- PHP
* `Hexo <http://hexo.io/>`_ -- Javascript
* `Octopress <http://octopress.org/>`_ -- Ruby
* `Brunch <http://brunch.io/>`_ -- Javascript

And `hundreds more <https://www.staticgen.com/>`_
(`and even more! <https://staticsitegenerators.net/>`_)


Thank you!
==========

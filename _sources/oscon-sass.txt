Sass: What it is, how it's used, and why it's so Syntactically Awesome
======================================================================

What is Sass?
=============

Impudent back talk?
===================

To sauce or be saucy to?
========================

Stewed Fruit?
=============

S.A.S.S
-------

.. figure:: static/sass.jpg
    :align: center
    :scale: 25%

The Language
============

The CSS Preprocessor
====================

The Ruby Gem
============

Is it Turing-Complete?
======================

Why should I use it?
====================

.. Ok, so what's the big deal?
    ---------------------------
    .. rst-class:: build
        * Variables
        * Nesting
        * Mixins
        * Inheritance
        * Operators
        * Conditionals
        * For loops
        * Datatypes
     
Variables
=========

Boo
---

.. code-block:: css

    .error1{
        color: red;
    }
    
    .error2{
        color: red;
    }

    .error3{
        color: red;
    }

Yay
---

.. code-block:: css

    $error-color: red;

    .thing1{
        color: $error-color;
    }

    .thing2{
        color: $error-color;
    }

    .thing3{
        color: $error-color;
    }

Nesting
=======

Raisins
-------

.. code-block:: css

    #thing1 {
        ...
    }

    #thing1 .thing2 {
        ...
    }

    #thing1 .thing2 a {
        ...
    }

Hugs
----

.. code-block:: css

        #thing1 {
            ...
            .thing2 {
                ...
                a {
                    ...
                }
            }
        }

Inheritance
===========


Toad's feet
-----------

.. code-block:: css

    .thing1 {
        width: 100%;
        border: 1px solid #444;
        margin: 20px;
    }

    .thing2 { 
        width: 100%;
        border: 1px solid #444;
        margin: 0px;
    }    
     

Puppies
-------

.. code-block:: css

    %common {
        width: 100%;
        border: 1px solid #444;
    }

    .thing1 {
        @extend %common;
        margin: 20px;
    }

    .thing2 {
        @extend %common;
        margin: 0px;
    }

Mixins
======


IE6
---

.. code-block:: css

    .thing1 {
        -webkit-border-radius: 10px;
        -moz-border-radius: 10px;
        -o-border-radius: 10px;
        border-radius: 10px;
    }

    .thing2 {
        -webkit-border-radius: 12px;
        -moz-border-radius: 12px;
        -o-border-radius: 12px;
        border-radius: 12px;
    }



Firefox
-------

.. code-block:: css

    @mixin border-radius($radius){
        -webkit-border-radius: $radius;
        -moz-border-radius: $radius;
        -o-border-radius: $radius;
        border-radius: $radius;
    }

    .thing1 {
        @include border-radius(10px);
    } 

    .thing2 {
        @include border-radius(12px);
    }

Operators
=========

Pirranhas
---------

.. code-block:: javascript

    var width = '500px';
    $('.thing1').css('width', toString(width/2)+'px');
    
Doctor Who
----------

.. code-block:: css
    
    $width: 500px;

    .thing1{
        width: $width/2;
        }

Conditionals
============

Blink tags
----------

.. code-block:: jquery

    if($('.thing1').parent()){
        $('.thing1').css('color', 'red');
        } else {
        $(a).css('color', 'red');
        }

Beyonce
-------

.. code-block:: css

    @mixin does-parent-exist {
        @if & {
            &:hover {
                color: red;
            }
        } @else {
        a {
            color: red;
        }
      }
    }

Functions
---------

There are functions to: 

* Darken, lighten, or invert colors
* Upper case, lower case, length of strings
* Round, floor, ceiling, abs, generate random numbers
* Traverse lists and maps
* `And more! <http://sass-lang.com/documentation/Sass/Script/Functions.html>`_

Thank you!
==========


page
----

.. figure:: static/any-questions.gif
    :align: center
    :height: 400px

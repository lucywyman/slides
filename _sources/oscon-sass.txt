Sass: What it is, how it's used, and why it's so Syntactically Awesome
======================================================================

What is Sass?
=============

Impudent back talk?
===================

.. rst-class:: build

    `Well, yes, but no. <http://google.com>`_

To sauce or be saucy to?
========================

.. rst-class:: build

    .. note::

        Maybe this will help

    Closer. 

Stewed Fruit?
=============

.. rst-class:: build

    `What? <http://dictionary.reference.com/browse/sass>`_

page
----

.. figure:: _static/sass.jpg
    :align: center
    :scale: 25%

But wait, how does it work?
===========================


Why should I use it?
====================


Is it Turing-Complete?
======================


Ok, so what's the big deal?
---------------------------

.. rst-class:: build

    * Variables

    * Nesting

    * Mixins

    * Inheritance

    * Operators

 
Variables
=========


Boo
---

.. code-block:: css

    .thing1{
        color: #fff;
    }
    
    .thing2{
        color: #fff;
    }

    .thing3{
        color: #fff;
    }

Yay
---

.. code-block:: css

    $white: #fff;

    .thing1{
        color: $white;
    }

    .thing2{
        color: $white;
    }

    .thing3{
        color: $white;
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

.. code-block:: sass

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

.. rst-class:: build

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



.. code-block:: css
        
        $width: 500px;
        $height: 200px;

        div{
            width: ($width/$height);
            }

And more!
=========

* Conditional logic
* Data types
* Lists and maps
* !default
* @debug

The Future
==========


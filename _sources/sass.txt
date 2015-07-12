Sass: What it is, how it's used, and why it's so Syntactically Awesome
======================================================================

What is Sass?
-------------
Sass--or Syntactically Awesome StyleSheets--is "an extension of CSS that adds power and elegance to the basic language" (Sass docs). 

It provides us with several handy features that help keep CSS clean and functional.  

You can think of it as a set of tools which make styling your website easier; kind of like trading a screw-driver for a powerdrill. 

.. figure:: _static/sass.jpg
    :align: center
    :scale: 25%


But wait, how does it work?
---------------------------
(Warning: jargon ahead)
Sass is a scripting language which is interpreted in CSS by a preprocessor. It actually has two syntaxes!  

The first, Sass (.sass file extension), is an indented syntax similar to haml.  This means that blocks are determined by whitespace.  This syntax is older, and has fallen out of style.

The second, Sassy CSS (.scss file extension), is an extension of CSS3 syntax.  Any valid CSS statement is also a valid SCSS statement, which makes it more user-friendly.

:code:`sass-convert` will convert between the two.


Ok, so what's the big deal?
---------------------------
Sass has a couple of really cool features that I will be covering today:

* Variables

* Nesting

* Import

* Mixins

* Inheritance

* Operators

 
Variables
---------
You read right--Sass uses variables!

.. code-block:: sass

        $primary: #B2D5BA;
        $secondary: #3299BB;
        $font: 'Open Sans', sans-serif;

        h1, h2, h3, h4, p, a{
            font-family: $font;
            color: $secondary;
            }

        article{
            background: $primary;
            }



Nesting
-------
Sass supports nesting your statements.

.. code-block:: sass

        #navigation{
            width: 100%;
            background: $secondary;

            li{
                display: inline-block;
                }
            p{
                font-size: 16px;
                }
            }

No more redundant and unorganized code!


Inheritance
-----------
You can inherit from other elements, then modify them to the element you're currently styling

.. code-block:: sass

        .block{
        @extend .other-block;
        color: 


Mixins
------
Basically macros, with a cute name

.. code-block:: sass

        @mixin border-radius($radius){
            -webkit-border-radius: $radius;
            -moz-border-radius: $radius;
            -o-border-radius: $radius;
            border-radius: $radius;
           }

        .box {@include border-radius(10px);} 

Operators
---------
Although the types must match up (no 100%-70px), you can also perform basic arithmetic with your css

.. code-block:: sass
        
        $width: 500px;
        $height: 200px;

        div{
            width: ($width/$height);
            }


Conditional Logic
-----------------
If, for, each, while...

Other cool features:
--------------------
* Data types
* Lists and maps
* !default
* @debug
*

The Future
----------


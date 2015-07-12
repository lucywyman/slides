Your Roots Are Showing
======================

An exploration of polynomial roots and pretty fractals

Polynomials
-----------

Polynomials are a function of the form 
:math:`a_0 + a_1x + a_2x^2 + ... + a_nx^n, a_n \neq 0`

e.g. :math:`x+5 = y`

.. rst-class:: build

    .. figure:: _static/heart.jpg
        :align: center
        :height: 300px


Ok, so what's a root?
---------------------

The root of a polynomial :math:`p` is a value :math:`a`
such that :math:`p(a) = 0`. 

e.g. The root of :math:`x+5 = 0` is -5, because the expression
is only true if we set x equal to -5.

.. rst-class:: build

    .. figure:: _static/carrot.jpg
        :align: center
        :height: 200px

Why are these a big deal?
-------------------------

It's often handy to know for what values a function will evaluate to 0.
As a simple example, the trajectory of a projectile can be modelled
with a quadratic equation, and the roots will tell you where the
projectile will hit the ground.

More useful, factoring equations is at the heart of RSA, a 
widely use cryptographic scheme.

More interesting, it's used to find the eigenvalues of a matrix.

Multiplicities
--------------

The number of times a polynomial has a root at a given point.

e.g. :math:`(x+1)(x+1)(x+1) = x^3 + 3x^2 + 3x + 1` has multiplicity
3 at x = -1.

Bounds on Roots
---------------

The one I understand best: :math:`x < max(a_i)` (Cauchy)

`Wikipedia's answer <http://en.wikipedia.org/wiki/Properties_of_polynomial_roots#Bounds_on_.28complex.29_polynomial_roots>`_

Easy Roots
----------

* Linear: For :math:`a_1x + a_0 = 0` :math:`x = \frac{-a_0}{a_1}`
* Quadratic: :math:`x = \frac{-a_2 \pm \sqrt{a_2 - 4*a_1*a_3}}{2*a_1}`

.. nextslide::

.. figure:: _static/cubic.gif
    :align: center

.. nextslide::

.. figure:: _static/quartic-formula.png
    :align: center

The problem:
------------

In 1824, Niels Henrik Abel (with help from LaGrange and Ruffini) 
proved that it was not possible to 
algebraically find the roots of polynomial of degree greater than 5.

Other Possibilities:
--------------------

* Newton's Method
* Fixed Point Iteration
* Secant Method
* Bisection

Newton's Method
---------------

The basic idea: :math:`x_{n+1} = x_n + \frac{f(x_n)}{f'(x_n)}`

.. rst-class:: build

    .. figure:: _static/NewtonRGB.jpg
        :align: center
        :height: 500px

Fixed Point Iteration
---------------------

:math:`x_{n+1} = g(x_n)` where :math:`g(x_n) = x_n - \frac{f(x_n)}{f'(x_n)}`


.. rst-class:: build

    .. figure:: _static/cobweb.gif
        :align: center

Secant
------

Draw a secant line between :math:`a, b | a< \alpha, b> \alpha`
, and set x-axis intercept as new a.


Bisection
---------

Choose values :math:`a, b | a < \alpha, b> \alpha`, determine whether
root is above or below :math:`\frac{a-b}{2}`, and then set 
:math:`\frac{a-b}{2}` to be the new a or b. 

Root Density Plot
-----------------

.. figure:: _static/deg5.png
    :align: center

Mandelbrot Set
--------------

The set of complex numbers c such that :math:`z_{n+1} = {z_n}^2 + c`
remains bounded (doesn't diverge under iteration)(I think)

.. figure:: _static/mandelbrot.jpg
    :align: center
    :height: 300px

Problem Conditioning
--------------------

Finding polynomial roots is an ill-conditioned problem.  
This means that small errors can dramatically affect results. 

Wilkinson's Polynomial
----------------------

.. figure:: _static/wilkinson.png
    :align: center

.. rst-class:: build 

    In plain english: by creating a polynomial 
    :math:`(x-1)(x-2)(x-3) ... (x-n)`, we know that it has roots
    at the integers up to n. 

    .. figure:: _static/wilkinson-expanded.png
        :align: center
        :height: 300px

Why is this hard?
-----------------

As we've seen, finding roots is really more of an art than a science.

Questions?
==========



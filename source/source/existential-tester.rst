The Existential Tester
======================

How to prioritize tests and assess risk

Roadmap
-------

.. rst-class:: build

- What we talk about when we talk about testing
- Intro to risk-based testing
- Pitfalls of risk-based testing
- How to avoid the pitfalls
- Examples!

`$ whoami`
----------

.. rst-class:: build

    .. figure:: static/koalaty-assurance.jpg
        :align: left
        :height: 250px

    .. figure:: static/hacking.gif
        :align: center
        :height: 250px

Lucy Wyman

Software Developer in Test

The Company Formerly Known As Puppet Labs

What *is* Testing?
------------------

.. rst-class:: build

* "Making sure software works the way we expect it to"
* Not at all ambiguous

What Should I Test?
-------------------

.. rst-class:: build

    .. figure:: static/risk.jpg
        :align: center
        :height: 450px


What *is* Risk?
---------------

.. rst-class:: build

- "Customer loss of value in a given product because of a defect or deficiency in design or implementation of the product."
- Severity
- Probability
- Dependencies
- Unknown qualities
- Developer confidence

Risk-Based Testing
------------------

====================  =============== ==================  ================
'                     Low Probability Medium Probability  High probability
====================  =============== ==================  ================
**Low Severity**      No action       No action           Manual
**Medium Severity**   No action       Manual              Automate
**High severity**     Manual          Automate            Automate
====================  =============== ==================  ================

Pitfalls
--------

.. rst-class:: build

* Accurately assessing severity and probability require deep knowledge of the thing being tested
* More of an art than a science
* Wrong assessments have consequences
* There are always exceptions
* There are other factors
* What happens when several high-priority features come in at once?

Dodging the Balls
-----------------

.. rst-class:: build

* Ask questions to understand methodology at your org
* Give yourself grace
* Err on the side you're most comfortable defending
* Talk through it with your mentor / manager

Example
-------

Resources
---------

Questions?
==========

Thank you!
==========

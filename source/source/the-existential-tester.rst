The Existential Tester
======================

How to Assess Risk and Prioritize Tests

Roadmap
-------

.. rst-class:: build

- What we talk about when we talk about testing
- Intro to risk-based testing
- Pitfalls of risk-based testing
- How to avoid the pitfalls
- An example!

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

    "Making sure software works the way we expect it to. When the user does X, Y happens."

    .. figure:: static/testing.gif
        :align: center
        :height: 300px

How Do I Prioritize?
--------------------

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

* Err on the side you're most comfortable defending
* Ask questions to understand methodology at your org
* Give yourself grace
* Talk through it with your mentor / manager

Example
-------

**Scenario**: Writing Hello World in Python
**Expectation**: When I run the program, it will print 'Hello World' to stdout

Risks
-----

.. rst-class:: build

- **Note**: In the course of doing this, there will be assessments you probably disagree with! That's the point ;)
- It doesn't print anything
  - High severity
  - High probability
- It doesn't print 'Hello World'
  - Medium severity
  - Medium probability
- It prints to stderr instead of stdout
  - Medium severity
  - Low probability
- It prints 'Hello World\n'
  - Low severity
  - Low probability
- **Note**: This focuses on *results* of errors, not *causes* of errors

Resources
---------

Questions?
==========

Thank you!
==========

QAELK
=====

Are Our Tests Any Good?

http://slides.lucywyman.me/qaelk.html

Roadmap
-------

* Problems with testing at Puppet
* Why we built QAELK
* What QAELK is
* How we're using QAELK
* QAELK V1 and V2
* Demo
* Goals | dreams | next year's disappointments

$ whoami
--------

.. rst-class:: build

    .. figure:: static/testing.gif
        :align: center
        :height: 300px

Lucy Wyman & Zach Reichert

Software Developers in Test

Puppet

Thesis
------

You can use data to make your test suites more efficient + cheaper using ~science~

.. figure:: static/the-more-you-know.gif
    :align: center

Testing At Puppet
-----------------

.. rst-class:: build

    Too many...

    * Pipelines
    * Supported platforms
    * Configurations
    * Jenkins restarts
    * Difficult to keep track of what tests ran, when, and why

    .. figure:: static/limes.jpg
        :align: center
        :height: 250px

Why We Made QAELK
-----------------

We had a lot of questions...

.. rst-class:: build

* **Are our tests providing value?**
* What makes a test valuable?
* Which tests tell us our code is broken?
* Can a test that never fails provide value?
* **Are our tests worth the cost of running them?**
* Why is grafana so terrible?

What is QAELK?
--------------

"Quality Assurance ElasticSearch Logstash Kibana(Grafana)"

.. rst-class:: build

* **A dashboard for aggregating and visualizing data about our acceptance testing**
* Helps us make data-informed decisions based on:
    * Test duration 
    * Test flakiness 
    * Test failure rate
    * And more!

How We Use QAELK
----------------

.. rst-class:: build

* Identify most expensive tests
* Identify flaky tests
* See failure history of tests
* Improve developer feedback time

QAELK phase 1
-------------

First attempt at testing metrics in CI based on ELK

.. rst-class:: build

* Aggregated acceptance testing results
* Learning things about how our tests run in CI
* Keep acceptance testing valuable

QAELK phase 2
-------------

Replace the stack

.. rst-class:: build

* `Google BigQuery`_ (replaces ElasticSearch)
* Custom Application `Dr. Teeth`_ (replaces Logstash)
* `Looker`_ (replaces Kibana/Grafana)
* Maybe we should call it "QABqDrThL" ¯\\_(ツ)_/¯

.. _Google BigQuery: https://cloud.google.com/bigquery/
.. _Dr. Teeth: http://muppet.wikia.com/wiki/Dr._Teeth
.. _Looker: https://looker.com

.. nextslide::

Decoupling ourselves from specific testing tools
------------------------------------------------

.. rst-class:: build

* Tracking test results from all the tools
* Only dependency is that your tool produces JUNIT.xml
* Concepts that are not part of the JUNIT.xml are communicated via query params

.. nextslide::

Benefits of the new stack
-------------------------

.. rst-class:: build

* Custom dashboards built in Looker
* Specific 'Looks' shipped to confluence
* Specific 'Looks' shipped to teams via email
* Querying with SQL is a fallback for those on the bleeding edge

Demo
====

What's Next?
------------

Go beyond our proof of concept

.. rst-class:: build

* Polish what we have
* Find the edges of what is possible with our current stack
* Integrate with existing tools at Puppet that identify transient errors
* Dynamically tier tests

.. _Looker: https://looker.com
.. _Google BigQuery: https://cloud.google.com/bigquery/

Questions?
==========

Thank you!
==========

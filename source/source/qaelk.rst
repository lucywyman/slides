QAELK
=====

Are Our Tests Any Good?

Roadmap
-------

* Problems with testing at Puppet
* Why we built QAELK
* What QAELK is
* How we're using QAELK
* Demo
* Goals | dreams | next year's disappointments

$whoami
-------

.. rst-class:: build

    .. figure:: static/koalaty-assurance.jpg
        :align: left
        :height: 250px

    .. figure:: static/hacking.gif
        :align: center
        :height: 250px

Lucy Wyman | Zach Reichert

Software Developers in Test

Puppet

Thesis
------

You can use data about your tests to improve your test suites. 

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

QAELK phase 1
-------------

First attempt at testing metrics in CI based on ELK

.. rst-class:: build

* Aggregated acceptance testing results
* Learning things about how our tests run in CI
* Keep acceptance testing valuable

.. note::

    1. We chose ELK bc oss, others where using in house
    2. Elastic Search: No SQL database
    3. Logstash: server-side data processing pipeline
    4. Kibana/Grafana: Visualization tool often used for Analytics and Monitoring
    5. In the end ELK/G was the wrong tool for the job
        a. Logstash is optimized for performance not accuracy
        b. The questions we are trying to answer are not Analytics or Monitoring

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

.. note::

    Better BC:
    BQ: provides a SQL interface which I find more appealing to work with
    DrTH: Our custom application is built to be more testable
    Looker: Used by other organizations at Puppet

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

How We Use QAELK
----------------

.. rst-class:: build

* Identify most expensive tests
* Identify flaky tests
* See failure history of tests

Demo
====

What's Next?
------------

Go beyond our proof of concept

.. rst-class:: build

* Polish what we have
* Find the edges of what is possible with our current stack
* Make our data more accurate
* Integrate with existing tools at puppet that identify transient errors

.. _Looker: https://looker.com
.. _Google BigQuery: https://cloud.google.com/bigquery/

Questions?
==========

Thank you!
==========

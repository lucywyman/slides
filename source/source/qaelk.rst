QAELK
=====

Are Our Tests Any Good?

Note: Press 'c' to see presenter notes

This kind of doesn't work for me, but I'll see if I can troubleshoot why later today. Let me know if it does work for you

Roadmap
-------

* Problems with testing at Puppet
* Why we built QAELK
* What QAELK is
* How we're using QAELK
* Demo
* Goals | dreams | next year's disappointments

Who Are We?
-----------

.. rst-class:: build

    .. figure:: static/koalaty-assurance.jpg
        :align: left
        :height: 250px

    .. figure:: static/hacking.gif
        :align: center
        :height: 250px

.. note::
    
    The empty lines are so that these are rendered onto their own lines :P

Lucy Wyman | Zach Reichert

Software Developers in Test

Puppet (Labs)

Testing At Puppet
-----------------

.. rst-class:: build

    Too many...

    * Pipelines
    * Supported platforms
    * Transients
    * Jenkins restarts
    * Difficult to keep track of what tests ran, when, and why

Why We Made QAELK
-----------------

We had a lot of questions...

.. rst-class:: build

* **Are our tests providing value?**
* What makes a test valuable?
* Which tests tell us our code is broken? How much do those tests cost?
* Can a test that never fails provide value?
* Why is grafana so terrible?

What is QAELK?
--------------

"QA ElasticSearch Logstash Kibana/Grafana"

.. rst-class:: build

* "A window into the testing layer of CI"
* **A dashboard for aggregating and visualizing data about our acceptance testing**
* Helps us make informed decisions based on:
    * Test duration 
    * Test flakiness
    * Test failure rate
    * And more!

QAELK phase 1
-------------

.. rst-class:: build

* A metrics project
* Aggregated acceptance testing results
* Learning things about how our tests run in CI
* Keep acceptance testing valuable

.. note::

    1. We chose ELK bc oss, others where using in house
    2. Elastic Search: No SQL database
    3. Logstash: server-side data processing pipeline
    4. Kibana/Grafana: Visualization tool often used for Analytics and Monitoring
    3. In the end ELK/G was the wrong tool for the job
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

.. rst-class:: build

* Tracking test results from all the tools
* Only dependency is that your tool produces JUNIT.xml
* Concepts that are not part of the JUNIT.xml are communicated via query params

.. nextslide::

Benefits of the new stack

.. rst-class:: build

* Custom dashboards built in Looker
* Specific 'Looks' shipped to confluence
* Specific 'Looks' shipped to teams via email
* Querying with SQL is a fallback for those on the bleeding edge

How We Use QAELK
----------------

.. note::

    2-3 examples of "We made this decision based on data from qaelk"

Demo
====

What's Next?
------------
Go Beyond our POC

.. rst-class:: build

* Polish what we have
* Find the edges of what is possible with our current stack
* Make our data more accurate
* integrate with existing tools at puppet that identify transient errors

Resources
---------

* `The ELK Stack`_ - The everything you need to know guide

.. _The ELK Stack: https://logz.io/learn/complete-guide-elk-stack/

Questions?
==========

Thank you!
==========

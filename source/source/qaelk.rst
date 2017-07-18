QAELK
=====

Are Our Tests Any Good?

Roadmap
-------

* Problems with testing at Puppet
* Why we built QAELK
* What QAELK is
* How we're using it
* Demo
* Goals | dreams | next year's disappointments

Who Are We?
-----------

.. table::
   :class: no-border

Testing At Puppet
-----------------

* Waaaaayyyy too many pipelines
* Testing on many supported platforms
* Lots of transients
* Difficult to keep track of what failed, when, and why

We had a lot of questions
-------------------------

.. rst-class:: build

* **How do we know if our tests are providing value?**
* What makes a test valuable?
* Which tests tell us our code is broken? How much do those tests cost?
* How do we know if a failure is a broken test, or broken code?
* Can a test that never fails provide value?
* How can we know the answers to any of these?
* Why is grafana so terrible?

.. figure:: static/whyyy.gif
    :align: center
    :height: 200px

What is QAELK?
--------------

"A window into the testing layer of CI"

A dashboard for aggregating and visualizing data about our Jenkins pipelines

.. rst-class:: build

* Test duration (which tests are taking the longest?)
* Test flakiness
* Test failure rate
* And more!

QAELK phase 1
-------------

"QA ElasticSearch Logstash Kibana/Grafana"

.. rst-class:: build

* A metrics project
* Aggregated acceptance testing results
* Learning things about how our tests run in CI
* Keep acceptance testing valuable
# why was it the right tool at the time
# shortcomings of ELK/G
# elastic cloud is
#everybodyelse is doing it

QAELK phase 2
-------------

Replace the stack

.. rst-class:: build

* Google BigQuery (replaces ElasticSearch)
* Custom Application Dr. Teeth (replaces Logstash)
* Looker (replaces Kibana/Grafana)
* Maybe we should call it "QABqDrThL" ¯\_(ツ)_/¯

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

Demo
====

TODO this should include talking about how we use QAELK data. Maybe 2-3 examples? "Our SRE team uses this feature to do XYZ"
# Base this on the demo given in the MPR

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

Questions?
==========

Thank you!
==========

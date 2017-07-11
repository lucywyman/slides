QAELK
=====

Are Our Tests Any Good?

Roadmap
-------

- What QAELK is
- Why we built it
- How we're using it
- Demo
- Goals | dreams | next year's disappointments

Who Are We?
-----------

What is QAELK?
--------------

A dashboard for aggregating and visualizing data about our Jenkins pipelines

.. rst-class:: build

* Test duration (which tests are taking the longest?)
* Test flakiness
* Test failure rate
* And more!

Down the Rabbit Hole
--------------------

.. rst-class:: build

* **How do we know if our tests are providing value?**
* What makes a test valuable?
* Which tests tell us our code is broken? How much do those tests cost?
* How do we know if a failure is a broken test, or broken code?
* Can a test that never fails provide value?
* How can we know the answers to any of these?
* Why is grafana so terrible?

So...We had a lot of questions
------------------------------

And we decided to make a tool that could answer them

TODO talk about project requirements / goals here?

QAELK phase 1
-------------

"QA ElasticSearch Logstash Kibana/Grafana"

* A metrics project
* Aggregated acceptance testing results
* Learning things about how our tests run in CI
* Keep acceptance testing valuable

QAELK phase 2
-------------
"QAELK2"

Replace the stack
* Google BigQuery (replaces ElasticSearch)
* Custom Application Dr. Teeth (replaces Logstash)
* Looker (replaces Kibana/Grafana)
* Maybe we should call it "QABqDrThL" ¯\_(ツ)_/¯

Decoupling ourselves from specific testing tools
* Only dependency is tool produces JUNIT.xml
* Other data relevant to test runs accepted by Dr. Teeth REST endpoint

Benefits of the new stack
* Custom dashboards built in Looker
* Specific 'Looks' shipped to confluence
* Specific 'Looks' shipped to teams via email
* Querying with SQL is a fallback for those on the bleeding edge
Demo
====

TODO this should include talking about how we use QAELK data. Maybe 2-3 examples? "Our SRE team uses this feature to do XYZ"

What's Next?
------------

Resources
---------

Questions?
==========

Thank you!
==========


Notes: 
- 30 minute talk

Outline:
- Roadmap
- What is QAELK?
- Why did we build it?
  - What questions does it answer?
  - What makes a test "valuable"?
    - Which tests tell us our code is broken?
    - Perception vs reality -- tests are perceived as more or less valuable than they are
    - Cost of tests -- which tests take longer to run than they are "worth"?
    - Cost of maintenance / running time / resources
    - flaky?
    - Transients?
    - never failing?
    - Is it a problem with tests or code?
    - How do you identify a "bad test"?
    - Did we learn anything from this test? Video game scoring
    - Future ideas: 
      - sub systems integrated together
      - qaelk = repo of test run data <--> jira integration (bordain?)(what bugs were found by tests?)  --> report back to jira if an issue was fixed or not
      - testrail (cry)
    - More subtopics here (What is a flaky test? Does a test that never fails provide value? etc.)
- What decisions / actions have we made based on data from QAELK
  - What will you do when you find out XYZ about ABC metrics?
  - Refactor, throw away, or do nothing, put into different testing tier
- Possibly a demo
- Future plans / hopes / dreams
- Resources
- Questions

PE Bolt Server
==============

http://slides.lucywyman.me/pe-bolt-server.html

What?
-----

.. rst-class:: build

  .. figure:: _images/bolt-cutters.gif
      :align: center
      :height: 350px

  * An API to expose bolt's SSH and WinRM transports
  * A thin ruby webserver (`Puma`_) wrapper around the `bolt executor`_
  * A PE service

.. _Puma: https://github.com/puma/puma
.. _bolt executor: https://github.com/puppetlabs/bolt/blob/master/lib/bolt/executor.rb

Decisions
---------

.. rst-class:: build

  .. figure:: _images/small-wrench.gif
      :align: center
      :height: 250px

  "Why isn't bolt-server a clojure service managed by Orchestrator?"
  * We wanted to be able to use Bolt classes directly
  * We didn't want to rewrite any parts of Bolt

  "Why a webserver instead of sockets?"
  * Poor library support in ruby for sockets
  * Difficult for other teams to adopt

Why?
----

.. rst-class:: build

  .. figure:: _images/bolt-why.gif
      :align: center
      :height: 350px

  * Enable the PE Console to run agentless tasks - part of the Road to Automation story
  * Generalize for other tools to use

Other Resources
---------------

* Install from http://builds.puppetlabs.lan/pe-bolt-server/
* Docs at :code:`bolt/developer-docs`
* Available in Johnson builds

Demo
----

.. figure:: _images/usain-bolt-yeah.gif
    :align: center
    :height: 500px

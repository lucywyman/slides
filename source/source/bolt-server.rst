PE Bolt Server
==============


What?
-----

.. rst-class:: build

* An API to expose bolt transports (namely SSH and WinRM)
  
  * For now just run task

* A thin ruby webserver wrapper around the `bolt executor`_

.. _bolt executor: https://github.com/puppetlabs/bolt/blob/master/lib/bolt/executor.rb

Decisions
---------

.. rst-class:: build

"Why isn't bolt-server a clojure service managed by Orchestrator?"

* We wanted to be able to use Bolt classes directly
* We didn't want to rewrite any parts of Bolt

"Why a webserver instead of sockets?"

* Poor library support in ruby for sockets
* Difficult for other teams to adopt

Why?
----

.. rst-class:: build

* Enable the PE Console to run agentless tasks

  * Part of the `Road to Automation`_ story
 
* Generalize for other tools to use

  * Possibly discovery

.. _Road to Automation: 

Demo
----

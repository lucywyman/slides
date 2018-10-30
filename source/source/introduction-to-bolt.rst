Introduction to Bolt
====================

Imperative and Declarative, Together at Last

https://slides.lucywyman.me/intro-to-bolt.html

Agenda
------

* A brief overview of Bolt basics
* What’s new this year in Bolt
* A demo of Bolt in action 

https://pup.pt/installbolt
==========================

Bolt Basics
===========

What Is Bolt?
-------------

:code:`bolt --help`

* Bolt is a Ruby command-line tool for executing commands, scripts, and
  tasks on remote systems
* Distributes and execute scripts, such as Bash, PowerShell, Python
* Supports industry standard protocols (SSH/SCP, WinRM/PSRP) and
  authentication methods (password, publickey)

Tasks
-----

:code:`bolt task run module::mytask`

* Tasks are scripts which are kept in modules and can have metadata
* JSON metadata is stored next to the task
* Any language your target can run
* Can have parameters
* Live in the :code:`tasks/` directory of module

Plans
-----

:code:`bolt plan run module::myplan`

* Plans compose tasks together in meaningful ways
* Plans can have multiple tasks, compute task input, and process output
* Plans are written in puppet plan language, with .pp extension
* Include plan functions, such as run_task() and puppetdb_query()
* Can have parameters
* Live in the plans/ directory of module

Other Commands
--------------

:code:`bolt help`

* bolt task show
* bolt plan show
* bolt command run
* bolt file upload
* bolt script run
* bolt puppetfile install

Configuration
-------------

:code:`~/.puppetlabs/bolt.yaml`

* Global configuration at ~/.puppetlabs/bolt/bolt.yaml
* Local configuration at <project>/Boltdir/bolt.yaml
* Allow global and transport-specific configuration
* Connect to PuppetDB or Orchestrator

Inventory
---------

:code:`~/.puppetlabs/bolt/inventory.yaml`

* Store information about your nodes
* Set transport configuration for specific nodes or node groups
* Override configurations for specific nodes (ie. user)
* Set facts, vars, and features for nodes

Installing Tasks
----------------

:code:`bolt puppetfile install`

Create a Puppetfile in ./Boltdir or ~/.puppetlabs/bolt

Advanced Features
=================

Bolt Apply
----------

:code:`bolt apply`

* Apply blocks of manifest code to a node
* Compiles and applies a standalone Puppet manifest
* Manifest blocks can use existing content from the Forge
* Central code loading
* Most features of the Puppet language are available in a manifest block
  * Classes
  * Custom resource types
  * Functions

Cross-platform Tasks
--------------------

* A task can support multiple platforms by having implementations
* Metadata describes when to use each implementation, using ‘requirements’
* Requirements are features of the target, ie. “Powershell”
* Specify additional features with set_feature or add features in the inventory
* The task runner will choose the first implementation whose requirements are satisfied.

Resources
---------

* **Bolt Project**: https://github.com/puppetlabs/bolt
* **Bolt Documentation**: https://puppet.com/docs/bolt/latest/bolt.html
* **Tasks Hands-on Lab**: https://github.com/puppetlabs/tasks-hands-on-lab#puppet-tasks-hands-on-lab
* **Learning VM**: https://learn.puppet.com/course/puppet-orchestration-bolt-and-tasks
* **Bolt Slack Channel**: #puppet-tasks on https://puppetcommunity.slack.com

Questions?
==========

Thank You
=========

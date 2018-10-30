Get Started Writing Robust Tasks
================================

Lucy Wyman, Software Engineer - Bolt
https://slides.lucywyman.me/writing-tasks.html

https://pup.pt/installbolt
==========================

Agenda
------

* Reading parameter input and producing output in your tasks
* Best practices for writing task metadata
* How to test your tasks and plans

Input
-----

.. rst-class:: build

  * Tasks can receive input as either environment variables, a JSON hash
    on standard input, or as PowerShell arguments

  .. figure:: static/input.gif
      :align: center
      :height: 300px

.. nextslide::

.. code-block:: bash

    # bash.sh
    echo "Hello my name is $PT_name"

.. code-block:: ruby

    # ruby.rb
    params = JSON.parse(STDIN.read)
    puts "Hello my name is #{params['name']}"

.. code-block:: powershell

    # powershell.ps1
    param(
    [Parameter(Mandatory = $true)]
    [String]
    $Name
    )
    Write-Host @"Hello my name is $Name"

Output
------

.. rst-class:: build

  * Fail with a non-zero exit code, and print a specific error message
    to stderr
  * Tasks can provide more details about the failure by including their
    own error object in the :code:`result[:_error]`
  * Return structured data (i.e. JSON to be consumed) by printing a
    single JSON object to stdout

  .. figure:: static/print.gif
      :align: center
      :height: 300px

.. nextslide::

.. code-block:: ruby

  begin
    params = JSON.parse(STDIN.read)
    result = {}
    result['result'] = params['dividend'] / params['divisor']

  rescue ZeroDivisionError
    result[:_error] = { msg: "Cannot divide by zero",
                        kind: "puppetlabs-example_modules/dividebyzero",
                        details: { divisor: divisor },
                        }

Security
--------

* In Powershell

  * Do not call :code:`Invoke-Expression` or :code:`Add-Type` with user input.
  * Use :code:`Resolve-Path` to verify that the path doesn't go outside the locations you expect the task to access

* In Bash

  * Put quotations marks around arguments to prevent the vulnerable shells from evaluating them

* https://puppet.com/docs/bolt/latest/writing_tasks.html#concept-8077 And more!

Task Metadata
-------------

.. rst-class:: build

  * Give it a :code:`description` (duh)
  * Specify an :code:`input_method`
  * Give your parameters descriptions

    * And types! More specific is more better. `Types Documentation <https://puppet.com/docs/bolt/1.x/writing_tasks.html#reference-3806>`_

  * Specify :code:`private` or :code:`supports_noop` if applicable

  .. figure:: static/metadata.gif
      :align: center
      :height: 250px

Implementations
---------------

.. rst-class:: build

* Tasks can have multiple implementations, i.e. a Bash version and
  Powershell version
* Determined based on 'features' - either default or custom

.. nextslide::

.. code-block:: json

  {
    "description": "Install the Puppet 5 agent package",
    "parameters": {
      "version": {
        "description": "The version of puppet-agent to install",
        "type": "Optional[String]"
      }   
    },  
    "implementations": [
      {"name": "install_shell.sh", "requirements": ["shell"]},
      {"name": "install_powershell.ps1", "requirements": ["powershell"]}
    ]
  }


Sharing Code
------------

* Specify other files the task relies on, from module endpoints of any
  module in the modulepath
* Path consists of 

    * the module name
    * one of :code:`lib`, :code:`files`, or :code:`tasks` for the directory within the module
    * the remaining path to a file or directory; directories must include a trailing slash /

.. nextslide::

.. code-block:: json

    {
      "implementations": [
        {"name": "sql_linux.sh", "requirements": ["shell"],
            "files": ["mymodule/files/lib.sh"]},
        {"name": "sql_windows.ps1", "requirements": ["powershell"],
            "files": ["mymodule/files/lib.ps1"]}
      ],
      "files": ["othermodule/files/emojis/"]
    }

Testing Tasks
-------------

* :code:`BoltSpec` ruby library to run bolt tasks, commands, and
  scripts

  * :code:`run_task`, :code:`run_plan`, :code:`run_command`, :code:`run_script`

* Plans to add rspec :code:`Result` and :code:`ResultSet` matchers

.. code-block:: ruby

  include Bolt::Run
  describe 'run_task' do
    it 'should run a task on a node' do
      result = run_task('sample::echo', 'ssh', config: config_data,
                        inventory: inventory_data)
      expect(result[0]['status']).to eq('success')
    end
  end

Shameless Self-Promotion
------------------------

* `Python Task Helper <https://github.com/puppetlabs/puppetlabs-python_task_helper>`_
* `Ruby Task Helper <https://github.com/puppetlabs/puppetlabs-ruby_task_helper>`_

.. nextslide::

.. code-block:: json

  {
    "files": ["ruby_task_helper/lib/task_helper.rb"],
    "input_method": "stdin"
  }

.. code-block:: ruby

  #!/usr/bin/env ruby

  require_relative '../../ruby_task_helper/lib/task_helper.rb'

  class MyTask < TaskHelper
    def task(name: nil, **kwargs)
      { greeting: "Hi, my name is #{name}" }
    end
  end

  MyTask.run if __FILE__ == $0

Resources
---------

* Bolt Project: https://github.com/puppetlabs/bolt
* Bolt Documentation: https://puppet.com/docs/bolt/latest/bolt.html
* Tasks Hands-on Lab:
* https://github.com/puppetlabs/tasks-hands-on-lab#puppet-tasks-hands-on-lab
* Learning VM:
* https://learn.puppet.com/course/puppet-orchestration-bolt-and-tasks
* Bolt Slack Channel: #puppet-tasks on https://puppetcommunity.slack.com

Questions?
==========

Who Orchestrates the Orchestrators?
===================================

Managing Container Linux and Kubernetes with Puppet

https://slides.lucywyman.me/puppet-on-coreos.html

Where We're Going
-----------------

* The Stack
* Why?
* How to manage CoreOS with Puppet
* Deploy K8s to CoreOS with Puppet
* Demo 

Caveats
-------

* I don't do this in production
  * More of a 'proof of concept'
* Literally spawned from "I wonder if I can manage CoreOS with Puppet..."
* No cloud providers, just local VMs

.. figure:: static/no-idea.jpg
    :align: center
    :height: 300px

`Source <http://knowyourmeme.com/memes/i-have-no-idea-what-im-doing>`_

:code:`$ whoami`
----------------

.. rst-class:: build

    .. figure:: static/programmer-valentine.gif
        :align: center
        :height: 300px

Lucy Wyman

Software Engineer - `Bolt`_

`Puppet`_

`Source <https://www.reddit.com/r/gifs/comments/5tyymj/programmer_valentain_day/>`_

.. _Bolt: https://github.com/puppetlabs/bolt

The Stack
---------

.. rst-class:: build

  .. figure:: static/pancakes.jpg
      :align: center
      :height: 250px

  * `Puppet`_
  * `Container Linux`_
  * `Kubernetes`_

`Source <https://www.justataste.com/fluffy-greek-yogurt-pancakes-recipe/>`_

.. _Kubernetes: https://kubernetes.io/
.. _Puppet: https://puppet.com
.. _Container Linux: https://coreos.com/

Why This Doesn't Make Sense
---------------------------

.. note::
    - Once my thing is working it should always work
    - Reproducible
    - Dev --> production is reliable
    - Poor man's version control
    - Everything is in config files, similar to Puppet
    - No package manager on container linux
    - Puppet is used to get your machine to a state, but with immutable infra and config files that is already happening

.. rst-class:: build

* Containers are "immutable"
* CoreOS is "immutable"

  * Configured using `ignition`_ | `cloud-config`_

* Configuration files are your "configuration management"
* Puppet is used to make changes to systems, and manage their lifecycle

.. _cloud-config: https://coreos.com/os/docs/latest/cloud-config.html
.. _ignition: https://coreos.com/ignition/docs/latest/

Why (or when) This Makes Sense
------------------------------

.. note::

    - Don't always want things to be immutable
      - Don't have to worry much about upgrading
      - But, if you have 20 node cluster, want to add ssh key, need to rebuild the whole thing
      - Lose a lot of state caches
      - Brings a lot of risk (latest tag)
      - Can be expensive and slow
    - Testing and debuggability is critical
    - Dependencies need to be versioned
    - Cluster PKI management is not easy
      - No key rotation
    - Terraform abstracts a lot of this away
    - Having bash scripts to manage things is --, not flexible
    - Difference between desired state + actual state
    - End up having state -- databases, caches, etc.
      - Big risk of downtime

.. rst-class:: build

* Manage your entire infra in one place
* When immutable infra doesn't work 

  * Changes can be expensive
  * Lose cache
  * Can be risky

* Handle configuration drift
* Add or modify services without restarting

* `Puppetconf talk`_

.. _Puppetconf talk: https://youtu.be/ThbcHUj70EA?list=PLV86BgbREluVYuJaYGQ0-ep45NCAFe3OQ&t=550

This Is Where The Magic Happens
-------------------------------

.. rst-class:: build

  * `Puppet agent container`_ running on the CoreOS system it's managing
  * Mount directories we care about
  * Make changes to the CoreOS system from within the container
  * Have a networking expert on hand

  .. figure:: static/magic.gif
      :align: center
      :height: 200px

.. _Puppet agent container: https://hub.docker.com/r/puppet/puppet-agent/

Demo
----

https://github.com/lucywyman/puppet-on-coreos-demo

.. figure:: static/stadium-bus-demo.gif
    :height: 400px
    :align: center

Create Kubernetes Cluster
-------------------------

.. rst-class:: build

* Use the `Puppet Kubernetes module`_
* Some manual setup required

Demo Time
---------

https://github.com/lucywyman/puppet-on-coreos-demo

.. figure:: static/demo-day.gif
    :align: center
    :height: 300px

Resources
---------

* `Puppet on CoreOS`_
* `Using Puppet with CoreOS Tools`_
* `Puppet master and agent on CoreOS`_
* https://hub.docker.com/r/epflsti/cluster.coreos.puppet/
* `Puppet Kubernetes module`_
* `Kubernetes on CoreOS`_

.. _Puppet on CoreOS: https://github.com/jumanjihouse/puppet-on-coreos
.. _Using Puppet with CoreOS Tools: https://puppet.com/blog/using-puppet-coreos-rkt-flannel-and-etcd
.. _Puppet master and agent on CoreOS: http://www.admintome.com/blog/configure-puppet-on-coreos/
.. _Puppet Kubernetes module: https://forge.puppet.com/puppetlabs/kubernetes
.. _Kubernetes on CoreOS: https://github.com/coreos/coreos-kubernetes

Questions?
----------

.. figure:: static/jlaw-questions.gif
    :align: center
    :height: 300px

Thank you!
==========

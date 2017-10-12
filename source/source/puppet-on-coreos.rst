Who Orchestrates the Orchestrators?
===================================

Managing Container Linux and Kubernetes with Puppet

https://slides.lucywyman.me/puppet-on-coreos.html

Roadmap
-------

* Why?
* How to manage CoreOS and K8s with Puppet
* Demo 

:code:`$ whoami`
----------------

.. rst-class:: build

    .. figure:: static/beaker-fire.gif
        :align: center
        :height: 300px

Lucy Wyman (lucyw)

Software Engineer

Puppet

Why This Doesn't Make Sense
---------------------------

.. rst-class:: build

* Containers are "immutable"
* CoreOS is "immutable"

  * Configured using `ignition`_ | `cloud-config`_

* Puppet is used to make changes to systems, and manage their lifecycle

.. _cloud-config: https://coreos.com/os/docs/latest/cloud-config.html
.. _ignition: https://coreos.com/ignition/docs/latest/

Why (or when) This Makes Sense
------------------------------

.. rst-class:: build

* Manage information about your entire infrastructure in one place
* When immutable infra doesn't work for you, but containers do

  * Systems aren't immutable, we just pretend they are!

* Handle configuration drift
* Add or modify services without restarting

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

Demo Time
---------

https://github.com/lucywyman/puppet-on-coreos-demo

The Shiny New
-------------

We have a `kubernetes module`_ that installs k8s now!

https://forge.puppet.com/puppetlabs/kubernetes


.. _kubernetes module: https://forge.puppet.com/puppetlabs/kubernetes

Demo Time
---------

https://github.com/puppetlabs/puppetlabs-kubernetes

Resources
---------

* `Puppet on CoreOS`_
* `Using Puppet with CoreOS Tools`_
* `Puppet master and agent on CoreOS`_
* https://hub.docker.com/r/epflsti/cluster.coreos.puppet/

.. _Puppet on CoreOS: https://github.com/jumanjihouse/puppet-on-coreos
.. _Using Puppet with CoreOS Tools: https://puppet.com/blog/using-puppet-coreos-rkt-flannel-and-etcd
.. _Puppet master and agent on CoreOS: http://www.admintome.com/blog/configure-puppet-on-coreos/

Questions?
----------

.. figure:: static/puppy-questions.gif
    :align: center
    :height: 400px

Thank you!
==========

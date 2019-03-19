=============================
hadoop-yarn-api-python-client
=============================

This codebase is originally written by toidi_ and can be found here_. This modified version is temporary and rolls in unreleased features currently part of the master branch. Once a new release has been officially cut, this repo will be destroyed.

Python client for Apache Hadoop® YARN API

Package documentation: python-client-for-hadoop-yarn-api.readthedocs.org_

REST API documentation: hadoop.apache.org_

------------
Installation
------------

From PyPI

::

    pip install yarn-api-client-fix

From source code

::

   git clone https://github.com/hansohn/hadoop-yarn-api-python-client.git
   pushd hadoop-yarn-api-python-client
   python setup.py install
   popd


Enabling support for Kerberos/SPNEGO Security

To avoid deployment issues on a non Kerberized environment, the `requests_kerberos`
dependency is optional and needs to be explicit installed in order to enable access
to YARN console protected by Kerberos/SPNEGO.

::

   pip install requests_kerberos


-----
Usage
-----

CLI interface
=============

::

   bin/yarn_client --help

alternative

::

   python -m yarn_api_client --help

Programmatic interface
======================

.. code-block:: python

   from yarn_api_client import ApplicationMaster, HistoryServer, NodeManager, ResourceManager

Changelog
=========

0.3.2-fix Release
   - Add HADOOP_CONF_DIR env functionality.

0.3.2 Release
   - Make Kerberos/SPNEGO dependency optional

0.3.1 Release
   - Fix cluster_application_kill API

0.3.0 Release
    - Add support for YARN endpoints protected by Kerberos/SPNEGO
    - Moved to `requests` package for REST API invocation
    - Remove `http_con` property, as connections are now managed by `requests` package

0.2.5 Release
    - Fixed History REST API

0.2.4 Release
    - Added compatibility with HA enabled Resource Manager

.. _python-client-for-hadoop-yarn-api.readthedocs.org: http://python-client-for-hadoop-yarn-api.readthedocs.org/en/latest/
.. _hadoop.apache.org: http://hadoop.apache.org/docs/stable/hadoop-yarn/hadoop-yarn-site/WebServicesIntro.html
.. _toidi: https://github.com/toidi
.. _here: https://github.com/toidi/hadoop-yarn-api-python-client

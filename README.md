rax-api-ref
===========

API reference pages for Rackspace APIs

Prerequisites
=============
To build the documentation, you must install `Apache Maven <http://maven.apache.org/>`

To install Maven 3 for Ubuntu 12.04 and later or Debian wheezy and later:

apt-get install maven

On Fedora 15 and later::

yum install maven3

Build
=====
The web pages are in the ``api-ref`` directory.

Run the ``mvn`` command in that directory.

cd api-ref
mvn clean generate-sources

The generated PDF documentation file is::

api-ref/target/docbkx/webhelp/api-quick-start-onepager-external/api-quick-start-onepager.pdf

The root of the generated HTML documentation is::

api-ref/target/docbkx/webhelp/api-quick-start-onepager-external/content/index.html

Test
====

Install the python tox package and run ``tox`` from the top-level
directory to use the same tests that are done as part of our Jenkins
gating jobs.

If you like to run individual tests, run:

* ``tox -e checkniceness`` - to run the niceness tests
* ``tox -e checksyntax`` - to run syntax checks
* ``tox -e checkdeletions`` - to check that no deleted files are referenced
* ``tox -e checkbuild`` - to actually build the manual

tox uses the `openstack-doc-tools package
<https://github.com/openstack/openstack-doc-tools>`_ for execution of
these tests. openstack-doc-tools has a requirement on maven for the
build check.
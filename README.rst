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

To build and test any of these documents:

#. Open a terminal window.

#. Change into a directory where you want to clone api-site.

#. Run this command to clone openstack/api-site:

        git clone https://github.com/openstack/api-site

#. CD into the api-site directory.

#. Run these commands to ensure you have the latest changes:

        git remote update
        git checkout master
        git pull origin master
        git review –d change-number /* where change-number is the change number of the review

#. Run this command to build the docs locally:

        mvn clean generate-sources

- The root of the generated HTML (API site) documentation is::

        api-site/api-ref/target/docbkx/html/api-ref.html

- The root of the generated API guide (in progress) is::

        api-site/api-guide/target/docbkx/webhelp/api-guide/index.html

- The generated PDFs for the API pages are at::

        api-site/api-ref-guides/target/docbkx/pdf/*.pdf

- The root of the API quick start is at::

        api-site/api-quick-start/target/docbkx/webhelp/api-quick-start-onepager-external/api-quick-start-onepager.pdf

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
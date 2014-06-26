docs-api-reference
==================

API reference pages for Rackspace APIs

Prerequisites
=============

To build the documentation, you must install `Apache Maven <http://maven.apache.org>`_.
    
To install Maven 3 for Ubuntu 12.04 and later or Debian wheezy and later::
    
    apt-get install maven
    
On Fedora 15 and later::
    
    yum install maven3
    
Locations of WADL files
=======================

- Auto Scale: `https://github.com/rackerlabs/otter.git <https://github.com/rackerlabs/otter.git>`_ (Maria Abrahms)
- Barbican: Coming Soon to: `git@github.com:dwcramer/barbican.git <git@github.com:dwcramer/barbican.git>`_		
- Cloud Backup:	`git@github.com:rackerlabs/docs-cloud-backup.git <git@github.com:rackerlabs/docs-cloud-backup.git>`_ (Catherine Richardson)	
- Cloud Big Data: `git@github.com:rackerlabs/docs-cloud-big-data.git <git@github.com:rackerlabs/docs-cloud-big-data.git>`_ (Catherine Richardson)	
- Cloud Block Storage: `git@github.com:rackerlabs/docs-cloud-block-storage.git <git@github.com:rackerlabs/docs-cloud-block-storage.git>`_ (Catherine Richardson)
- Cloud Databases: `https://github.com/rackerlabs/docs-cloud-databases.git <https://github.com/rackerlabs/docs-cloud-databases.git>`_ (Mike Asthalter)
- Cloud DNS: `https://github.com/rackerlabs/docs-cloud-dns.git <https://github.com/rackerlabs/docs-cloud-dns.git>`_ (Mike Asthalter)	
- Cloud Feeds: `git@github.com:rackerlabs/standard-usage-schemas.git <git@github.com:rackerlabs/standard-usage-schemas.git>`_ (atom_hopper.wadl) (Constanze Kratel)
- Cloud Files: `git@github.com:rackerlabs/docs-cloud-files.git <git@github.com:rackerlabs/docs-cloud-files.git>`_ (Catherine Richardson)
- Cloud Identity 3.x: `git@github.rackspace.com:IX/auth-3.0.git <git@github.rackspace.com:IX/auth-3.0.git>`_ (Margaret Eker)
- Cloud Identity 2.x: `git@github.rackspace.com:IX/auth-2.0.git <git@github.rackspace.com:IX/auth-2.0.git>`_, `https://github.com/rackerlabs/docs-cloud-identity.git <https://github.com/rackerlabs/docs-cloud-identity.git>`_, and `https://raw.githubusercontent.com/rackerlabs/docs-api-reference/master/api-ref/src/wadls/cloud-identity/wadl/RAX-AUTH.wadl <https://raw.githubusercontent.com/rackerlabs/docs-api-reference/master/api-ref/src/wadls/cloud-identity/wadl/RAX-AUTH.wadl>`_ (Margaret Eker)
- Cloud Images:	`https://github.com/rackerlabs/docs-cloud-images.git <https://github.com/rackerlabs/docs-cloud-images.git>`_ (Cat Lookabaugh)
- Cloud Load Balancers: `https://github.com/rackerlabs/docs-cloud-load-balancers.git <https://github.com/rackerlabs/docs-cloud-load-balancers.git>`_ (Mike Asthalter)		
- Cloud Monitoring: `https://github.com/rackerlabs/docs-cloud-monitoring.git <https://github.com/rackerlabs/docs-cloud-monitoring.git>`_ (Maria Abrahms)
- Cloud Networks: `https://github.com/catlook/networks2.git <https://github.com/catlook/networks2.git>`_, and `https://github.com/rackerlabs/docs-cloud-networks.git <https://github.com/rackerlabs/docs-cloud-networks.git>`_ (Cat Lookabaugh)
- Cloud Orchestration: `git@github.com:rackerlabs/docs-cloud-orchestration.git <git@github.com:rackerlabs/docs-cloud-orchestration.git>`_  (Mike Asthalter)
- Cloud Queues:	`git@github.com:rackerlabs/docs-cloud-queues.git <git@github.com:rackerlabs/docs-cloud-queues.git>`_ (Catherine Richardson)
- Cloud Servers 1.x: likely will not be done. Product will be end-of-lifed this year. (Cat Lookabaugh)
- Cloud Servers 2.x: `https://github.rackspace.com/IX/cloud-server.git <https://github.rackspace.com/IX/cloud-server.git>`_ (in progress/unpublished) (Cat Lookabaugh)
- Email & Apps:	`https://github.com/rackerlabs/docs-api-reference/tree/master/api-ref/src/wadls/email-apps/wadl <https://github.com/rackerlabs/docs-api-reference/tree/master/api-ref/src/wadls/email-apps/wadl>`_ (for WADLs that generates API site) and `https://github.rackspace.com:IX/email-and-apps.git <https://github.rackspace.com:IX/email-and-apps.git>`_ (for actual source) (Rose Coste)
- Object Rocket: (Margaret Eker)

To update or add WADLs to API pages
===================================
    
#. Complete steps 1 and 2 in this `procedure <https://one.rackspace.com/display/devdoc/Github+workflow+howto>`_ for this project (rackerlabs/docs-api-reference).                     
        
#. To add a WADL for a product, go to the ``docs-api-reference/api-ref/src/docbkx`` folder.
        
#. If a ch_{product}-{version}.xml file exists for your product already (such as ch_dns-v1.xml), open it. If not, create a file for your product that uses the ch_{product}-{version}.xml naming convention and open it.
        
#. Update this file to point to your WADL in your repository. To do so, you need the *raw* link to the WADL.
   To get that, navigate to your WADL file in your project repository, click on the file name to open a view of the
   file. Then, click **Raw** at the top of the file. Then, copy the URL in the address bar.
        
#. In your ch_{product}-{version}.xml file, add code like this to point to your WADL and methods::
        
        <chapter xmlns="http://docbook.org/ns/docbook"
            xmlns:xi="http://www.w3.org/2001/XInclude"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xmlns:linkend="http://www.w3.org/1999/linkend"
            xmlns:xref="http://www.w3.org/1999/xref"
            xmlns:wadl="http://wadl.dev.java.net/2009/02"
            version="5.0-extension RackBook-2.0" xml:id="dns-v1.0">
            <title>Cloud DNS API v1.0</title>
            <wadl:resources xmlns:wadl="http://wadl.dev.java.net/2009/02"
                href="https://raw.githubusercontent.com/rackerlabs/docs-cloud-dns/master/src/main/resources/wadl/dns.wadl"
            />
        </chapter>
        
#. If an api-ref-{product}.xml file exists for your product, do nothing. Otherwise, copy another product api-ref-{product}.xml file and rename it to your product name.
   For example, api-ref-dns.xml. 
        
#. Edit the api-ref-{product}.xml file and add this exact markup, using an appropriate xml:id, title, and included ch_{product}-{version}.xml file name::
        
        <?xml version="1.0" encoding="UTF-8"?>
        <book xmlns="http://docbook.org/ns/docbook"
            xmlns:xi="http://www.w3.org/2001/XInclude"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xmlns:linkend="http://www.w3.org/1999/linkend"
            xmlns:xref="http://www.w3.org/1999/xref"
            xmlns:wadl="http://wadl.dev.java.net/2009/02"
            version="5.0-extension RackBook-2.0"
            xml:id="api.rackspace.com-dns">
            <info>
                <title>Cloud DNS APIs</title>
                <copyright>
                    <year>2010-2014</year>
                </copyright>
                <legalnotice role="rs-api">
                    <para/>
                </legalnotice>
                <annotation>
                    <xi:include href="itemizedlist-service-list.xml"/>
                </annotation>
            </info>
            <xi:include href="ch_dns-v1.xml"/>
        </book> 
        
#. Update the itemizedlist-service-list.xml file to add your product. For example::
        
        <listitem>
            <para><link xlink:href="api-ref-dns.html">Cloud DNS API</link></para>
        </listitem>
        
#. Update the pom.xml file to add instructions to build your api-ref-{product}.xml file. Follow the pattern in that file.
        
#. Do a remote build (mvn clean generate-sources) to make sure that things work okay.
        
#. When you are ready to commit, and periodically if you want the latest stuff, merge changes from remote project into your local fork. See `merge changes from upstream to fork <https://one.rackspace.com/display/devdoc/Merge+changes+from+upstream+to+fork>`_.
            
#. Push your branch to your fork::
            
       $ git push origin {mybranch}
            
The root of the generated HTML (API site) documentation is ``docs-api-reference/api-ref/target/docbkx/html/api-ref.html``.
            
Test
====
            
Install the python tox package and run ``tox`` from the top-level
directory to use the same tests that are done as part of our Jenkins
gating jobs.
            
If you like to run individual tests, run::
            
* ``tox -e checkniceness`` - to run the niceness tests
* ``tox -e checksyntax`` - to run syntax checks
* ``tox -e checkdeletions`` - to check that no deleted files are referenced
* ``tox -e checkbuild`` - to actually build the manual
            
tox uses the `openstack-doc-tools package
<https://github.com/openstack/openstack-doc-tools>`_ for execution of
these tests. openstack-doc-tools has a requirement on maven for the
build check.
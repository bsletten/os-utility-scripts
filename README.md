Overview
=========

Operating system scripts written for Mac OS X in Groovy that support the use of NetKernel and IntelliJ.

Directory Structure
-------------------

While these scripts should work with any directory structure, they were designed with the following structure in use:

<pre>
../source/netkernel/module/{module-uri}
../source/netkernel/package/{package-name}
</pre>

Installation
------------

Install Groovy on your computer. The scripts were developed using Groovy 1.8.4

Download these scripts into a "bin" directory. I use ~/bin and set my path to include this directory

Usage
-----

initializeModule.gy

This script will initialize a NetKernel and IntelliJ module based on the name of the directory in which it is run.
If the directory is:

<pre>
../source/netkernel/module/urn.net.databliss.netkernel.layer0
</pre>

and the initializeModule.gy script is run in this directory, it will create the following files and 
associated directories:

<pre>
../src/main/java/net/databliss/netkernel/layer0/doc/license-commercial.txt
../src/main/java/net/databliss/netkernel/layer0/doc/license-mit.txt
../src/main/java/net/databliss/netkernel/layer0/doc/title.txt
../src/main/java/resources/etc/messages.properties
../src/main/resources/module.xml
../src/main/resources/etc/system/Books.xml
../src/main/resources/etc/system/Docs.xml
../src/main/resources/resources/mappers/httpMapper.xml
../src/main/resources/resources/mappers/serviceMapper.xml
../src/urn.net.databliss.netkernel.layer0.iml
</pre>

The *.iml file is an IntelliJ module definition file that is ready to be imported into an IntelliJ project.


installModules.gy

This script will create a file to be placed in NetKernel's directory structure to allow it to load
the modules under development. 
First, create an IntelliJ project (using the .idea option for meta data), 
import the constituent modules and then from the project, run this script.
The script will find NetKernel's installation directory (NetKernel must be running)
and create a file {project-name}.xml within the [install]/etc/modules.d directory.


removeModules.gy

When run from the IntelliJ project directory, this will remove the file
{project-name}.xml from the NetKernel [install]/etc/modules.d directory
and hence remove these modules from the running instance of Netkernel.

Services
========

Girder
------

`Girder <https://girder.readthedocs.org>`_ is a free and open source web-based
data management platform developed by `Kitware <http://www.kitware.com/>`_ as
part of the `Resonant <http://resonant.kitware.com/>`_ data and analytics
ecosystem. We host our own instance of the Girder at `https://girder.hub.yt/
<https://girder.hub.yt>`_. It offers additional features enabled via `ytHub
plugin <https://github.com/data-exp-lab/girder_ythub>`_ which currently allows
to:

 * create persistent notebooks, which have direct access to the Girder's data
 * manage running notebooks directly from the Girder's UI

For some basic information about how to use Girder, see :doc:`Girder 101 </girder>`.

curldrop
--------

curldrop is a simple web application that allows you to upload and download
files straight from your Terminal with curl.  It was initially developed by
`Kevin Kennell <https://github.com/kennell/curldrop>`_ and later `forked
<https://github.com/xarthisius/curldrop>`_ and adjusted for yt Hub's needs. 

Basic usage::

    $ curl -T filename http://use.yt/upload/   # uploads the file, trailing backslash is important
    $ curl -JO http://use.yt/upload/hash       # downloads the file

Note that the trailing backslash at the end of the upload URL is necessary. If
you do not include it, the file will be uploaded to the curldrop as a file named
"upload". If you have done everything correctly, running the download command
should download a file with the same filename as the one you uploaded.

SAGE2
-----

`SAGE2 <http://sage2.sagecommons.org/>`_ is a software enabling groups to work
in front of large shared displays in order to solve problems that required
juxtaposing large volumes of information in ultra high-resolution. In yt Hub
it's used to provide temporary remote desktops for screen casting during
videoconferences. You can spawn new screen server by following
`http://use.yt/startsage/ <http://use.yt/startsage>`_. 

After few seconds you should be redirected to new SAGE2 server with unique url:
`https://hub.yt/sage/HASH/index.html`. 

Remote desktop can be viewed using `https://hub.yt/sage/HASH/display.html`. 

Please refer to `SAGE2 documentation
<http://sage2.sagecommons.org/instructions/>`_ for additional details.

JupyterHub
----------

`JupyterHub <https://github.com/jupyter/jupyterhub>`_ is a multi-user server
that manages and proxies multiple instances of the single-user JupyterLab
server. We currently offer two instances of JupyterHub

 * public - `https://use.yt/ <https://use.yt>`_
 * DXL specific - `https://hub.yt/jupyter-dev/ <https://hub.yt/jupyter-dev/>`_

Public JupyterHub
^^^^^^^^^^^^^^^^^
In order to access `https://use.yt/ <https://use.yt>`_ users are required to use
their Bitbucket's credentials. Inside JupyterLab yt's introductory notebooks are
provided, along with access to all example datasets that are available at
`https://yt-project.org/data/ <https://yt-project.org/data/>`_. 

.. warning::
   There is no persistent storage available, i.e. all data is deleted after
   JupyterLab is shut down. Make sure you download your notebooks before logging
   out. 

DXL JupyterHub
^^^^^^^^^^^^^^
JupyterLab can be accesed using NCSA credentials by all members of DXL group. 
During login phase, the credentials are used to generate OTP token for OwnCloud, 
which allows to mount user's OwnCloud directory as home directory making data in
notebooks persistent. Docker images used in this instance of JupyterLab provide
several ipython kernels via independent conda environments. Current setup
offers:

 * yt (stable release) using both python 3.5 and 2.7
 * yt (current tip) using both python 3.5 and 2.7
 * IJulia (with Iyt)

OwnCloud
--------

`OwnCloud <https://owncloud.org>`_ is free and open source software that
operates as a Dropbox-like cloud storage system. The Hub's instance is provided
at `https://hub.yt/owncloud/ <https://hub.yt/owncloud/>`_ and can be accessed
using NCSA's LDAP credentials (DXL members)

REST API
--------

t.b.d.

MediaGoblin
-----------
`MediaGoblin <http://mediagoblin.org/>`_ is a free software media publishing
platform. Its current usage within the Hub is limited to statically serving
images that and be anonymously uploaded using curldrop. 

Basic usage::

   $ curl -T example.jpg https://images.hub.yt/uploads/
   Open in your browser: https://images.hub.yt/u/fido/m/a7f673af-jpg/
   Download: curl -JO https://images.hub.yt/upload/a7f673af
   Delete: curl -X DELETE https://images.hub.yt/upload/f4a1993d


DXL tools
---------

t.b.d.

Jenkins
-------

`Jenkins CI <https://jenkins-ci.org>`_ is the leading open-source continuous
integration server. Apart from running yt's test suite, `our instance
<https://test.yt-project.org/>`_ is also used for automatic build and deployment
of yt Hub's services and web content.

.. vim: tw=80

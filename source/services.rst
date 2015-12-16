Services
========

curldrop
--------

curldrop is a simple web application that allows you to upload and download
files straight from your Terminal with curl.  It was initially developed by
`Kevin Kennell <https://github.com/kennell/curldrop>`_ and later `forked
<https://github.com/xarthisius/curldrop>`_ and adjusted for yt Hub's needs. 

Basic usage::

    $ curl -T filename http://use.yt/upload/   # uploads the file
    $ curl -JO http://use.yt/upload/hash       # downloads the file

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

REST API
--------

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

Jenkins
-------

`Jenkins CI <https://jenkins-ci.org>`_ is the leading open-source continuous
integration server. Apart from running yt's test suite, `our instance
<https://test.yt-project.org/>`_ is also used for automatic build and deployment
of yt Hub's services and web content.

.. vim: tw=80

CKAN: The Open Source Data Portal Software
==========================================

.. image:: https://img.shields.io/badge/license-AGPL-blue.svg?style=flat
    :target: https://opensource.org/licenses/AGPL-3.0
    :alt: License

.. image:: https://img.shields.io/badge/docs-latest-brightgreen.svg?style=flat
    :target: http://docs.ckan.org
    :alt: Documentation
.. image:: https://img.shields.io/badge/support-StackOverflow-yellowgreen.svg?style=flat
    :target: https://stackoverflow.com/questions/tagged/ckan
    :alt: Support on StackOverflow

.. image:: https://circleci.com/gh/ckan/ckan.svg?style=shield
    :target: https://circleci.com/gh/ckan/ckan
    :alt: Build Status

.. image:: https://coveralls.io/repos/github/ckan/ckan/badge.svg?branch=master
    :target: https://coveralls.io/github/ckan/ckan?branch=master
    :alt: Coverage Status

.. image:: https://badges.gitter.im/gitterHQ/gitter.svg
    :target: https://gitter.im/ckan/chat
    :alt: Chat on Gitter

**CKAN is the world’s leading open-source data portal platform**.
CKAN makes it easy to publish, share and work with data. It's a data management
system that provides a powerful platform for cataloging, storing and accessing
datasets with a rich front-end, full API (for both data and catalog), visualization
tools and more. Read more at `ckan.org <http://ckan.org/>`_.


Installation
------------

See the `CKAN Documentation <http://docs.ckan.org>`_ for installation instructions.

My notes about installation (JCC):
----------------------------------
I tried to install using Docker Windows version with several methods and the result
  was always the same: Problem binding port for ckan and datapusher. I tried changing
  .env variable CKAN_URL and asign http://127.0.0.1:5000 instead http://localhost:5000
  
CKAN_MAX_UPLOAD_SIZE_MB=5000 variable added to contrib/docker/.env file

I created two new branches tags/2.8.2.jcc and tags/2.8.3.jcc to include CKAN_MAX_UPLOAD_SIZE_MB
variable in contrib/docker/.env.test versions 2.8.2 and 2.8.3  
    
Conclusions:
------------
Use Docker Linux instead Docker Windows
Some users said that using 2.8.3 and 2.8.2 instead latest version from https:/github.com/ckan
    works, but it doesn't work for me.
In case of Docker Linux there are no problem with binding ports between host and client container.

In my opinion the problem will be some updated library or the installation process that doesn't
include configparser module. I hope next ckan version will solve this problem!
  
Usefull links:
--------------
https://docs.ckan.org/en/2.8/maintaining/installing/install-from-docker-compose.html

https://github.com/ckan/ckan/issues/5212

Doc about ImportError: No module named configparser.
Solution: Use an stable version git checkout tags/2.8.3 
It doesn't work for me!

Basic install instructions:
---------------------------
   
* git clone git@github.com:ckan/ckan
* cd ckan/contrib/docker
* cp .env.template .env
* docker-compose up

Support
-------
If you need help with CKAN or want to ask a question, use either the
`ckan-dev`_ mailing list, the `CKAN chat on Gitter`_, or the `CKAN tag on Stack Overflow`_ (try
searching the Stack Overflow and ckan-dev `archives`_ for an answer to your
question first).

If you've found a bug in CKAN, open a new issue on CKAN's `GitHub Issues`_ (try
searching first to see if there's already an issue for your bug).

If you find a potential security vulnerability please email security@ckan.org,
rather than creating a public issue on GitHub.

.. _CKAN tag on Stack Overflow: http://stackoverflow.com/questions/tagged/ckan
.. _archives: https://www.google.com/search?q=%22%5Bckan-dev%5D%22+site%3Alists.okfn.org.
.. _GitHub Issues: https://github.com/ckan/ckan/issues
.. _CKAN chat on Gitter: https://gitter.im/ckan/chat


Contributing to CKAN
--------------------

For contributing to CKAN or its documentation, see
`CONTRIBUTING <https://github.com/ckan/ckan/blob/master/CONTRIBUTING.rst>`_.

Mailing List
~~~~~~~~~~~~

Subscribe to the `ckan-dev`_ mailing list to receive news about upcoming releases and
future plans as well as questions and discussions about CKAN development, deployment, etc.

Community Chat
~~~~~~~~~~~~~~

If you want to talk about CKAN development say hi to the CKAN developers and members of
the CKAN community on the public `CKAN chat on Gitter`_. Gitter is free and open-source;
you can sign in with your GitHub, GitLab, or Twitter account.

The logs for the old `#ckan`_ IRC channel (2014 to 2018) can be found here:
https://github.com/ckan/irc-logs.

Wiki
~~~~

If you've figured out how to do something with CKAN and want to document it for
others, make a new page on the `CKAN wiki`_ and tell us about it on the
ckan-dev mailing list or on Gitter.

.. _ckan-dev: http://lists.okfn.org/mailman/listinfo/ckan-dev
.. _#ckan: http://webchat.freenode.net/?channels=ckan
.. _CKAN Wiki: https://github.com/ckan/ckan/wiki
.. _CKAN chat on Gitter: https://gitter.im/ckan/chat


Copying and License
-------------------

This material is copyright (c) 2006-2018 Open Knowledge Foundation and contributors.

It is open and licensed under the GNU Affero General Public License (AGPL) v3.0
whose full text may be found at:

http://www.fsf.org/licensing/licenses/agpl-3.0.html

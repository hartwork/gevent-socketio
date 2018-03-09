PLEASE NOTE
===========
What you see here is a post-0.3.6 Git version of ``gevent-socketio``
maintained by `Sebastian Pipping <https://github.com/hartwork>`_ (``@hartwork``)
branded ``gevent-socketio-hartwork`` for distinction on PyPI.

The idea is to deviate from upstream ``gevent-socketio`` as little as possible
and mirror branch ``master`` unmodified.  Maintenance is done on
`branch hartwork-master <https://github.com/hartwork/gevent-socketio/commits/hartwork-master>`_.

Over release 0.3.6, these notable commits are included, from most recent to oldest:

* `Add support for Django 1.10 <https://github.com/hartwork/gevent-socketio/commit/0e1d9d5d461530724522d12d592cde9fc68264a9>`_
  by `Lucas Connors <https://github.com/RevolutionTech>`_ (``@RevolutionTech``)
* `Drop support for Django 1.3 <https://github.com/hartwork/gevent-socketio/commit/9a6e024e056964c3d860316d5b13b295ed80d379>`_
  by `Lucas Connors <https://github.com/RevolutionTech>`_ (``@RevolutionTech``)
* `Fixed import to support Django>=1.9 <https://github.com/hartwork/gevent-socketio/commit/acf095b78208edb59b5873662653e12773add3cc>`_
  by `Chris Spencer <https://github.com/chrisspen>`_ (``@chrisspen``)
* `Leadership note <https://github.com/hartwork/gevent-socketio/commit/1c84627980c0b77f8f9005fdbcc916ca33d0e4d1>`_
  by `Alexandre Bourget <https://github.com/abourget>`_ (``@abourget``)
* `Full Python 2+3 support <https://github.com/hartwork/gevent-socketio/commit/12da9667deba432d8917129afab1daa86c20ec84>`_
  by `Eugene Pankov <https://github.com/Eugeny>`_ (``@Eugeny``)

The remainder of this document is the original documentation, except with
links adjusted.  Enjoy.

Sebastian Pipping


Presentation
============

.. image:: https://secure.travis-ci.org/hartwork/gevent-socketio.png?branch=master

``gevent-socketio`` is a Python implementation of the Socket.IO
protocol, developed originally for Node.js by LearnBoost and then
ported to other languages.  Socket.IO enables real-time web
communications between a browser and a server, using a WebSocket-like
API.  One aim of this project is to provide a single ``gevent``-based
API that works across the different WSGI-based web frameworks out
there (Pyramid, Pylons, Flask, web2py, Django, etc...).  Only ~3 lines
of code are required to tie-in ``gevent-socketio`` in your framework.
Note: you need to use the ``gevent`` python WSGI server to use
``gevent-socketio``.

Community, rise up!
===================

ANNOUNCEMENT: This project is in need of a solid maintainer to navigate through the 27+ open Pull Requests, merge what needs to be merged, and continue on with newer developments. @abourget is not putting as much time as he'd like on this project these days.  This project has nearly 1000 GitHub Stars.. it's used by major corporations. It's a great project for you to lead. Contact @abourget on Twitter @bourgetalexndre to take more leadership.


Technical overview
==================

Most of the ``gevent-socketio`` implementation is pure Python.  There
is an obvious dependency on ``gevent``, and another on
``gevent-websocket``.  There are integration examples for Pyramid, Flask,
Django and BYOF (bring your own framework!).


Documentation and References
============================

You can read the renderered Sphinx docs at:

* http://readthedocs.org/docs/gevent-socketio/en/latest/

Discussion happen in the Github issue tracking:

* https://github.com/hartwork/gevent-socketio/issues
* (and https://github.com/abourget/gevent-socketio/issues)

You can also contact the maintainer:

* sebastian@pipping.org


Installation
============

You can install with standard Python methods::

   pip install gevent-socketio-hartwork

or from source::

   git clone git://github.com/hartwork/gevent-socketio.git
   cd gevent-socketio
   python setup.py install

For development, run instead of ``install``::

   python setup.py develop

If you want to do all of that in a virtualenv, run::

   virtualenv env
   . env/bin/activate
   python setup.py develop   # or install

To execute all tests, run:

    tox

To execute all tests for a specific Python version, run something like:

    tox -e py27
    
To execute a specific test for a specific Python version, run something like:

    tox -e py27 -- test_packet.py::TestEncodeMessage::test_encode_event

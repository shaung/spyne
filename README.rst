
About
=====

Spyne aims to save the protocol implementers the hassle of implementing their
own remote procedure call api and the application programmers the hassle of
jumping through hoops just to expose their services using multiple protocols and
transports.

In other words, Spyne is framework for building distributed solutions that
strictly follow the MVC pattern, where Model = `spyne.model`,
View = `spyne.protocol` and Controller = `user code`.

Spyne comes with the implementations of popular transport, protocol and
interface document standards along with a well-defined API that lets you
build on existing functionality.

Spyne currently supports the WSDL 1.1 interface description standard,
along with SOAP 1.1 and the so-called HttpRpc and JsonObject protocols which
can be transported via Http or ZeroMQ. The transports can be used in both a
client or server setting.

The following are the primary sources of information about spyne:

* The latest documentation for Spyne can be found at: http://arskom.github.com/spyne
* The official source code repository is at: https://github.com/arskom/spyne
* The official spyne discussion forum is at: http://mail.python.org/mailman/listinfo/soap
* You can download Spyne packages from `github <http://github.com/arskom/spyne/downloads>`_
  or `pypi <http://pypi.python.org/pypi/spyne>`_.

Spyne is a generalized version of a Soap library known as soaplib. The following
legacy versions of soaplib are also available in the source repository at github
as branches:

* Soaplib-0.8 branch: http://github.com/arskom/spyne/tree/soaplib-0_8
* Soaplib-1.0 branch: http://github.com/arskom/spyne/tree/soaplib-1_0
* Soaplib-2.0 was never released as a stable package, but the branch is still
  available: http://github.com/arskom/spyne/tree/soaplib-2_0

Requirements
============

Spyne reportedly runs on any version of Python from 2.4 through 2.7. We're also
looking for volunteers to test Python 3.x.

While the aim is to have no requirements besides the standard Python library for
the Spyne core, the following packages are needed if you want to run any
Spyne service at all:

* `lxml <http://codespeak.net/lxml/>`_
* `pytz <http://pytz.sourceforge.net/>`_

both of which are available through ``easy_install``.

Additionally the following software packages are needed for various subsystems
of Spyne:

* `SQLAlchemy <http://sqlalchemy.org>`_ for :class:`spyne.model.table.TableModel`.
* `pyzmq <https://github.com/zeromq/pyzmq>`_ for
  :class:`spyne.client.zeromq.ZeroMQClient` and
  :class:`spyne.server.zeromq.ZeroMQServer`.
* A Wsgi server of your choice to wrap :class:`spyne.server.wsgi.WsgiApplication`.
* `Werkzeug <http://werkzeug.pocoo.org/>`_ is needed for :class:`spyne.protocol.http.HttpRpc`.

You are advised to add these as requirements to your own projects, as these are
only optional dependencies of Spyne, thus not handled in its setup script.

Installing
==========

You can get spyne via pypi: ::

    easy_install spyne

or you can clone from github: ::

    git clone git://github.com/arskom/spyne.git

or get the source distribution from one of the download sites and unpack it.

To install from source distribution, you should run its setup script as usual: ::

    python setup.py install

To run the non-interop tests use: ::

    python setup.py test

And if you want to make any changes to the spyne code, it's more comfortable to
use: ::

    python setup.py develop

Contributing
============

The main developers of Spyne lurk in the `official soap implementors
forum <http://mail.python.org/mailman/listinfo/soap/>`_. kindly operated
by python.org. That's mostly because Spyne is the continuation of soaplib,
but also because soap is an important part of Spyne.

If you wish to contribute to Spyne's development, create a personal fork
on GitHub.  When you are ready to push to the upstream repository,
submit a pull request to bring your work to the attention of the core
committers. They will respond to review your patch and act accordingly.

To save both parties time, make sure the existing tests pass. If you are
adding new functionality or fixing a bug, please have the accompanying test.
This will both help us increase test coverage and insure your use-case
is immune to feature code changes. You could also summarize in one or
two lines how your work will affect the life of spyne users in the
CHANGELOG file.

Please follow the `PEP 8 <http://www.python.org/dev/peps/pep-0008/>`_
style guidelines for both source code and docstrings.

We could also use help with the docs, which are built from
`restructured text <http://docutils.sourceforge.net/rst.html>`_ using
`Sphinx <http://sphinx.pocoo.org>`_.

Regular contributors may be invited to join as a core Spyne committer on
GitHub. Even if this gives the core committers the power to commit directly
to the core repository, we highly value code reviews and expect every
significant change to be committed via pull requests.

Submitting Pull Requests
------------------------

Github's pull-request feature is awesome, but
there's a subtlety that's not totally obvious for newcomers: If you continue
working on the branch that you used to submit a pull request, your commits will
"pollute" the pull request until it gets merged. This is not a bug, but a
feature -- it gives you the ability to address reviewers' concerns without
creating pull requests over and over again. So, if you intend to work on other
parts of spyne after submitting a pull request, please do move your work to its
own branch and never submit a pull request from your master branch. This will
give you the freedom to continue working on spyne while waiting for your pull
request to be reviewed.

.. -*- mode: rst; coding: utf-8 -*-

====================================================================================
sphinx-server - A minimalistic server for uploading and viewing sphinx documentation
====================================================================================

:Authors: Roman Mohr <roman@fenkhuber.at>
:Version: 0.1.0.a1
:Date: 2013-05-26
:Code: https://github.com/rmohr/sphinx-server

.. contents:: Table of Contents
  :backlinks: top

sphinx-server is a minimal sphinx documentation hosting server. It is
compatible with Sphinx-PyPi-upload_.

Installation and Usage
======================

Download a WSGI HTTP Server::

    pip install gunicorn

Install sphinx-server::

    git clone git://github.com/rmohr/sphinx-server.git
    cd sphinx-server
    pip install .

Run the server::

    gunicorn -w 1 'sphinxserver:app(home="root/folder")' -b 127.0.0.1:8080

Upload the documentation of your project::

    cd /your/project/path
    python setup.py upload_sphinx --repository=http://127.0.0.1:8080

Browse the documentation::

    firefox http://127.0.0.1:8080/your_project_name/

.. _Sphinx-PyPI-upload: https://pypi.python.org/pypi/Sphinx-PyPI-upload
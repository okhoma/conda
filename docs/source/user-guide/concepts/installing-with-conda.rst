=====================
Installing with conda
=====================

.. image:: /img/installing-with-conda.png
    :align: right

.. _installing-with-conda:


To install conda packages, in the terminal or an Anaconda Prompt, run::

  conda install [packagename]


During the install process, files are extracted into the specified
environment, defaulting to the current environment if none is specified.
Installing the files of a conda package into an
environment can be thought of as changing the directory to an
environment, and then downloading and extracting the artifact
and its dependencies---all with the single
``conda install [packagename]`` command.

Read more about :doc:`conda environments and directory structure <../concepts/environments>`.

* When you ``conda install`` a package that exists in a channel and has no dependencies, conda:

  * looks at your configured channels (in priority)

  * reaches out to the repodata associated with your channels/platform

  * parses repodata to search for the package

  * once the package is found, conda pulls it down and installs

Conda update versus conda install
=================================

``conda update`` is used to update to the latest compatible version.
``conda install`` can be used to install any version.
 
Example:

* If Python 2.7.0 is currently installed, and the latest version of Python 2 is 2.7.5, then ``conda update python`` installs Python 2.7.5. It does not install Python 3.5.2.

* If Python 3.4.0 is currently installed, and the latest version of Python is 3.5.2, then ``conda install python=3`` installs Python 3.5.2.
 
Conda uses the same rules for other packages. ``conda update`` always installs the highest version with the same major version number, whereas ``conda install`` always installs the highest version.


Installing conda packages offline
=================================

To install conda packages offline, run:
``conda install /path-to-package/package-filename.tar.bz2/``
 
If you prefer, you can create a /tar/ archive file containing
many conda packages and install them all with one command:
``conda install /packages-path/packages-filename.tar``

.. note::
   If an installed package does not work, it may be missing
   dependencies that need to be resolved manually.
 
Installing packages directly from the file does not resolve
dependencies.

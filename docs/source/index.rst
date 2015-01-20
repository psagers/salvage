Salvage
=======

.. include:: ../../README.rst


Installation
------------

    ``$ pip install salvage``

This package will just install the `salvage` executable. Salvage does not depend
on any Python packages, but it does require `gpg <https://www.gnupg.org/>`_ to
handle the cryptography.

The installed executable is packaged as a standalone script so that it can be
bundled with recovery kits and run without installation.


Quick Start
-----------

To create a new :term:`recovery kit` for five :term:`participants` with a
:term:`threshold` of three:

    ``$ salvage split -n 5 -t 3 path/to/source/dir``

This will create five :term:`shares`, each containing a secure :term:`locker`
and a :term:`manifest`. To unpack the locker:

    ``$ salvage recover path/to/share1 path/to/share2 path/to/share3``

The three paths must be three of the shares generated in the first step. The
master key will be reconstructed and the locker will be decrypted and unpacked.

See ``salvage -h`` for additional options.


Glossary
--------

Here are a few terms that are used in a consistent manner.

.. glossary::

    kit
    recovery kit
        The output of ``salvage split``. The kit consists of multiple
        :term:`shares`, one for each :term:`participant`. On recovery, a kit can
        also refer to a partial set of the original shares.

    share
    shares
        A portion of a :term:`recovery kit` allocated to one
        :term:`participant`. At minimum, this consists of a :term:`locker` and a
        :term:`manifest`.

    locker
    lockers
        An encrypted archive containing the data to be protected.

    manifest
        The metadata of a :term:`share`, especially the key material that can be
        recombined into a master key.

    participant
    participants
        A person or entity that will hold one :term:`share` of the :term:`kit`.

    threshold
        The number of shares that must be present in order to access the
        :term:`locker`.


Details
-------

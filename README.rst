Salvage stores sensitive information such that no single person is able to
access it, but multiple people collaborating may. This is useful for storing
information with both a low risk of losing access to it and a low risk of
accidental exposure. A classic application is to create a "recovery kit" for a
server or infrastructure, which can be used in the event that conventionally
stored keys and credentials become lost or unavailable.

Salvage works by encrypting a file or directory with a random master key and
then applying a simple key-splitting scheme to distribute the key across
multiple shares. You can create a kit for any number of participants with any
threshold required to recover the information. For example, you might create a
kit for five people, any three of which may combine their shares to recover the
data.

Salvage runs under Python 2.7 plus Python 3.2 and later. The only external
dependency is `gpg <https://www.gnupg.org/>`_, for the cryptography. For maximum
utility, it is packaged as a single flat Python script that can be run with no
installation. The algorithms and file formats are simple and carefully
documented to ensure that recovery is always possible even if this software is
unavailable for some reason.

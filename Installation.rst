Installation
============

This pages contains instructions on how to install this module on your machine.
There are several ways to achieve that. Each method is described below.

..  warning::
    You cannot mix the different methods. Especially, **you must use the same
    method to install this module as the one you selected for Erebot itself**.

..  contents::

..  note::
    We recommend that you install this module using `Erebot's PEAR channel`_.
    This will result in a system-wide installation which can be upgraded
    very easily later.
    If this is not feasible for you or if you prefer to keep the installation
    local (for a single user), we recommend that you go the PHAR way.
    Installation from sources is reserved for advanced installations
    (developers).


Installation from Erebot's PEAR channel
---------------------------------------

This is by far the simplest way to install the module.
Hence, it's the recommended way for beginners.
Just use whatever tool your distribution provides to manage PEAR packages:

* Either `pear`_ (traditionnal tool)
* or `pyrus`_ (new experimental tool meant to replace pear someday)

..  warning::
    Pyrus currently has issues with some PEAR packages. It is thus recommended
    that you use the regular pear tool to install Erebot.
    See https://github.com/pyrus/Pyrus/issues/26 for more information.

You can install (**as a privileged user**) either the latest stable release
using a command such as:

..  sourcecode:: bash

    $ pear channel-discover pear.erebot.net
    $ pear install erebot/<module>

... or you can install the latest unstable version instead, using:

..  sourcecode:: bash

    $ pear channel-discover pear.erebot.net
    $ pear install erebot/<module>-alpha

Please note that the ``channel-discover`` command needs to be run only once
(pear and pyrus will refuse to discover a PEAR channel more than once anyway).
To use Pyrus to manage PEAR packages instead of the regular Pear tool,
just replace ``pear`` with ``pyrus`` in the commands above.


Installation using PHAR archives
--------------------------------



..  todo::
    Explain how to do this.


Installation from source
------------------------

First, make sure a git client is installed on your machine.
Under Linux, **from a root shell**, run the command that most closely matches
the tools provided by your distribution:

..  sourcecode:: bash

    # For apt-based distributions such as Debian or Ubuntu
    $ apt-get install git

    # For yum-based distributions such as Fedora / RHEL (RedHat)
    $ yum install git

    # For urpmi-based distributions such as SLES (SuSE) or MES (Mandriva)
    $ urpmi git

..  note::
    Windows users may be interested in installing `Git for Windows`_ to get
    an equivalent git client. Also, make sure that ``git.exe`` is present
    on your account's ``PATH``. If not, you'll have to replace ``git`` by
    the full path to ``git.exe`` on every invocation
    (eg. ``"C:\Program Files\Git\bin\git.exe" clone ...``)

Now, clone the module's repository:

..  sourcecode:: bash

    $ cd /path/to/Erebot/vendor/
    $ git clone --recursive git://github.com/fpoirotte/<module>.git

..  note::
    Linux users (especially Erebot developers) may prefer to create a separate
    checkout for each component and then use symbolic links to join them
    together, like this:

    ..  sourcecode:: bash

        $ git clone --recursive git://github.com/fpoirotte/<module>.git
        $ cd Erebot/vendor/
        $ ln -s ../../<module>

Optionally, you can compile the translation files for each component.
However, this requires that `gettext`_ and `phing`_ be installed on your machine
as well. See the documentation on `Erebot's prerequisites`_ for additional
information on how to install these tools depending on your system.

Depending on the module, other additional tools may be required.
Check out this module's `prerequisites`_ for more information.

Once you got those two up and running, the translation files can be compiled
using these commands:

..  sourcecode:: bash

    $ cd /path/to/Erebot/vendor/
    $ phing


..  _`pear`:
    http://pear.php.net/package/PEAR
..  _`Pyrus`:
    http://pyrus.net/
..  _`Erebot's PEAR channel`:
    https://pear.erebot.net/
..  _`gettext`:
    http://www.gnu.org/s/gettext/
..  _`Phing`:
    http://www.phing.info/
..  _`Git for Windows`:
    http://code.google.com/p/msysgit/downloads/list
..  _`Erebot's prerequisites`:
    /Erebot/Prerequisites.html
..  _`prerequisites`:
    ../Prerequisites.html

.. vim: ts=4 et

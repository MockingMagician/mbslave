#################
Development Guide
#################

Development Setup
=================

Clone the repository and install the project using `poetry <https://python-poetry.org/>`__.
If you don't have poetry installed, you can install it using ``pipx install poetry`` or ``pip install poetry``.

::

    git clone https://github.com/acoustid/mbslave.git
    cd mbslave/
    poetry install

Poetry will automatically create a virtual environment for you. You can then run commands
within this environment using ``poetry run mbslave <command>`` or by activating the shell with ``poetry shell``.
For example, to see available commands:

::

    poetry run mbslave --help

Updating SQL files and models
=============================

Run these scripts to update SQL files::

    ./scripts/update_sql.sh

Release a new version
=====================

1. Change the version number in ``mbslave/__init__.py``.

2. Add notes to ``CHANGELOG.rst``

3. Tag the repository::

    git tag -s vX.Y.Z

4. Upload the package to PyPI::

    rm -rf dist/
    python setup.py sdist
    twine upload dist/mbslave-*.tar.gz

.. 

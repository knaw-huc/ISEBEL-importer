======================
ISEBEL Importer plugin
======================

ISEBEL importer plugin integrates importing scripts for ISEBEL. The scripts import ISEBEL
data from XML into CKAN


------------
Requirements
------------

Current version of CKAN is 2.9.0a


------------
Installation
------------


To install ckanext-isebelimporter (``pip install -r requirements.txt`` to install all the dependencies):

1. Activate your CKAN virtual environment, for example::

     source activate

2. Install the ckanext-isebelimporter Python package into your virtual environment::

     cp ckanext-isebelimporter ./

3. Add ``isebelimporter`` to the ``ckan.plugins`` setting in your CKAN
   config file (by default the config file is located at
   ``production.ini``).

4. Restart CKAN. Restart Apache or restart docker container::

     sudo service apache2 reload
     docker-compose restart ckan

---------------
Config Settings
---------------

No configurable options yet. Will be documented here when available


------------------------
Development Installation
------------------------

To install ckanext-isebelimporter for development, activate your CKAN virtualenv and
do::

    git clone https://github.com/knaw-huc/ckanext-isebelimporter.git
    cd ckanext-isebelimporter
    python setup.py develop
    pip install -r dev-requirements.txt


-----------------
Running the Tests
-----------------

To run the tests, do::

    nosetests --nologcapture --with-pylons=test.ini

To run the tests and produce a coverage report, first make sure you have
coverage installed in your virtualenv (``pip install coverage``) then run::

    nosetests --nologcapture --with-pylons=test.ini --with-coverage --cover-package=ckanext.isebelimporter --cover-inclusive --cover-erase --cover-tests


---------------------------------
Registering ckanext-isebelimporter on PyPI
---------------------------------

ckanext-isebelimporter should be availabe on PyPI as
https://pypi.python.org/pypi/ckanext-isebelimporter. If that link doesn't work, then
you can register the project on PyPI for the first time by following these
steps:

1. Create a source distribution of the project::

     python setup.py sdist

2. Register the project::

     python setup.py register

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the first release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.1 then do::

       git tag 0.0.1
       git push --tags


----------------------------------------
Releasing a New Version of ckanext-isebelimporter
----------------------------------------

ckanext-isebelimporter is availabe on PyPI as https://pypi.python.org/pypi/ckanext-isebelimporter.
To publish a new version to PyPI follow these steps:

1. Update the version number in the ``setup.py`` file.
   See `PEP 440 <http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers>`_
   for how to choose version numbers.

2. Create a source distribution of the new version::

     python setup.py sdist

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the new release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.2 then do::

       git tag 0.0.2
       git push --tags

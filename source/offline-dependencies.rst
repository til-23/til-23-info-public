Installing dependencies in an offline environment
=================================================

Should the need arise to install your python dependencies in an offline environment,
follow this tutorial to download your python dependencies into a thumbdrive,
and reinstall the libaries in a new virtual environment via the thumbdrive.

Saving your dependencies as wheel files
---------------------------------------

Assumptions:

- you are in an internet-enabled environment

**Download all pypi-indexed third-party python dependencies for your code**

.. code-block:: shell

    pip download -r path/to/requirements.txt -d /path/to/downloaded/packages  
    # download all third-party dependencies (wheel files) 
    # into a destination folder of your choice.

To generate a requirements.txt file, you can run ``pip freeze > requirements.txt``.
But note that if the til-23-finals package is already installed in ur venv, you will have to 
remove it from the requirements.txt file before you attempt the above ``pip download``. 
This is because til-23-finals package doesn't exist
in that internet repository - it comes from our custom challenge repo.


**(OPTIONAL) Make wheel file for the TIL2023 software development kit from the til-23-finals repo**

This step is optional as the during the Finals, the organizing team will provide a flash drive
(separate from the one loaned to finalists) from which students can install the til-23-finals package.

First, make sure, you have git pulled the til-23-finals repo and your current working directory 
is the til-23-finals repo root. Then run..

.. code-block:: shell

    python setup.py bdist_wheel --universal
    # This creates the wheel from the setup.py of the current python project.

**(OPTIONAL) Transfer til-23-finals wheel file to dest folder**

Copy-paste wheel file generated from prev step into target folder of python wheel files.

**Transfer your finalized folder of wheel files to a portable drive**

Copy-paste whole folder of downloaded packages (wheel files) into a portable drive, e.g. a flash drive.


Installing from offline packages 
--------------------------------

Now let's install into a *new* virtual environment from the dependency files stored in the portable drive.

Assumptions:

- You have activated a python virtual environment

**Install til-23-finals dependencies and your own model dependencies while offline**

.. code-block:: shell

    pip install --no-index --find-links="/path/to/downloaded/packages" -r requirements.txt

**Install til-23-finals software development kit while offline**

.. code-block:: shell

    pip install --no-index --find-links="/path/to/downloaded/packages" til-23-finals

**Test that the installation of the til-23-finals package is succesful by running these commands**

.. code-block:: shell

    til-scoring --help

.. code-block:: shell

    til-simulator --help

If the installation of the TIL softwares were successful, you should see the help messages of these commands.

You should now be able to run your autonomy code and AI models in the new virutal environment.
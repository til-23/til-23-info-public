Installing dependencies in an offline environment
=================================================

You will need to be able to install your python dependencies in an offline environment,
To do this, you will have to first download your dependencies into a portable format.
Follow this tutorial to download your python dependencies into a thumbdrive,
and reinstall the libaries in an offline virtual environment via the thumbdrive.

Saving your dependencies as wheel files
---------------------------------------

Assumptions:

First ensure you are in an internet-enabled environment.

**Download your third-party python dependencies from the PyPi package index**

Download wheel files into the flash drive.

.. code-block:: shell

    pip download -r path/to/requirements.txt -d /path/to/downloaded/packages  
    # Download all third-party dependencies (wheel files) 
    # into a destination folder of your choice.

To generate a requirements.txt file, you may run ``pip freeze > requirements.txt``.
But note that if the til-23-finals package is already installed in ur python virtual
environment, you will have to remove it from the requirements.txt file before you 
attempt the ``pip download``. This is because til-23-finals package doesn't exist
on the pypi index - it comes from our custom challenge github repo.

**Transfer your finalized folder of wheel files to a portable drive**

Copy-paste whole folder of downloaded packages (wheel files) into a portable drive, e.g. a flash drive.


**(OPTIONAL) Make wheel file for the TIL2023 software development kit from the til-23-finals repo**

This step is optional as the during the Finals, the organizing team will provide a flash drive
(separate from the one loaned to finalists) from which students can install the til-23-finals package.

First, make sure, you have git pulled the til-23-finals repo and your current working directory 
is the til-23-finals repo root. Then run..

.. code-block:: shell

    python setup.py bdist_wheel --universal
    # This creates the wheel from the setup.py of the current python project.

Next, copy-paste wheel file generated from prev step into a folder of ur choice (e.g.
in the flash drive)


Installing python packages from offline wheel files 
---------------------------------------------------

Now let's install into a *new* virtual environment from the dependency files stored in the portable drive.

Assumptions:

- You have activated a python virtual environment

**Install til-23-finals dependencies and your own model dependencies while offline**

.. code-block:: shell

    pip install --no-index --find-links="/path/to/downloaded/packages" -r requirements.txt
    # This ignores the pypi index and looks for wheels found in the directory pointed to by--find-links

**Install til-23-finals software development kit while offline**

.. code-block:: shell

    pip install --no-index --find-links="/path/to/downloaded/packages" til-23-finals
    # Install the til-23-finals package from a folder containing the corresponding wheel.

**Test that the installation of the til-23-finals package is succesful by running these commands**

.. code-block:: shell

    til-scoring --help

.. code-block:: shell

    til-simulator --help

If the installation of the TIL softwares were successful, you should see the help messages of these commands.

You should now test that you can run your autonomy code and AI models on the simulator, using this newly
installed Python virtual environment.

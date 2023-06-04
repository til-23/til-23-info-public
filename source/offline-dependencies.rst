Installing dependencies in an offline environment
=================================================

Should the need arise to install your python dependencies in an offline environment,
follow this tutorial to download your python dependencies in a transferrable format
and reinstall them in a new virtual environment.

Saving your dependencies into a transferrable format
----------------------------------------------------

Assumptions:

- You have git pulled the til-23-finals repo and your current working directory 
  is the til-23-finals repo root
- you are in an internet-enabled environment

**Download all pypi-indexed dependencies for your code**

.. code-block:: shell

    pip download -r path/to/requirements.txt -d /path/to/downloaded/packages  
    # download all third-party dependencies (wheel files) from the pypi index by default
    # into a destination folder of your choice.

**Make wheel file for the TIL2023 software development kit from the til-23-finals repo**

.. code-block:: shell

    python setup.py bdist_wheel --universal
    # creates the wheel from the setup.py of the current python project.

**Transfer til-23-finals wheel file to dest folder**

copy-paste wheel file generated from prev step into target folder of python wheel files.

**Transfer the folder of wheel files to a portable drive**

copy-paste folder of downloaded packages (wheel files) into a portable drive, e.g. a flash drive.


Installing from offline packages 
--------------------------------

Now let's install a *new* virtual environment from the dependency files stored in the portable drive.

Assumptions:

- You have activated a python virtual environment

**Install til-23-finals dependencies and your own model dependencies**

.. code-block:: shell

    pip install --no-index --find-links="/path/to/downloaded/packages" -r requirements.txt

**Install til-23-finals software development kit**

.. code-block:: shell

    pip install --no-index --find-links="/path/to/downloaded/packages" til-23-finals

**Test that the installation of the til-23-finals package is succesful by running these commands**

.. code-block:: shell

    til-scoring --help

.. code-block:: shell

    til-simulator --help

If the installation of the TIL softwares were successful, you should see the help messages of these commands.

You should now be able to run your autonomy code and AI models in the new virutal environment.
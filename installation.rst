Installation
==============

Use `Composer <https://getcomposer.org/download/>`_ to manage the dependencies of your project.

Inside your project folder
--------------------------
.. code-block:: text

    composer require fakerino/fakerino
    cd vendor/fakerino/fakerino
    build/ods

Like a stand-alone project 
--------------------------

.. code-block:: text

    composer create-project fakerino/fakerino fakerino

**NOTE**  
the last paramenter in the above command is the project folder and could be changed with a custom one, example:

``composer create-project fakerino/fakerino myFakerinoFolder``

Open Data Sample Project
^^^^^^^^^^^^^^^^^^^^^^^^

From the version 0.2.0 Fakerino integrates the `Open Data Sample Project <https://github.com/niklongstone/open-data-sample>`_, it means that when Fakerino it's installed the first time, automatically all the files from the ODS project will be installed.
If in future you want to update the ODS file (because there is some additions) you must run that command from the Fakerino project folder:  
``build/ods``
 
**NOTE**  
the command could overwrite files in the data/ folders

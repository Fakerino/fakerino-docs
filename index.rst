.. image:: _static/img/fakerino_logo.png 
   :align: left

Welcome to Fakerino's documentation!
==================================================
|
|
|
What is Fakerino?
----------------

Fakerino is a **fake data generator** that can generates :doc:`every kind of data </available-fake-data>`, from simple username and password to complex financial functions.

The usage of Fakerino is mainly oriented to facilitate testing operation, like fill forms, **database** population, **TDD**, **BDD**, system *mocks*, and much more.

The logical approach is very easy, Fakerino provides some basic data types (also in different languages) but allows the developer to extends its own custom types.

Fakerino can also fill with fake data a :doc:`database table </functionalities>`, a PHP :doc:`entity </functionalities>` object or render a custom template, it also support data generated by a :doc:`regular expression </functionalities>`.

It shows is real power combined with a :doc:`configuration </define-fake-data-groups>` (optional), it could return a particular aggregation type of data, for example can generate fake data to describe a ”Person”, a "Family", a "Response output", ...everything.

Project status
--------------
.. image:: https://poser.pugx.org/fakerino/fakerino/v/stable.svg
.. image:: https://travis-ci.org/niklongstone/Fakerino.svg?branch=master
.. image:: https://insight.sensiolabs.com/projects/4e7de12a-8fc4-4626-a33d-3287a20f02f6/mini.png
.. image:: https://codeclimate.com/github/niklongstone/Fakerino/badges/gpa.svg
.. image:: https://img.shields.io/scrutinizer/g/niklongstone/Fakerino.svg?style=flat-square



Contents:
---------
.. toctree::
   :maxdepth: 2

   installation
   quick-start
   available-fake-data
   functionalities
   define-fake-data-groups
   advanced-configuration
   command-line-tool
   outputs-format
   support
   contribute


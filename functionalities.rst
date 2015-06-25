Functionalities
===============

 - :ref:`loop` generates N number of fake data.
 - :ref:`fake-table` sets fake data inside a given Entity/Object.  
 - :ref:`fake-template` returns fake data inside a given template source.
 - :ref:`fake-entity` sets fake data inside a given Entity/Object.
 - :ref:`regular-expression` support
 - :ref:`seed` sets a fixed seed number for having on each call the same data.

.. _loop:

Loop
^^^^
The loop, allows to generate multiple fake data in one line of code.

.. code-block:: php 

    $fakerino->fake('Name')->num(100);

The num() method is also available for :doc:`complex fake data </advanced-configuration>` and fakeTable.

.. _fake-table:

Fake table
^^^^^^^^^^
The fakeTable method supports Mysql, Sqlite, PostgresSQL, Oracle, Microsoft SQL.  

.. code-block:: php 

    $fakerino->num(100)->fakeTable('tableName');

The database connection must be set trough configuration's values.  

.. code-block:: php 

    //mysql example
    $conf['database'] = array(
        'dbname' => 'mydb',
        'user' => 'user',
        'password' => 'secret',
        'host' => 'localhost',
        'driver' => 'pdo_mysql',
    );

    //sqlite example
    $conf['database'] = array(
        'path' => __DIR__ . '/mytable.sqlite',
        'driver' => 'pdo_sqlite'
    );

For further database configuration please read the `Doctrine Dbal configuration <http://doctrine-dbal.readthedocs.org/en/latest/reference/configuration.html>`_.

.. _fake-template:

Fake template
^^^^^^^^^^^^^
Providing a [Twig](http://twig.sensiolabs.org/) template, Fakerino can render the template with fake data inside.
the fakeTemplate method accept both file or string.

Inline template:

.. code-block:: php 

    //string
    $fakerino->fakeTemplate('Hello Mr {{ surname }}');
    //output: Hello Mr Brown
 
Loading external template file:

.. code-block:: php 

    //file.php
    $fakerino->fakeTemplate('template/path/response.xml');

.. code-block:: php 

    //response.xml
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <response>
      <person>
         <name>{{ namemale }}</name>
         <surname>{{ surname }}</surname>
      </person>
    </response>



.. _fake-entity:

Fake entity
^^^^^^^^^^^
The fake entity method, receive an Entity class in input and insert fake in every public properties and non public properties exposed by a public method setter.

.. code-block:: php 

    $myEntity = new MyEntity();
    $fakerino->fakeEntity($myEntity);

    //entity example
    class MyEntity
    {
        public $one;
        private $two;
        static public $four;

        public function setTwo($two)
        {
            $this->two = $two;
        }
    }

**Note** The pubblic setter name must start with 'set' (example: setMyVar)

.. _regular-expression:

Regular expression
^^^^^^^^^^^^^^^^^^
To fake a regular expression just call the fake method with the expression value.  

Example: ``$fakerino->fake('/\d{10}/');``

Ouput: 0483791034  

The regular expression could be used combined with configuration values.  
Example:

.. code-block:: php

    $arrayConfig = array('surname', 'threeCharText' => '/\w{3}/');
    $fakerino->fake($arrayConfig);
    //result:
    //Brown
    //abc 

.. _seed:

Seed
^^^^
If the seed is defined for each program run, you will receive the same fake data.


.. code-block:: php 

    $fakerino->seed(123);
    $fakerino->fake('surname');


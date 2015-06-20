Define fake data groups
=======================

Introduction
^^^^^^^^^^^^

With a configuration file you could use all the power of Fakerino and fake more complex object in one shot instead of call several times the same functions.

The default configuration tag (could be modified in the :doc:`Advanced configuration </advanced-configuration>`) Fakerino uses to recognize a custom fake element is:
    
    `fake`  
This implies that: 
 - Every complex elements has to be under the main **fake** configuration tag
 - Each element's name must start with the **fake** tag name (ex: fake1, fake2, ..)


Below an example of configuration in Php:

Php configuration example
^^^^^^^^^^^^^^^^^^^^^^^^^
.. code-block:: php

    //conf.php
    <?php
    $conf['fake'] = array(
        'fake1' => array(
            'NameMale',
            'Surname'
        ),
        'fake2' => array(
            'NameFemale',
            'Surname'
        )
    );

The configuration file can be injected with:

.. code-block:: php

    $fakerino = Fakerino::create('filepath/conf.php');

Using the above configuration you could fake the whole fake1 structure or only the second one as below.

.. code-block:: php

    echo $fakerino->fake('fake1');
    echo $fakerino->fake('fake2');

You could also continue to use the basic fake calls everytime (`$fakerino->fake('Name');`).

Examples of supported configurations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Yaml
~~~~
.. code-block:: text


    fake:
      fakeMale:
       - titlemale
       - surname

Xml
~~~
.. code-block:: text

    <?xml version="1.0"?>
    <fake>
        <fake1>
            <NameFemale/>
            <Surname/>
        </fake1>
    </fake>

Ini
~~~
.. code-block:: text

    [fake]
    fake1[]=NameFemale
    fake1[]=Surname

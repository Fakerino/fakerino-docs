Define fake data groups
=======================

With a configuration file you could use all the power of Fakerino and fake more complex object in one shot instead of call several times the same functions.

The default configuration tag (could be modified see [Advance configuration](https://github.com/niklongstone/Fakerino/wiki/Advance-configuration)) that Fakerino uses for recognize an element is:
    
    fake  
this means that for configure multiple element:
 - every complex elements has to be under the main **fake** tag
 - each element's name must start with the **fake** tag name (ex: fake1, fake2, ..)


below an example of configuration in Php:
#####Php configuration example
```PHP
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
```
The configuration file can be injected with:  
```PHP
$fakerino = Fakerino::create('filepath/conf.php');
```  
With the above configuration you could fake the whole fake1 structure or the second one in a very easy way.
```PHP
    echo $fakerino->fake('fake1');
    echo $fakerino->fake('fake2');
```
You could also continue to use the basic fake calls everytime (`$fakerino->fake('Name');`).

####Examples of supported configurations.
#####Yaml configuration
```YMl
fake:
  fakeMale:
   - titlemale
   - surname
```
#####Xml configuration
```XML
<?xml version="1.0"?>
<fake>
    <fake1>
        <NameFemale/>
        <Surname/>
    </fake1>
</fake>
```
#####Ini configuration
```Ini
[fake]
fake1[]=NameFemale
fake1[]=Surname
```

Advanced Configuration
======================

The default Fakerino configuration parameters are the follows:

    fakerinoTag = fake
    locale = en-GB 
    fakeFilePath = /data          

**fakerinoTag** is used to identify complex object to fake inside the configuration.  
If you want to change the **fakeFilePath**, it must point to your custom fake files folder directory as follow:
`/path/of/your/folder/`
your directory must contain one or more locale directory on it
`/path/of/your/folder/en-GB`  
If the path is not correct Fakerino simply will return a random string instead of throwing an error.

It's possible to override every parameters using a configuration file. 
######Example of custom configuration
```PHP
//conf.php
<?php
$conf['locale'] = "en-US";
$conf['fakerinoTag'] = "mycustom";
$conf['fakeFilePath'] = "/your/file/path";  
/* fakeFilePath is without slash at the end 
   and must contain at least the en-Us folder on it /your/file/path/en-US */

$conf['mycustom'] = array(
'mycustom-one' => array(
    'FemaleName'
    'Surname'
),
'mycustom-two' => array(
    'MaleName'
    'Surname'
));


Quick start
===========

1. Load the Fakerino class
2. Create a Fakerino instance (only once)
3. Fake the data

```PHP    
require('../Fakerino/vendor/autoload.php'); //path to the Fakerino folder
use Fakerino/Fakerino
$fakerino = Fakerino::create();
echo $falerino->fake('NameMale');
```

To fake more than one data in same time, an array must be passed to the fake method.
```PHP   
echo $falerino->fake(array('NameMale', 'Surname'));
```

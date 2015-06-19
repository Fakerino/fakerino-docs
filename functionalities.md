Functionalities
===============

 - **[Loop](#loop)** generates N number of fake data.
 - **[Fake table](#fake-table)** sets fake data inside a given Entity/Object.  
 - **[Fake template](#fake-template)** returns fake data inside a given template source.
 - **[Fake entity](#fake-entity)** sets fake data inside a given Entity/Object.
 - **[Regular expression](#regular-expression)** support
 - **[Seed](#seed)** set a fixed seed number for having on each call the same data.

Loop
^^^^
The loop, allows to generate multiple fake data in one row of code.

    $fakerino->fake('Name')->num(100);

The num() method is also available for [complex fake data](https://github.com/niklongstone/Fakerino/wiki/Advance-Configuration) and fakeTable.

Fake table
^^^^^^^^^^
The fakeTable method supports Mysql, Sqlite, PostgresSQL, Oracle, Microsoft SQL.  
```PHP $fakerino->num(100)->fakeTable('tableName');```  

The database connection must be set trough configuration's values.
```PHP
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
```
for further database configuration please read the [Doctrine Dbal configuration](http://doctrine-dbal.readthedocs.org/en/latest/reference/configuration.html).

### Fake template
Providing a [Twig](http://twig.sensiolabs.org/) template, Fakerino can render the template with fake data inside.
the fakeTemplate method accept both file or string.
Examples:

```PHP
//file
$fakerino->fakeTemplate('template/path/response.xml');
```  
```XML
//response.xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<response>
  <person>
     <name>{{ namemale }}</name>
     <surname>{{ surname }}</surname>
  </person>
</response>
```
```PHP 
//string
$fakerino->fakeTemplate('Hello Mr {{ surname }}');
//output: Hello Mr Brown
```  

Fake entity
^^^^^^^^^^^
The fake entity method, receive an Entity class in input and insert fake in every public properties and non public properties exposed by a public method setter.
```PHP
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
```
*Note* The pubblic setter name must start with 'set' (example: setMyVar)

### Regular expression
To fake a regular expression just call the fake method with the expression value.  
Example:`$fakerino->fake('/\d{10}/');`  
Ouput: 0483791034  

The regular expression could be used combined with configuration values.  
Example:   
```PHP
$arrayConfig = array('surname', 'threeCharText' => '/\w{3}/');
$fakerino->fake($arrayConfig);
//result:
//Brown
//abc 
```
 
Seed
^^^^
If the seed is defined in each program run, you will receive the same fake data.
```PHP
$fakerino->seed(123);
$fakerino->fake('surname');
```



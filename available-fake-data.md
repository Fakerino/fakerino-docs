Available Fake Data
===================

- **[Framework core data](#framework-core-data):** text, integer, date.
- **[ODS based](#ods-data):** name, surname, country, postcode, and more in several languages.
- **[Custom regex](#ods-data):** custom data, from regular expression support.

Generating fake data is really easy, you can just call the Fakerino fake method with the desired type:
```PHP 
$fakerino->fake('nameFemale');
```
**NOTE** The name inside the fake method is NOT case sensitive.

Below a list of the current supported fake data.

##Framework core data
 * Text,  
  options:  
  * length (default:[3-20])
  * addChar (used to add new chars to the default ones 0123456789abcdefghijklmnopqrstuvwxyz)
 * Integer,   
  options:  
  * length (default: [1-5]),  
  * negative: true|false (default:false),  
  * type: decimal, hex, octal, binary (default: decimal)
 * Date,   
  options:  
  * format: es Y-m-d
  * startDate: 2015-01-01 (will fake a date into the startDate - now range)
  * endDate: 2016-01-01 (in combination with startDate could fake date into range startDate endDate)
 

ODS data
--------

Fakerino, from version 0.2.0 integrates the [Open Data Sample Project](https://github.com/niklongstone/open-data-sample), you can access to all the ODS data by simply call the filename.

for more information see the [List of available fake files] (https://github.com/niklongstone/open-data-sample/tree/master/data)

If you need more data, you can add it without any particular programming skill, the ODS data files are a simple text files separated by new line.

##Regular expression
With the regular expression support is possible to fake every kind of custom data, additional information on [functionalities section](https://github.com/niklongstone/Fakerino/wiki/Functionalities#regular-expression)

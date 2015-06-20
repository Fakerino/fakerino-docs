Command line tool
=================

From the 0.3.0 Fakerino includes a command line tools.

.. code-block:: text

    Usage:
     app/fake <fake data name> [-j] [-n <integer>] [-c <config file path>]

    Options:
     -j                 Returns JSON format (default string)
     -n <num>           Returns <num> times the result
     -l                 Changes the locale settings (default en-GB)
     -c <conf>          Uses the <conf> file for generating data (override the locale -l if set)
     -t <table>         Fills fake data in the specified <table> (requires a config file)
     -s <file|string>   Returns a fake data from specified <file> or <string> template source
     -h                 Displays this help

Examples:

.. code-block:: text

    app/fake -h //for help
    app/fake namemale surname //Travis Baldwin
    app/fake surname -j //["Brooks"]
    app/fake nameMale -n 2 //Nick Andy
    app/fake country -c path/config.ini //uses a config file
    app/fake surname -l de-DE //Schleßinger   
    app/fake -t tableName -c  path/config.xml  
    app/fake -s 'Hello Mrs {{namefemale}} {{surname}}' -l de-DE //Hello Mrs Seeliger Ceylin

# Basic Python Revision Notes

# Logging 

6 logging level (Highest to Lowest) -> CRITICAL , ERROR , WARNING (Default) , INFO , DEBUG , NOTSET 

Root Logger (default) 
```
import logging
logging.basicConfig(filename='log.txt',level=logging.WARNING)
logging.warning('Warning information')
logging.error('Error information')
```
Customized Logger - Can be setup using module 'logging' and method 'getLogger'

_terms - logger , logger object , log level , handler_ 

# Inner Classes

Without existing one type of object if there is no chance of existing another type of object, then we should go for inner classes.
You can have multiple inner class / nested class in python. 

Example : Without having proper connection to database , you cannot try to run the fetch query to extract data.

# Composition (Has-A relationship)

Access member of one class inside another class by using class name or by creatiing object
When we don't want to extents parent class functionality but child class just want to use those , then we go for Has-A relationship

# Inheritance (Is-A relationship)
Access member of one class inside another class by using class name or by creatiing object
When we want to extents parent class functionality in child class then we go for Is-A relationship

# Composition vs Aggregation
Composition - Strong association between object.  2nd object cannot exists without 1st object. University -> Department relationship.

Aggregation - Week association between object. 2nd object can exists without 1st object. Department -> Professor relationship.


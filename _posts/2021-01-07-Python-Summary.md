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

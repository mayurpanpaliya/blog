# Python Logging 
6 logging level (Highest to Lowest) -> CRITICAL , ERROR , WARNING (Dafault) , INFO , DEBUG , NOTSET 
```
import logging
logging.basicConfig(filename='log.txt',level=logging.WARNING)
logging.warning('Warning information')
logging.error('Error information')
```

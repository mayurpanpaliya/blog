# Python Generators
- Generator is a function that returns an object (iterator) which we can iterate over (one value at a time). 
- Iterate through the items using next() or for loop . 
- Use case : To generate a seqence of value.
- Keyword  : yield 
- yield vs return keyword : The difference is that while a return statement terminates a function entirely, yield statement pauses the function saving all its states and later continues from there on successive calls.

##  Generators Function
``` 
def countdown(num):
  print("Start Countdown")
  while(num>0):
    yield num
    num=num-1 
```  
## Check type
```
type(countdown(10)) ==> generator
```

## Calling next element using next()
```
next_obj = countdown(10)
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
print(next(next_obj))
```
Output :
```
Start Countdown
10
9
8
7
6
5
4
3
2
1
```

## Calling next element using loop 
```
loop_obj = countdown(10)
for i in loop_obj:
  print(i)
```
Output :
```
Start Countdown
10
9
8
7
6
5
4
3
2
1
```


## Practical use-case of generator in project : 
Problem statement : Client decided to decommission user-manged database and move those to service-managed mode for better governance and compliance.
Task assigned to developer to identify list of database , view used in all scripts along with it's count. 

Dummy data :
Database and base view name : e_abc_area_db , stg_abc_area_db , core_xyz_area_base.

Use in script : E_abc_Area_db.table1 ,  e_abc_area_db.table2 etc 


- Approach 1 : Manually open each file and list down details. 
- Approach 2 : Write unix shell script to gather this information
- Approach 3 : Write python script to gather this information


## Python sample code to gather information using generator

```
# import lib
import re , glob

# lazy iterator for file data
def read_in_chunks(file_object , chunk_size=1024):
  """
  Lazy function (generator) to read a file piece by piece. Default chunk size 1k 
  """
  
  while True:
    data = file_object.read(chunk_size)
    if not data:
      break
     yield data
  
# Actual data logic
def process_data(data):
  data_list = re.findall(r'\w+(?:db|view|base)[.]',data,flags=re.IGNORECASE)
  for val in data_list:
    master_dict[val] = master_dict.get(val,0) + 1
  
# File Pattern
files = glob.glob("/home/username/scripts/*.py")

#Initialize dict
master_dict = {}

for file in files:
  with open(file) as f:
    for piece in read_in_chunks(f):
      process_data(piece)
  
#Output dict
print(master_dict)

# Dummy output. Using appropriate regex pattern , required information can be generated.  
{'e_abc_area_db.':105 , 'stg_abc_area_db.':1 , 'core_xyz_area_base.':6}

```




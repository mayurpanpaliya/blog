# Difference between in Python

## List and Array 
```
List : collection of items , heterogeneous data types . Insertion order preserved . Mutable . Duplicates allowed. Indexing possible.
- l = [10,20]
- list(range(0,10,2))
```
Array : An array is a vector containing homogeneous elements i.e. belonging to the same data type. Elements are allocated with contiguous memory locations.
```
import array 
  
sample_array = array.array('i', [1, 2, 3])   
  
# accessing elements of array 
for i in sample_array: 
     print(i)
     
output:
1
2
3

```

Reference: 
https://www.geeksforgeeks.org/difference-between-list-and-array-in-python/

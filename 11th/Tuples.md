
# Tuples

*   We saw that lists and strings have many common properties, such as indexing and slicing operations. There is also another standard sequence data type: the tuple.
*   A tuple consists of a number of values separated by commas, for instance:




```python
t = 12345, 54321, 'hello!'
print( t[0])
print( t)

# Tuples may be nested
u = t, (1, 2, 3, 4, 5)
print(u)

# Tuples can contain mutable objects:
v = ([1, 2, 3], [3, 2, 1])
v[0][2] = 5
print(v)

# Tuples are immutable:
t[0] = 88888 #throws an error
```

    12345
    (12345, 54321, 'hello!')
    ((12345, 54321, 'hello!'), (1, 2, 3, 4, 5))
    ([1, 2, 5], [3, 2, 1])



    

    TypeErrorTraceback (most recent call last)

    <ipython-input-5-610e7c5d7e14> in <module>()
         13 
         14 # Tuples are immutable:
    ---> 15 t[0] = 88888
    

    TypeError: 'tuple' object does not support item assignment


A special problem is the construction of tuples containing 0 or 1 items: the syntax has some extra quirks to accommodate these. Empty tuples are constructed by an empty pair of parentheses; a tuple with one item is constructed by following a value with a comma (it is not sufficient to enclose a single value in parentheses). For example:


```python
emptyTuple = ()
singletonTuple = 'hello',    # <-- note trailing comma

print (len(emptyTuple))
print (len(singletonTuple))
```

    0
    1


## Addding Elements to a Tuple
We can add new element to tuple using + operator.


```python
t = (10, 20 ,30, 40)
print (t + (60, ) )
# Addding a tuple with a single element to the existing tuple t won't change the value of tuple t

# To modify t we need to assign the tuple returned above to t
# This can be done as follows
t = t + (60, )
print( t)
```

    (10, 20, 30, 40, 60)
    (10, 20, 30, 40, 60)


## Tuple Assignment
If we want to interchange (swap) any two variable values, we have to use temporary variable. For example:


```python
a = 10
b = 20

print( 'Before Swapping: ', a, b)

# Swapping using a temporary variable
temp = a
a = b
b = temp

print( 'After Swapping: ', a, b)
```

    Before Swapping:  10 20
    After Swapping:  20 10


But in python, tuple assignment is more elegant:


```python
tuple1 = (10, 20, 30)
tuple2 = (100, 200, 300, 400)

print( 'Before Swapping: ', tuple1, tuple2)

# Swapping using tuple assignment
tuple1, tuple2 = tuple2, tuple1

print( 'After Swapping: ', tuple1, tuple2)
```

    Before Swapping:  (10, 20, 30) (100, 200, 300, 400)
    After Swapping:  (100, 200, 300, 400) (10, 20, 30)


## Slicing

*   Slicing in tuple is similar to list or string slicing
*   Syntax of tuple slicing is `tuple[start : stop : steps]`.
*   which means that slicing will start from index **start** will go up to **stop** in **step** of steps.
*   Default value of start is 0, stop is last index of list and for step it is 1.




```python
# Let us first create a tuple to demonstrate slicing 
# tuple contains all number from 1 to 10 
tuple0 = tuple(range(1, 11))
print( tuple0)

#  below tuple has numbers from 2 to 5 
tuple1_5 = tuple0[1 : 5] 
print (tuple1_5 )
  
#  below tuple has numbers from 6 to 8 
tuple5_8 = tuple0[5 : 8] 
print (tuple5_8) 
  
#  below tuple has numbers from 2 to 10 
tuple1_ = tuple0[1 : ] 
print (tuple1_) 
  
#  below tuple has numbers from 1 to 5 
tuple_5 = tuple0[: 5] 
print (tuple_5) 
  
#  below tuple has numbers from 2 to 8 in step 2 
tuple1_8_2 = tuple0[1 : 8 : 2] 
print (tuple1_8_2) 
  
#  below tuple has numbers from 10 to 1 
tuple_rev = tuple0[ : : -1] 
print (tuple_rev) 
  
#  below tuple has numbers from 10 to 6 in step 2 
tuple_rev_9_5_2 = tuple0[9 : 4 : -2] 
print (tuple_rev_9_5_2)
```

    (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
    (2, 3, 4, 5)
    (6, 7, 8)
    (2, 3, 4, 5, 6, 7, 8, 9, 10)
    (1, 2, 3, 4, 5)
    (2, 4, 6, 8)
    (10, 9, 8, 7, 6, 5, 4, 3, 2, 1)
    (10, 8, 6)


## Other Tuple Methods
### cmp(x, y)
Compare the two objects x and y and return an integer according to the outcome. The return value is negative if `x < y`, zero if `x == y` and strictly positive if `x > y`.


```python
myTuple1 = (100, 200, 300)
myTuple2 = (100, 200, 300)
myTuple3 = (1, 2)

print (cmp(myTuple1, myTuple3)) # both are not equal
print (cmp(myTuple1, myTuple2)) # both are equal
print (cmp(myTuple3, myTuple1))
```

    1
    0
    -1


### len(s)
 This method returns number of elements in the given tuple.


```python
myTuple = (100, 200, 300, 400)

print( len(myTuple))
```

    4


### max(iterable)
It returns its largest item in the tuple.


```python
myTuple = (100, 200, 300, 400, 500)

print (max(myTuple))
```

    500


### min(iterable)
It returns its least item in the tuple.


```python
myTuple = (100, 200, 300, 400, 500)

print (min(myTuple))
```

    100



```python

```

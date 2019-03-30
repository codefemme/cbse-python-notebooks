
# Generators
A generator is a function that returns an object (iterator) which we can iterate over (one value at a time).

### Creating a Generator
It is fairly simple to create a generator in Python. It is as easy as defining a normal function with ***`yield`*** statement instead of a ***`return`*** statement.

If a function contains at least one ***`yield`*** statement (it may contain other ***`yield`*** or ***`return`*** statements), it becomes a generator function. Both ***`yield`*** and ***`return`*** will return some value from a function.

The difference is that, while a ***`return`*** statement terminates a function entirely, ***`yield`*** statement pauses the function saving all its states and later continues from there on successive calls.

Let us now see a few examples of generator functions:


```python
# A simple generator function
def myGen():
    n = 1
    print('This is printed first')
    # Generator function contains yield statements
    yield n

    n += 1
    print('This is printed second')
    yield n

    n += 1
    print('This is printed at last')
    yield n

# Using for loop
for item in myGen():
    print(item)  
```

    This is printed first
    1
    This is printed second
    2
    This is printed at last
    3



```python
def revStr(myStr): 
    for i in range(len(myStr) - 1,-1,-1):
        yield myStr[i]

# For loop to reverse the string
for char in revStr("hello"):
     print(char)
```

    o
    l
    l
    e
    h



```python
def fibonacciGen(n):
  a = 0
  b = 1
  while a <= n:
    yield a
    a, b = b, a + b

for i in fibonacciGen(100):
  print i,
```

    0 1 1 2 3 5 8 13 21 34 55 89


The generator can also be used to return a list of values


```python
lst = list(fibonacciGen(100))
print lst
```

    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]


### Advantages of using generator
*   These functions are better w.r.t. memory utilization and code performance, as they allow function to
avoid doing all work at a time.
*   They provide a way to manually save the state between iterations. As the variables in function scope
are saved and restored automatically.


```python

```

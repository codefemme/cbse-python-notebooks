
# Chapter 2 : Functions

A function is named sequence of statement(s) that performs a computation. It contains line of code(s) that are executed sequentially from top to bottom by Python interpreter. 

They are the most important building block for any software in Python. They are of 3 types :

* **Modules** : A module is a file containing Python definitions (i.e. functions) and statements. Standard library of Python is extended as module(s) to a Programmer.


* **User Defined** : In Python, it is also possible for programmer to write their own function(s). These functions can then be combined to form module which can be used in other programs by importing them. To define a function, keyword 'def' is used. After the keyword comes an identifier i.e. name of the function, followed by parenthesized list of parameters and the colon which ends up the line, followed by the block of statement(s) that are the part of function.

* **Built In** : Built in functions are the function(s) that are built into Python and can be accessed by Programmer. These are always available and for using them, we don't have to import any module (file).

## 2.1 Modules
A module is a file containing Python definitions (i.e. functions) and statements.
Standard library of Python is extended as module(s) to a programmer. Definitions from
the module can be used within the code of a program.

To use these modules in the program, a programmer needs to import the module. Once you import a module, you
can reference (use), any of its functions or variables in your code. There are many ways
to import a module in your program, the one‟s which you should know are:

**i. import**

**ii. from**

### import

**import** is the simplest and most common way to use modules in your code.

#### **Syntax :  import module1, module2...  ** 


```python
import math
```

To use/ access/invoke a function, you will specify the module name and name of the function- separated by dot (.).  This format is also known as **dot notation.**


```python
value = math.sqrt(25)
print(value)
```

    5.0


The above code invokes the sqrt (Square root) function from the module **math** to calculate the square root of the number inserted in the parantheses.


```python
power= math.pow(2,3)
print(power)
```

    8.0


The above code invokes the pow function from the math module, and calculates 2 to the power of 3.

### from statement

It is used to get a specific function in the code instead of the complete module file. If we know beforehand which function(s), we will be needing, then we may use **from**. 

#### Syntax: from module_name import function_name


```python
from math import pow,sqrt
```


```python
from pandas import Series
```

### Math module

We've seen sqrt, and pow functions from the module math previously. Lets look into more functions available in this module.



```python
#ceil(x)

#It returns the greatest value not greater than x, where x is a numeric expression.

print(math.ceil(45.44))

print(math.ceil(76.1))
```

    46
    77



```python
#floor(x)

#It returns the smallest value not smaller than x, where x is a numeric expression.

print(math.floor(45.44))

print(math.floor(76.1))


```

    45
    76



```python
# fabs(x)

#It returns the absolute value for x , where x is a numeric value.

print(math.fabs(-45.44))

print(math.fabs(-76.1))


```

    45.44
    76.1



```python
# exp(x)

#It returns the exponential of x: e^x,  where x is a numeric expression.

print(math.exp(45.44))

print(math.exp(76.1))


```

    5.424269484438863e+19
    1.1215278765953436e+33



```python
# log(x) 

#It returns the logarithmic value of x, for x>0 where x is a numeric expression.

print(math.log(45.44))
print(math.log(2))


```

    3.816392774412896
    0.6931471805599453



```python
#log10(x)

#It returns base-10 logarithm of x, for x>0 where x is a numeric expression.

print(math.log10(45.44))
print(math.log10(76.1))



```

    1.6574383227029625
    1.8813846567705728



```python
#pow(x,y)

#It returns the value of x^y, where x and y are numeric expressions.

print(math.pow(100,2))

print(math.pow(100,-2))

print(math.pow(11,0))



```

    10000.0
    0.0001
    1.0



```python
# sqrt(x)

#It returns the square root of x, for x>0, where x is a numeric expression.

print(math.sqrt(100))

print(math.sqrt(2))



```

    10.0
    1.4142135623730951



```python
#cos(x)

#It returns the cosine of x in radians for x>0 where x is a numeric expression.

print(math.cos(0))

print(math.cos(math.pi))



```

    1.0
    -1.0



```python
#sin(x)

#It returns the sine of x in radians for x>0 where x is a numeric expression.

print(math.sin(0))

print(math.sin(90))



```

    0.0
    0.8939966636005579



```python
# tan(x)

#It returns the tangent of x in radians, where x must be a numeric value.

print(math.tan(0))

print(math.tan(3))


```

    0.0
    -0.1425465430742778



```python
#radians(x)

#It converts angle x from degrees to radians, where x must be a numerical value.

print(math.radians(90))

print(math.radians(60))


```

    1.5707963267948966
    1.0471975511965976


## 2.2 Built-in Functions

The Python interpreter has a number of functions that are always available for use. These functions are called built-in functions. For example, print() function prints the given object to the standard output device (screen) or to the text stream file.  These are always available and for using them, we don‟t have to import
any module (file).




```python
# abs(x)

#Returns distance between 0 and x, i.e the absolute value of x where x is a numeric expression.

print(abs(-45))

print(abs(119L))


```

    45
    119



```python
# max(x,y,z....)

#It returns the largest of its arguments: where x,y and z are numeric variable/expression.

print(max(70,10,500))

print(max(-80, -20 , -100))


```

    500
    -20



```python
# min(x,y,z..)

#It returns the smallest of its arguments: where x,y and z are numeric variable/expression.

print(min(70,10,500))

print(min(-80, -20 , -100))


```

    10
    -100



```python
#divmod(x,y)

#Returns both quotient and remainder by division via a tuple, when x is divided by y.

print(divmod(14,5))

print(divmod(27,3))


```

    (2, 4)
    (9, 0)



```python
#len(s)

#Returns the length of the number of items present in an object.

a=[1,2,3]

print(len(a))



```

    3



```python
#range(start, stop, step)

#This is used to define the arithmetic progressiob in creating lists. Used most often in for loops.

#if start parameter isn't defined then it is default at 0.

#the step parameter is used to define how many 
#if step parameter isn't defined then by default it traverses by +1 . its value cannot be 0.

#the range value executes from start value till (stop value minus 1)
print(range(3, 10))

print(range(10))

print(range(0,30,5))

print(range(0, -10))

print(range(0, -10, -1))
```

    range(3, 10)
    range(0, 10)
    range(0, 30, 5)
    range(0, -10)
    range(0, -10, -1)



```python
# round(x, n)

#rounds x to the nearest n digits from the decimal point. 

#if n is not provided then it is rounded to 0 decimal digits.

print(round(84.389150, 2))

print(round(9.941616))
```

    84.39
    10


## 2.3 Composition

Composition is an art of combining simple function(s) to build more complicated ones,
i.e., result of one function is used as the input to another.


```python
import math

value= math.cos(math.pi)
print(value)
```

    -1.0


## 2.4 User Defined Functions

So far we have only seen the functions which come with Python either in some file
(module) or in interpreter itself (built in), but it is also possible for programmer to write
their own function(s).

To define a function keyword def is used. After the keyword comes an identifier i.e.
name of the function, followed by parenthesized list of parameters and the colon which
ends up the line. Next follows the block of statement(s) that are the part of function

### Function definition



```python
def function_name(): #Function header
  #Function body
  print("Hello World")
```

### Calling a function

To call a function, use the function name followed by parenthesis:


```python
def function_name():
  
  print("Hello World")
  
function_name()
```

    Hello World


### Docstring

DocString is an important tool to document the program better, and makes it easier to
understand. We can actually access docstring of a function using ______doc__  (function
name). Also, when you used help(), then Python will provide you with docstring of that
function on screen. So it is strongly recommended to use docstring when you write
functions.


```python
def my_function():
    """Do nothing, but document it.

    No, really, it doesn't do anything.
    """
    pass

print (my_function.__doc__)
```

    Do nothing, but document it.
    
        No, really, it doesn't do anything.
        


### Parameters and Arguments

Information can be passed to functions as parameter.

Parameters are specified after the function name, inside the parentheses. You can add as many parameters as you want, just separate them with a comma.

Arguments are the value(s) provided in function call/invoke statement. List of
arguments should be supplied in same way as parameters are listed




```python
def my_function(name):
  print(name + " Hemsworth")

my_function("Liam")
my_function("Chris")

```

    Liam Hemsworth
    Chris Hemsworth



```python
def area_rectangle(length, breadth):
  area= length* breadth
  print("The area of the rectangle is " + str(area)) #why str(area)?

  
area_rectangle(5,6)

area_rectangle(7,9)

```

    The area of the rectangle is 30
    The area of the rectangle is 63


**Default Parameter Value**

The following example shows how to use a default parameter value.

If we call the function without parameter, it uses the default value:


```python
def my_function(country = "Norway"):
  print("I am from " + country)

my_function("Sweden")
my_function("India")
my_function()
my_function("Brazil")
```

    I am from Sweden
    I am from India
    I am from Norway
    I am from Brazil



```python
def greet(message, times=1):
  print(message* times)

greet("welcome")
greet("hello ", 2)
```

    welcome
    hello hello 


**Return Values**

We use the **return** statement to return values from a function.


```python
def my_function(x):
  return 5 * x

print(my_function(3))
print(my_function(5))
print(my_function(9))
```

    15
    25
    45


**Note:**
* The default value assigned to the parameter should be a constant only.
* Only those parameters which are at the end of the list can be given default value.
You cannot have a parameter on left with default argument value, without
assigning default values to parameters lying on its right side.
* The default value is evaluated only once, at the point of function definition

#### print() vs return : What's the difference?

Same as C++,  The "print" command outputs text directly to the screen, while the "return" command outputs the values back to whatever is calling the function.


```python
def example():
    print (1+1)

example() # this will output the number 2 to the screen
```

    2



```python
def example():
    return 1+1

x = example() # this will store the number 2 in the variable called x
```


```python

```

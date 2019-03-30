
# Chapter 2 - Concept of Object Oriented Programming
Object oriented programming – As the name suggests uses objects in programming. Object oriented programming aims to implement real world entities like inheritance, hiding, polymorphism etc in programming. The main aim of OOP is to bind together the data and the functions that operates on them so that no other part of code can access this data except that function.

 Let us learn about different characteristics of an Object Oriented Programming language:
1. Objects
2. Classes
3. Encapsulation
4. Abstraction
5. Polymorphism
6. Inheritance


## Object 
*   Object is an entity that has state and behavior. It may be anything. It may be physical and logical. For example: mouse, keyboard, chair, table, pen etc.
*   Everything in Python is an object, and almost everything has attributes and methods. All functions have a built-in attribute **`__doc__`** , which returns the doc string defined in the function source code.

## Class
Class can be defined as a collection of objects. It is a logical entity that has some specific attributes and methods. For example: if you have an employee class then it should contain an attribute and method i.e. an email id, name, age, salary etc.


```python
# Syntax
class className:
  <statement-1>
  .
  .
  .
  .
  .
  <statement-n>
```

## Namespace

In Python, the namespace is a fundamental idea to structure and organize the code, especially more useful in large projects.

Before getting on to namespaces, first, let’s understand what Python means by a name.



A name in Python is just a way to access a variable like in any other languages. However, Python is more flexible when it comes to the variable declaration. You can declare a variable by just assigning a name to it.

You can use names to reference values.

We can get the address (in RAM) of some object through the built-in function, id()


```python
num = 5
str = 'Z'
seq = [0, 1, 1, 2, 3, 5]
```


```python
def function():
 print('It is a function.')
 
foo = function
foo()
```

    It is a function.


You can also assign a name and then reuse it. Check the below example; it is alright for a name to point to different values.


```python
a = 2

# Output: id(a) = 10919424
print('id(a) =', id(a))

a = a+1

# Output: id(a) = 10919456
print('id(a) =', id(a))

# Output: id(3) = 10919456
print('id(3) =', id(3))

b = 2

# Output: id(2)= 10919424
print('id(2) =', id(2))
```

    id(a) = 140280961193216
    id(a) = 140280961193248
    id(3) = 140280961193248
    id(2) = 140280961193216




![alt text](https://cdn.programiz.com/sites/tutorial2program/files/aEquals2.jpg)



**A namespace is a simple system to control the names in a program** . It ensures that names are unique and won’t lead to any conflict.

Also, add to your knowledge that Python implements namespaces in the form of dictionaries. It maintains a name-to-object mapping where names act as keys and the objects as values. Multiple namespaces may have the same name but pointing to a different variable.

There are different tyes of namespaces: 

* Local namespace
* Global namespace
* Built-In namespaces 



**Local Namespace**

This namespace covers the local names inside a function. Python creates this namespace for every function called in a program. It remains active until the function returns.


**Global Namespace**

This namespace covers the names from various imported modules used in a project. Python creates this namespace for every module included in your program. It’ll last until the program ends.


**Built-in Namespace**

This namespace covers the built-in functions and built-in exception names. Python creates it as the interpreter starts and keeps it until you exit.

## Scope in Functions

Namespaces make our programs immune from name conflicts. However, it doesn’t give us a free ride to use a variable name anywhere we want. Python restricts names to be bound by specific rules known as a scope. The scope determines the parts of the program where you could use that name without any prefix

Scope is the portion of the program from where a namespace can be accessed directly without any prefix.

At any given moment, there are at least three nested scopes.

* Scope of the current function which has local names
* Scope of the module which has global names
* Outermost scope which has built-in names


```python
def outer_function():
    b = 20
    def inner_func():
        c = 30

a = 10
```

Here, the variable a is in the global namespace. Variable b is in the local namespace of outer_function() and c is in the nested local namespace of inner_function().

When we are in inner_function(), c is local to us, b is nonlocal and a is global. We can read as well as assign new values to c but can only read b and a from inner_function()


```python
def square(value):
  """Returns the square of a number."""
  new_val = value ** 2
  return new_val
square(3)

print (new_val)

```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-6-fd5570a13839> in <module>
          5 square(3)
          6 
    ----> 7 print (new_val)
    

    NameError: name 'new_val' is not defined



```python
new_val = 10
def square(value):
  """Returns the square of a number."""
  new_val = value ** 2
  return new_val 
```


```python
def outer_function():
    a = 20
    def inner_function():
        a = 30
        print 'a =',a

    inner_function()
    print'a =',a
     
a = 10
outer_function()
print 'a =',a
```

    a = 30
    a = 20
    a = 10


In this program, three different variables a are defined in separate namespaces and accessed accordingly.


```python
def outer_function():
    global a
    a = 20
    def inner_function():
        global a
        a = 30
        print('a =',a)

    inner_function()
    print('a =',a)
     
a = 10
outer_function()
print('a =',a)
```

    ('a =', 30)
    ('a =', 30)
    ('a =', 30)


Here, all reference and assignment are to the global a due to the use of keyword **global**.

## LEGB Rule

In Python, the LEGB rule is used to decide the order in which the namespaces are to be searched for scope resolution.
The scopes are listed below in terms of hierarchy(highest to lowest/narrowest to broadest): 

* Local(L): Defined inside function/class
* Enclosed(E): Defined inside enclosing functions(Nested function concept)
* Global(G): Defined at the uppermost level
* Built-in(B): Reserved names in Python builtin modules

![alt text](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/ScopeResolution-1-300x260.png)

**Local Scope**:
Local scope refers to variables defined in current function.Always, a function will first look up for a variable name in its local scope. Only if it does not find it there, the outer scopes are checked.




```python
# Local Scope 
  
pi = 'global pi variable'
def inner(): 
    pi = 'inner pi variable'
    print(pi) 
  
inner() 
```

    inner pi variable



On running the above program, the execution of the inner function prints the value of its local(highest priority in LEGB rule) variable pi because it is defined and available in the local scope.

**Local and Global Scopes :**
If a variable is not defined in local scope, then, it is checked for in the higher scope, in this case, the global scope.


```python
# Global Scope 

pi = 'global pi variable'
def inner(): 
	pi = 'inner pi variable'
	print(pi) 

inner() 
print(pi) 

```

    inner pi variable
    global pi variable


**Local, Enclosed and Global Scopes :**

For the enclosed scope, we need to define an outer function enclosing the inner function, comment out the local pi variable of inner function and refer to pi using the nonlocal keyword.


```python
# Enclosed Scope 

pi = 'global pi variable'

def outer(): 
	pi = 'outer pi variable'
	def inner(): 
		# pi = 'inner pi variable' 
		nonlocal pi 
		print(pi) 
	inner() 

outer() 
print(pi) 

```

    outer pi variable
    global pi variable


When outer() is executed, inner() and consequently the print functions are executed, which print the value the enclosed pi variable. The statement in line 10 looks for variable in local scope of inner, but does not find it there. Since pi is referred with the nonlocal keyword, it means that pi needs to be accessed from the outer function(i.e the outer scope). 

**Local,Enclosed,Global and Built-in Scopes :**
The final check can be done by importing pi from math module and commenting the global, enclosed and local pi variables as shown below:


```python
# Built-in Scope 
from math import pi 

# pi = 'global pi variable' 

def outer(): 
	# pi = 'outer pi variable' 
	def inner(): 
		# pi = 'inner pi variable' 
		print(pi) 
	inner() 

outer() 

```

    3.141592653589793


Since, pi is not defined in either local, enclosed or global scope, the built-in scope is looked up i.e the pi value imported from math module. Since the program is able to find the value of pi in the outermost scope, the following output is obtained. 

# Classes and Objects

## 2.1 Class
Class can be defined as a collection of objects. It is a logical entity that has some specific attributes and methods. For example: if you have an employee class then it should contain an attribute and method i.e. an email id, name, age, salary etc.



```python
# Syntax
class className:
  <statement-1>
  .
  .
  .
  .
  .
  <statement-n>
```

## 2.2 Object 
*   Object is an entity that has state and behavior. It may be anything. It may be physical and logical. For example: mouse, keyboard, chair, table, pen etc.
*   Everything in Python is an object, and almost everything has attributes and methods. All functions have a built-in attribute **`__doc__`** , which returns the doc string defined in the function source code.

##  Creating an Object 

We saw that the class object could be used to access different attributes.

It can also be used to create new object instances (instantiation) of that class. The procedure to create an object is similar to a function call.


```python
#Syntax 

ob = MyClass()

#Everything in Python is an Object
```


```python
class MyClass:
    variable = "CodeFemme"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

```

### Accessing Object Variables

To access the variable inside of the newly created object "myobjectx" you would do the following:


```python
class MyClass:
    variable = "code"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

print myobjectx.variable
```

    code


### Accessing Objects methods

Objects can also contain methods. Methods in objects are functions that belongs to the object.

Let us create a method in the Person class:


```python
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def myfunc(self):
    print("Hello my name is " + self.name)

p1 = Person("John", 36)
p1.myfunc()
```

    Hello my name is John


### Delete Objects

You can delete objects by using the **del** keyword:


```python
del p1
```

### Delete Object properties

Delete the age property from the p1 object:


```python
del p1.age
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-17-11aed6544815> in <module>
    ----> 1 del p1.age
    

    NameError: name 'p1' is not defined


## 2.3 Defining a class

Like function definitions begin with the keyword def, in Python, we define a class using the keyword class.

The first string is called docstring and has a brief description about the class. Although not mandatory, this is recommended.

Here is a simple class definition.


```python
class Class_Name:
    '''This is a docstring. I have created a new class'''
    def function():
      print('This is a function inside a class')
```

A class creates a new local namespace where all its attributes are defined. Attributes may be data or functions. 

As soon as we define a class, a new class object is created with the same name. This class object allows us to access the different attributes as well as to instantiate new objects of that class.


```python
class MyClass:
	"This is my second class"
	a = 10
	def func(self):
		print('Hello')

# Output: 10
print(MyClass.a)

# Output: 'This is my second class'
print(MyClass.__doc__)
```

    10
    <function MyClass.func at 0x7f38e234af28>
    This is my second class


## 2.4 Constructors in Python using \__init__

The examples above are classes and objects in their simplest form, and are not really useful in real life applications.

To understand the meaning of classes we have to understand the built-in \__init__() function.

All classes have a function called \__init__(), which is always executed when the class is being initiated.

The \__init__() function is called automatically every time the class is being used to create a new object.

Use the \__init__() function to assign values to object properties, or other operations that are necessary to do when the object is being created:


```python
class Example:
  def __init__(self):
    print('CodeFemme')

    
obj1= Example()

obj2= Example() # Each time an object is created, the __init__ function is called.
```

## self

So we've come across the term 'self' in our function parameters inside classes in the previous cells.

The self parameter is a reference to the class itself, and is used to access variables that belongs to the class.

It does not have to be named self , you can call it whatever you like, but it has to be the first parameter of any function in the class:



```python
class Person:
  def __init__(self):
 
    self.name = 'Tarun'
    self.age = 19

p1= Person()

p2= Person()

p1.name= 'Raja'
p1.age= 18

print(p1.name)
print(p1.age)

```

    Raja
    18



```python
class Person:
  def __init__(self):
 
    self.name = 'Coder'
    self.age = 19
  def update(self): #a new function
    self.age= 30

p1= Person()

p2= Person()

p1.name= 'Rajni'


p1.update() 
# We dont generally know which object the update() points to. 
# Since we've mentioned p1, self variable will redirect it to p1.

print(p1.name)
print(p1.age)

```

    Rajni
    30



```python
class Person:
  def __init__(abc, name, age):
    abc.name = name
    abc.age = age

  def myfunc(abc):
    print("Hello my name is " + abc.name)

p1 = Person("John", 36)
p1.myfunc()

```

    Hello my name is John


## 2.5 Class attributes vs Instance attributes 

Class attributes, as the name suggests, belong to the class itself. These attributes will be shared by all the instances. Such attributes are
defined in the class body part, usually at the top, for legibility.

Class variables are variables that are being shared with all instances (objects) which were created using that particular class. So when accessed a class variable from any instance, the value will be same. 

Instance variables on the other hand are variables, which all instances keep for themselves (i.e a particular object owns its instance variables). So typically values of instance variables differ from instance to instance.



```python
class Shark:
    animal_type = "fish"

print(Shark.animal_type)
```

    fish



```python
class Shark:
    animal_type = "fish"
    location = "ocean"
    followers = 5


new_shark = Shark()
print(new_shark.animal_type)
print(new_shark.location)
print(new_shark.followers)  #ALSO CLASS VARIABLES
```

    fish
    ocean
    5


Class variables allow us to define variables upon constructing the class. These variables and their associated values are then accessible to each instance of the class.


```python
class Shark:
    def __init__(self, name, age):
        self.name = name
        self.age = age

new_shark = Shark("Sammy", 5)
print(new_shark.name)
print(new_shark.age)   #instance variable example
```

    Sammy
    5


The output we receive is made up of the values of the variables that we initialized for the object instance of new_shark.


```python
class Shark:
    # Class variables
    animal_type = "fish"
    location = "ocean"
    # Constructor method with instance variables name and age
    def __init__(self, name, age):
        self.name = name
        self.age = age
    # Method with instance variable followers
    def set_followers(self, followers):
        print("This user has " + str(followers) + " followers")
def main():
    # First object, set up instance variables of constructor method
    sammy = Shark("Sammy", 5)
    # Print out instance variable name
    print(sammy.name)
    # Print out class variable location
    print(sammy.location)
    # Second object
    stevie = Shark("Stevie", 8)
    # Print out instance variable name
    print(stevie.name)
    # Use set_followers method and pass followers instance variable
    stevie.set_followers(77)
    # Print out class variable animal_type
    print(stevie.animal_type)
if __name__ == "__main__":
    main()
```

    Sammy
    ocean
    Stevie
    This user has 77 followers
    fish


Here, we have made use of both class and instance variables in two objects of the Shark class, sammy and stevie.

## 2.6 Adding methods dynamically in Python

Given the dynamic nature of Python you can do many things in runtime, like add methods dynamically to an object or class.

Here is the simplest way, adding a method to and object:


```python
class Person(object):
    pass

def play():
    print ("i'm playing!")

p = Person()
p.play = play
p.play()
```

    i'm playing!


Note that play is just a function, it doesn't receive self. There is no way to p knows that it's a method.

## 2.7 Built-in attributes

Every Python class keeps the following built-in attributes and they can be accessed using dot operator like
any other attribute:


\__dict__ : It gives the dictionary containing the class's namespace.

\__doc__ : It returns the class's documentation string(also called docstring) and if no docstring is
defined for a class this built in attribute returns None



\__name__: It gives the class name.

\__module__: It specifies the module name in which the class is defined. This attribute is called  "\__main__" in interactive mode.

\__bases__ : It gives a possibly empty tuple containing the base classes, in the order of their occurrence in the base class list.


```python
class Test:
  '''A sample class to demonstrate built in attributes''' 

  rollno=1
  marks=75
  
  def __init__(self,rollno,marks):
    self.rollno=rollno
    self.marks=marks
    
  def display(self):
    print(" Roll No : " , self.rollno)
    print("Marks : " , self.marks)
    
print ("Test.__doc__:" , Test.__doc__)
print ("Test.__name__:" , Test.__name__)
print ("Test.__module__:" , Test.__module__)
print ("Test.__bases__:" , Test.__bases__)
print ("Test.__dict__:" , Test.__dict__)
```

    Test.__doc__: A sample class to demonstrate built in attributes
    Test.__name__: Test
    Test.__module__: __main__
    Test.__bases__: (<class 'object'>,)
    Test.__dict__: {'__module__': '__main__', '__doc__': 'A sample class to demonstrate built in attributes', 'rollno': 1, 'marks': 75, '__init__': <function Test.__init__ at 0x7f95ac677510>, 'display': <function Test.display at 0x7f95ac6771e0>, '__dict__': <attribute '__dict__' of 'Test' objects>, '__weakref__': <attribute '__weakref__' of 'Test' objects>}


## 2.8 Static Methods

Static methods in Python are extremely similar to python class level methods, the difference being that a static method is bound to a class rather than the objects for that class.

This means that a static method can be called without an object for that class. This also means that static methods cannot modify the state of an object as they are not bound to it. Let’s see how we can create static methods in Python.

We can create a static method using the **@staticmethod** keyword




```python
class Calculator:

    # create addNumbers static method
    @staticmethod
    def addNums(x, y):
        return x + y

print(Calculator.addNums(15, 110))
```

    125


## 2.9  Garbage Collection 

Python automatically allocates and de-allocates memory. The user does not have to preallocate or
deallocate memory by hand as one has to when using dynamic memory allocation in languages such as C
or C++. Python uses two strategies for memory allocation-reference counting and automatic garbage
collection.

#### 1. Reference Counting 

Prior to Python version 2.0, the Python interpreter only used reference counting for memory
managementReference counting works by counting the number of times an object is referenced by
other objects in the system. Python's garbage collector runs during program execution and is triggered
when an object's reference count reaches zero.




#### 2. Automatic Garbage Collection

In this case garbage collection is a scheduled activity. Python schedules garbage collection based upon
a threshold of object allocations and object de-allocations. Python deletes the objects which are not
required, may it be built-in types or class instances, through the process named garbage collection.
When the number of allocations minus the number of de-allocations are greater than the threshold
number, the garbage collector is run and the unused block of memory is reclaimed. One can inspect the
threshold for new objects by loading the gc module and asking for garbage collection thresholds.
Automatic garbage collection will not run if your Python device is running out of memory. In such
case, your application will throw exceptions, which must be handled otherwise your application will
crash. Also, the automatic garbage collection occurs more for the number of free objects than the size of
objects.

## 2.10 Some other object oriented programming concepts


### Data Abstraction 

Data abstraction and encapsulation both are often used as synonyms. Both are nearly synonym because data abstraction is achieved through encapsulation.

Abstraction is used to hide internal details and show only functionalities. Abstracting something means to give names to things, so that the name captures the core of what a function or a whole program does.

### Polymorphism 

Polymorphism is made by two words "poly" and "morphs". Poly means many and Morphs means form, shape. It defines that one task can be performed in different ways. For example: You have a class animal and all animals talk. But they talk differently. Here, the "talk" behavior is polymorphic in the sense and totally depends on the animal. So, the abstract "animal" concept does not actually "talk", but specific animals (like dogs and cats) have a concrete implementation of the action "talk".


```python

```


#  Chapter 4 : Inheritance
Inheritance is a feature of object-oriented programming. It specifies that one object acquires all the properties and behaviors of parent object. By using inheritance you can define a new class with a little or no changes to the existing class. The new class is known as derived class or child class and from which it inherits the properties is called base class or parent class.

It provides re-usability of the code.

Inheritance can be categorised into five types:


1.   Single Inheritance
2.   Multilevel Inheritance
3.   Multiple Inheritance
4.   Hierarchical Inheritance
5.   Hybrid Inheritance




```python
# Inheritance Syntax

''' Note object in bracket. 
 (Generally, object is made ancestor of all classes) 
 In Python 3.x "class Person" is  
 equivalent to "class Person(object)"
 But in Python 2.x it is necessary to declare it explicitly'''

class BaseClass(object):
  # Statements of BaseClass go here
  pass

class DerivedClass(BaseClass):
  # Statements of BaseClass go here
  pass

obj1 = BaseClass()
obj2 = DerivedClass()

print (type(obj1))
print (type(obj2))
```

    <class '__main__.BaseClass'>
    <class '__main__.DerivedClass'>


## 4.1 Single Inheritance
When a child class inherits from only one parent class, it is called as single inheritance.

> ![alt text](https://i.imgur.com/MP1uEKk.png)




```python
# Example program to implement single inheritance
class Person(object):
    def __init__(self, first, last):
        self.firstname = first
        self.lastname = last

    def Name(self):
        return self.firstname + " " + self.lastname


class Employee(Person):
    def __init__(self, first, last, staffnum):
        # Notice that we are using class name for calling the constructor of the parent class
        # We may also use super() like
        # super(Employee, self).__init__(first, last)
        Person.__init__(self,first, last)
        self.staffnumber = staffnum

    def GetEmployee(self):
        return self.Name() + ", " +  self.staffnumber

x = Person("Marge", "Simpson")
y = Employee("Homer", "Simpson", "1007")

print (x.Name())
print (y.GetEmployee())
```

    Marge Simpson
    Homer Simpson, 1007


### In python the above task of extending __init__ () can be achieved the following ways:

* By using the super() function
* By using the name of the super class.


### Method 1: super() function: 

In Python, super() function is used to call the methods of base class which have been extended in derived class. 



```python
class Mammal(object):
  def __init__(self, mammalName):
    print(mammalName, 'is a warm-blooded animal.')
    
class Dog(Mammal):
  def __init__(self):
    print('Dog has four legs.')
    super().__init__('Dog')
    
d1 = Dog()
```

    Dog has four legs.
    Dog is a warm-blooded animal.


We do not need to specify the name of the base class if we use super(), hence we can easily change the base class for Dog method easily.

### Method 2:  By using name of the super class

In Python, name of the base class can also be used
to access the method of the base class which has been extended in derived class


```python
class Person(object):
    def __init__(self, first, last):
        self.firstname = first
        self.lastname = last

    def Name(self):
        return self.firstname + " " + self.lastname


class Employee(Person):
    def __init__(self, first, last, staffnum):
      
        Person.__init__(self,first, last)
        self.staffnumber = staffnum

```

## 4.2 Multiple Inheritance 

Like C++, a class can be derived from more than one base classes in Python. This is called multiple inheritance.

In multiple inheritance, the features of all the base classes are inherited into the derived class. The syntax for multiple inheritance is similar to single inheritance.

![alt text](https://i.ibb.co/PQvSNH6/multi-inherit.png)


```python
#Example pseudocode

class Base1:
    pass

class Base2:
    pass

class MultiDerived(Base1, Base2):
    pass
```


```python
# Python example to show working of multiple 
# inheritance 
class Base1(object): 
	def __init__(self): 
		self.str1 = "Geek1"
		print( "Base1")

class Base2(object): 
	def __init__(self): 
		self.str2 = "Geek2"		
		print( "Base2")

class Derived(Base1, Base2): 
	def __init__(self): 
		
		# Calling constructors of Base1 
		# and Base2 classes 
		Base1.__init__(self) 
		Base2.__init__(self) 
		print( "Derived")
		
	def printStrs(self): 
		print(self.str1, self.str2) 
		

ob = Derived() 
ob.printStrs() 

```

    Base1
    Base2
    Derived
    Geek1 Geek2


## 4.3 Multilevel Inheritance

 We can also inherit form a derived class. This is called multilevel inheritance. It can be of any depth in Python.

In multilevel inheritance, features of the base class and the derived class is inherited into the new derived class.

>  ![alt text](https://i.imgur.com/nvwXNUB.png)


```python
#Example pseudocode

class Base:
    pass

class Derived1(Base):
    pass

class Derived2(Derived1):
    pass
```


```python
# A Python program to demonstrate inheritance 

# Base or Super class. Note object in bracket. 
# (Generally, object is made ancestor of all classes) 
# In Python 3.x "class Person" is 
# equivalent to "class Person(object)" 
class Base(object): 
	
	# Constructor 
	def __init__(self, name): 
		self.name = name 

	# To get name 
	def getName(self): 
		return self.name 


# Inherited or Sub class (Note Person in bracket) 
class Child(Base): 
	
	# Constructor 
	def __init__(self, name, age): 
		Base.__init__(self, name) 
		self.age = age 

	# To get name 
	def getAge(self): 
		return self.age 

# Inherited or Sub class (Note Person in bracket) 
class GrandChild(Child): 
	
	# Constructor 
	def __init__(self, name, age, address): 
		Child.__init__(self, name, age) 
		self.address = address 

	# To get address 
	def getAddress(self): 
		return self.address		 

# Driver code 
g = GrandChild("Geek1", 23, "Noida") 
print(g.getName(), g.getAge(), g.getAddress()) 

```

    Geek1 23 Noida


### Some other types are:

### Hierarchical Inheritance :
More than one derived classes are created from a single base.

![alt text](https://i.ibb.co/g4KWtLb/hieinhe.png)

###  Hybrid Inheritance: 

This form combines more than one form of inheritance. Basically, it is a blend of more than one type of inheritance.

![alt text](https://i.ibb.co/L6HX34Q/hybrid-inheritance.png)

## 4.4 Method Overriding

The feature of overriding methods enables the programmer to provide specific implementation to a
method in the subclass which is already implemented in the superclass. The version of a method that is
executed will be determined by the object that is used to invoke it. If an object of a parent class is used to
invoke the method, then the version in the parent class will be executed, but if an object of the subclass is
used to invoke the method, then the version in the child class will be executed.

In Python method overriding occurs simply defining in the child class a method with the same name of a method in the parent class. When you define a method in the object you make this latter able to satisfy that method call, so the implementations of its ancestors do not come in play.


```python
class Parent(object):
    def __init__(self):
        self.value = 5

    def get_value(self):
        return self.value

class Child(Parent):
    def get_value(self):
        return self.value + 1
      
c = Child()

c.get_value()
```




    6



## 4.5 Abstract Methods

An abstract method is a method defined in a base class, but that may not provide any implementation. In Java, it would describe the methods of an interface.

An abstract method is provided by the (abstract) parent class but only implemented in the children classes.

So the simplest way to write an abstract method in Python is:


```python
class Pizza(object):
    def get_radius(self):
        raise NotImplementedError  #GTA vehicles/ different types/ can use abstract template to create and set params for diff types of vehicles.
```

Any class inheriting from Pizza should implement and override the get_radius method, otherwise an exception would be raised.

This particular way of implementing abstract method has a drawback. If you write a class that inherits from Pizza and forget to implement get_radius, the error will only be raised when you'll try to use that method.

The method of implementing abstract methods by using the "NotImplementedError" exception has a
drawback

If you write a class that inherits from circle and forget to implement get_radius, the error will only be raised
when you'll try to use that method.


```python

```

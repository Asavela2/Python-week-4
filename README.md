# Inheritence

Inheritance is a fundamental concept in object-oriented programming (OOP) 
where a new class (subclass or derived class) is created by inheriting attributes
and behaviors from an existing class (base class or parent class). 
The subclass can add or override functionalities, promoting code reuse.

## Syntax

The syntax for defining a subclass in Python is straightforward.
A class is declared by specifying the base class(es) in parentheses after the class name. 

Here is a basic example:
````class Animal:
    def __init__(self, species):
        self.species = species

    def speak(self):
        return "Generic animal sound"

class Dog(Animal):
    def bark(self):
        return "Woof!"
````

```#In this example, Dog is the subclass, and Animal is the base class. The Dog class inherits the __init__ and speak methods from the Animal class.```


## Code Reusability:

Inheritance promotes code reusability, as common attributes and methods need not be redefined in every class. 
The base class encapsulates shared functionalities, and subclasses can focus on specific, unique features.
This simplifies maintenance and reduces the likelihood of errors.

## Method Overriding:

Subclasses can provide their own implementation of a method that is already defined in the base class.
This is known as method overriding. For instance:

``class Cat(Animal):
    def speak(self):
        return "Meow!"
        ``
       `` #Here, the speak method in the Cat class overrides the speak method in the Animal class.``

       
    
  ## Access to Base Class:
  
A subclass can access the attributes and methods of the base class. 
This is achieved using the super() function. 
It allows calling methods from the base class within the subclass.

``class Puppy(Dog):
    def bark(self):
        return super().bark() + " Playfully!"``
    
        
## Types of Inheritance:

1. # Single Inheritance:

A class inherits from only one base class.
Example: class Dog(Animal):

2. # Multiple Inheritance:

A class inherits from more than one base class.
Example: class Engineer(Person, Employee):

3. # Multilevel Inheritance:

A class is derived from another derived class.
Example: class Grandchild(Child):

# Iterators:

An iterator in Python is an object that allows you to iterate (loop) through a collection of elements, such as a list or a tuple. 
It provides a way to access the elements of a container sequentially without exposing the underlying details of the container's implementation.

Key Concepts:

## Iterable:

An object capable of returning its elements one at a time is called an iterable.
- Examples of iterables include lists, tuples, strings, and more.
  
## Iterator Protocol:

An iterator in Python follows the iterator protocol, which involves implementing the __iter__ and __next__ methods.
- The __iter__ method returns the iterator object itself.
  
- The __next__ method returns the next element in the sequence and raises StopIteration when there are no more elements.


`` # Creating an iterator for a list
class MyIterator:
    def __init__(self, data):
        self.data = data
        self.index = 0``

    def __iter__(self):
        return self

    def __next__(self):
        if self.index < len(self.data):
            result = self.data[self.index]
            self.index += 1
            return result
        else:
            raise StopIteration

`` #Using the iterator
my_list = [1, 2, 3, 4, 5]
my_iterator = MyIterator(my_list)
for item in my_iterator:
    print(item) ``


## Generators:

A generator in Python is a concise way to create iterators.
It is a special type of iterator that is defined using a function with the yield keyword. 
Generators provide a convenient way to iterate over a potentially large set of data without loading the entire set into memory.



## yield Statement:

The yield statement is used in a function to produce a series of values to be iterated over.
When the generator function is called, it returns a generator object.

## Lazy Evaluation:

Generators use lazy evaluation, meaning they produce values on-the-fly and only when requested.
This can be more memory-efficient than creating a list with all values at once.

For Example :

`` # Creating a generator function
def my_generator(data):
    for item in data:
        yield item
        # Using the generator
        my_list = [1, 2, 3, 4, 5]
        my_gen = my_generator(my_list)
        for item in my_gen:
    print(item) ``



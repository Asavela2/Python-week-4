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










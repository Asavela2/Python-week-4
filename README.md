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


```
 # Creating an iterator for a list
class MyIterator:
    def __init__(self, data):
        self.data = data
        self.index = 0        

def __iter__(self):
        return self      

def __next__(self):
  if self.index < len(self.data):
      result = self.data[self.index]
      self.index += 1
            return result
        else:
            raise StopIteration
# Using the iterator
   my_list = [1, 2, 3, 4, 5]
            
my_iterator = MyIterator(my_list)

for item in my_iterator:
    print(item)

```


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

```
 # Creating a generator function
def my_generator(data):
    for item in data:

   yield item
   # Using the generator

    my_list = [1, 2, 3, 4, 5]
        
 my_gen = my_generator(my_list)
for item in my_gen:
        
    print(item)
```

## Advantages of Generators:

- Memory Efficiency:

Generators produce values on demand, which can be more memory-efficient compared to creating a list with all values at once.

- Simplified Syntax:

Generators provide a more concise and readable way to create iterators.

- Infinite Sequences:

Generators allow the creation of infinite sequences, as values are generated only when needed.

## Error Output Redirection:

Error output redirection involves capturing and handling errors, 
ensuring that they are properly logged or directed to the desired output stream.
This is commonly done using the # try, # except, and # finally blocks.

```
try:
    # Code that might raise an exception
    result = 10 / 0
except ZeroDivisionError as e:
    # Handling specific exception
    print(f"Error: {e}")
except Exception as e:
    # Handling other exceptions
    print(f"Unexpected error: {e}")
else:
    # Code to execute if no exception occurred
    print("No errors!")
finally:
    # Code to execute regardless of whether an exception occurred
    print("Finally block executed.")
```
## Key Points:

# 1. Exception Handling:

- Use try, except, and optionally finally blocks for effective exception handling.

2. # Error Output Redirection:

- Redirect error output to appropriate streams for logging or user feedback.

3. # Program Termination:

- Use sys.exit() or raise a SystemExit exception to gracefully terminate the program.

4. # Exit Codes:

- Provide meaningful exit codes (non-zero for errors) to indicate the program's status to calling processes.

5. # Finally Block:
- Use the finally block for cleanup operations that must be executed, whether an exception occurred or not.


# Logging

- Logging in Python is a way to capture and store information about the execution of a program.
- The logging module in Python provides a flexible and powerful framework for emitting log messages from Python programs.

```
 import logging

# Configure logging
logging.basicConfig(level=logging.DEBUG, 
                    format='%(asctime)s - %(levelname)s - %(message)s')

# Example usage
def example_function():
    logging.debug("This is a debug message.")
    logging.info("This is an info message.")
    logging.warning("This is a warning message.")
    logging.error("This is an error message.")
    logging.critical("This is a critical message.")

if __name__ == "__main__":
    example_function()
```
# Explanation:
1 ## Importing the logging Module:

- Start by importing the logging module.
  
2 # Configuring Logging:

- Use basicConfig to configure the logging system.
- level sets the threshold level for the messages (e.g., logging.DEBUG).
- format defines the format of the log messages.
  
3 # Logging Levels:

- There are several logging levels available, including DEBUG, INFO, WARNING, ERROR, and CRITICAL. Each level represents the severity of the log message.
- 
4 # Logging Messages:

- Use logging.debug(), logging.info(), logging.warning(), logging.error(), and logging.critical() to emit log messages at different levels.
  
5 # Log Message Format:

- The format specified in basicConfig determines how the log messages are presented. %(asctime)s, %(levelname)s, and %(message)s are placeholders for the timestamp, log level, and message, respectively.
  
6 # Example Function:

- In the example function (example_function), different log messages are emitted at various levels.
  
# Log Handlers and Formatters:
- Handlers: Define where the log records go. Examples include the console (StreamHandler), files (FileHandler), or even network sockets (SocketHandler).

- Formatters: Specify the layout of the log records. You can customize the appearance of log messages by configuring formatters.

## Example with FileHandler and Formatter:

```
import logging

# Configure logging
logging.basicConfig(level=logging.DEBUG)

# Create a FileHandler and set its formatter
file_handler = logging.FileHandler("example.log")
file_formatter = logging.Formatter('%(asctime)s - %(levelname)s - %(message)s')
file_handler.setFormatter(file_formatter)

# Add the FileHandler to the root logger
logging.getLogger('').addHandler(file_handler)

# Example usage
def example_function():
    logging.debug("This is a debug message.")
    logging.info("This is an info message.")
    logging.warning("This is a warning message.")
    logging.error("This is an error message.")
    logging.critical("This is a critical message.")

if __name__ == "__main__":
    example_function()
```

    



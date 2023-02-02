# Oops concept in cpp


<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## Introduction
OOPS stands for Object Oriented Programming System. It is a programming technique to organize the code in a structured way. It uses objects and classes to organize and structure the code.

### Class
In C++, a class is a blueprint for an object. It defines the data members (variables) and member functions (functions) of the object, as well as the relationships between different objects of the same class. Classes provide a way to encapsulate data and functionality, making it easier to organize and maintain code.

A class is defined using the "class" keyword, followed by the name of the class. The data members and member functions are defined within the class definition. For example:
```cpp
class Example {
  public:
    int data1;
    int data2;
    void function1();
    int function2(int input);
};
```
This defines a class called "Example" with two data members (data1 and data2) and two member functions (function1 and function2). The "public" keyword in the class definition makes the data members and member functions accessible to code outside of the class.


### Object
In C++, an object is an instance of a class. An object has its own unique set of data members (also known as properties or attributes) and member functions (also known as methods or behaviors) that are defined by the class.

An object of a class is created by declaring a variable of the class type and then creating an instance of the class using the "new" operator. This can be done as follows:
```cpp
Example object1;
Example* object2 = new Example;
```
The first line creates a stack-allocated object of the class type, while the second line creates a heap-allocated object, which is pointed by the pointer 'object2'


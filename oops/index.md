# Oops(object oriented programming)


<!--more-->
{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## Introduction
Object-oriented-programing(oops) is 

it inc the readability, extansability, managability of the code.

### Class
it is user defined data type just like int char or other datatypes.
it contains the properties of a class or we can say data members.
we can access datamembers by using "." operator.
class can be created as follows:
```c
class Hero
{
    //properties
    public:
    int health;
    char level; 
}
```

## object
it is an instance of `class` just like variable

>if we create an object with empty class then it takes i byte of memory
 `class test{    };`

 
## Inheritance
Inheritance is a process through which derived class acquires all the properties and behaviours of its parent class automatically.

* create new class from existing class.
* new class inherits the features of base or parent class and have additional features of its own.

>Syntax:
`class child_class: access_modifier parent_class{
  // body of the child class
};
`

access modifier

* public 
* private
* protected

{{< figure src="/posts/DSA/oops/photo.png" >}}
{{< figure src="/posts/DSA/oops/Start.png" >}}

## Types of Inheritance
There are mainly 5 type of inheritance:
1. single inheritance
2. multiple inheritance
3. multilevel inheritance
4. hierarchical inheritance
5. hybrid inheritance

### Single Inheritance
When one class inherits another class

### Multiple inheritance
Multiple inheritance is the process of deriving a new class that inherits the attributes from two or more classes


## Encapsulation
Wrapping of data members and methods into a single unit is called Encapsulation.
## Abstraction

## Polymorphism
### Compiletime Polymorphism
### Runtime polymorphism

## Constructor
### Default
### Parameterized
### Copy 

## Destructor

## Access Specifiers IMP :
The access specifiers are used to define how functions
and variables can be accessed outside the class. There are three types of
access specifiers:

### 1. Private:
Functions and variables declared as private can be accessed only
within the same class, and they cannot be accessed outside the class they
are declared.

### 2. Public:
Functions and variables declared under public can be accessed from
anywhere.

### 3. Protected:
Functions and variables declared as protected cannot be
accessed outside the class except a child class. This specifier is generally
used in inheritance.

### Delete
It is used to release a unit of memory.

### Delete[]
It is used to release an array.

### Virtual Inheritance
It facilitates you to create only one copy of each object even if the object appears more than one in the hierarchy.

### Overloading
Overloading is a static binding whereas overriding is dynamic binding, overloading is nothing but the same method with different arguments, and it may or may not return the same value in the same class itself.

### Function overloading
Function Overloading is defined as we can have more than one version of the same function. The versions of a function will have different signatures meaning that they have different set of parameters.

### Operator overloading
Operator overloading is defined as the standard
operator can be redefined so that it has a different meaning when applied to
the instances of a class.

### Overriding
Overriding is the same method name with the same arguments and return types associated with the class and its child class.

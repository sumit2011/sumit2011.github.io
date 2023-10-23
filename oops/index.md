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



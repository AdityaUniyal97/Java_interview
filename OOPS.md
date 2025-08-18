
## Procedure Programming and OOP
**Procedure Programming** It is a paradigm where the program is divided into multiple functions . The focuse is on action to be perofrmed
**OOP** is programming where the program is organized intor objects , which define the behavoir of the data. The focus is on modeling the real world entity
##  Class 
- is buleprint or template for creating objects
- It logically represent the attributes and methods that the object will have
## Object
- Object is an instance of a class. 
- Whenever an object is created from a class memory is allocated for it , and holds the data which is specifief by the class
- In java objects are automatically deleted by the Garabage collector
```
import java.util.*;

public static void main(String[] args) {
        Employee obj1 = new Employee();
        obj1.setName("Raj"); 
        obj1.setSalary(10000); 
        Employee obj2 = new Employee();
        obj2.setName("Rahul"); 
        obj2.setSalary(15000); 
        System.out.println("Salary of " + obj1.employeeName + " is " + obj1.getSalary());
        System.out.println("Salary of " + obj2.employeeName + " is " + obj2.getSalary());
    }
}

```
## Attributes
- Attributes are the cahracterstics of an object . They represent the current state of an object at give moment . Attributes are defined inside the classs and it can hold differenct types of the information which is related to objects.

## Methods 
- Methods are function that are defined inside a class and reprsent the behavoiur of an object

## Stack and Heap Memory
**Stack Memory** Stack memory is automatically managed , typically used for storing the local vairables and function calls and it follows the LIFO(Last in First Out Order) 

**Heap Memory** dynamically allocates and deallocates the objects  and data structures whose size isn;t known at the compile times.

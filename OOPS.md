
## Procedure Programming and OOP
**Procedure Programming** It is a paradigm where the program is divided into multiple functions . The focuse is on action to be perofrmed
**OOP** is programming where the program is organized intor objects , which define the behavoir of the data. The focus is on modeling the real world entity
##  Class 
- is buleprint or template for creating objects
- It logically represent the attributes and methods that the object will have
## Object
- Object is an instance of a class. 
- Whenever an object is created from a class , memory is allocated for it , and holds the data which is specifief by the class
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
## Attributes & Method
**Attribute**
- Attributes are the cahracterstics of an object . They represent the current state of an object at give moment . Attributes are defined inside the classs and it can hold differenct types of the information which is related to objects.
**Method**
- Methods are function that are defined inside a class and reprsent the behavoiur of an object
```
import java.util.*;
class BankAccount{
    private String name; //Attributes
    private double balance;
    public BankAccount(String name , double balance){
        this.name = name;
        this.balance = balance;
    }
    public void setName(String name){
        this.name = name;
    }
    public String getName(){
        return name;
    }
    public double getBalance(){
        return balance;
    }
    public void deposit(double amount){
        balance += amount;
    }
    public boolean withdrawl(double amount){
        if(amount >= balance){
            System.out.println("Insufficent amount");
            return false;
        }
        balance = balance - amount;
        return true;
    }
}
```
## Stack and Heap Memory
**Stack Memory** Stack memory is automatically managed , typically used for storing the local vairables and function calls and it follows the LIFO(Last in First Out Order) 

**Heap Memory** dynamically allocates and deallocates the objects  and data structures whose size isn;t known at the compile times.

## Instance Variable
- Instance variable are declared inside the class but outside any method
- Instance variable belongs to the objects of the class
- Every object can have its own copy of the instance vairable
- Thier values can be dirrent for differnet objects
- Instance vairable are accessed using the object refference(obj.variableName)
```
class Student{
    String name;
    int age;
}
public class Main{
    public static void main(Stirng agrs[]){
        Strundent s1 = new Student();
        s1.name = "Aditya";
        s1.age = 21;
        System.out.println(s1.name);
        System.out.println(s1.age);
    }
}
```

## Constructor
- Constructor is a special method in a class which have the same name as the class name
- Constructor is automatically called during object creation
- Constructor does'nt have any return type
**Uses of Constructor**
- **Object Initialization** = Assigns default value or user defined values to variable at run time
- **Code Reusability** = Same logic for intialization is written everytime which creates the code reusability
**<u><b>Types of Constror</b></u> 
Non-parametrised Constror(Default Construtor)**
- A constructor which doesn't take any argument as the input its is called as the Non-paramterised constructor
- It return defualt values which is 0 for primitive dataype , NULL for non primitive data type
```
class Student{
  Employee(){
	System.out.println("hello");
  }
}
```

**Parameterized Constructor**
- Takes the arguments to initalise an object with specific values
```
class Student{
	String name , int age;
	Student(String name , int age){
		this.age = age;
		this.name = name;
	}
}
```

**Copy Constructor**
- Creates the new object by copying the vlaues of another object
```
class Student{
	string name , int age;
	Student(Student s){
	this.name = s.name;
	this.age = s.age;
	}
}
```
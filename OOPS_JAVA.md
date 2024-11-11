Here’s an enhanced version with lines added for a polished appearance in Obsidian:

---

### Folder: `Object-Oriented Programming (OOP)`

---

#### 1. OOP Basics

Object Oriented Programming language is a way of writing code , in which we follow a structured approach so that our code become easy to maintain , execute and understand.

---

#### 2. Classes and Objects

- **Class**  
  A class is like a blueprint for creating an object  and a class will define the nature and the behavior of its object . We can also say that a class is also a data type having variable as object the difference between a primitive data type and a class data type is that primitive datatype are single value having no special capabilities while on other hand the class data type can have data members .  

  **---**

- **Object**  
  An object is a instance of a class , and it is used to call the data and the members of the class , Object is also know as the real world entity

  **---**

```
class Student{
int roll;
String name;

void takelevel(){
System.out.println("On Leave");
}

void bunkClass(){
System.out.println("Go Out And Play");
}
}

class Main(){
public static void Main(String Args)
{
Student obj = new Student();
obj.name = "Aditya";
System.out.println(obj.name);
}
}
```
---

#### 3. Core Features of OOP (Pillars)

- **Encapsulation**  
  Encapsulation can be defined as the wrapping up of data into a single unit  , Encapsulation is a protective shield that protect our data from being accessed to the outside world . In encapsulation we declare all the variables as private in a class and writing public method to set and get these values.
  **---**

- **Abstraction**  
 Abstraction means hiding the complex detail which are not relevant for the user and showing only those details which is suitable for them.

  **---**

- **Polymorphism**  
  Polymorphism allows functions to behave differently based on the object calling them. . Examples include method overloading (compile-time) and overriding (runtime).

  **---**

- **Inheritance**  
 Inheritence is used to design the realtionship . Inheritence creates code reusablity by defining the method in parent class and extending the parent class into child class so that we can access the function 
  **---**

---

#### 4. Access Modifiers

- **Definition**  
  Keyword used in the object - oriented programming(OOPS)language to specify the accessibility of classes , methods and other members.

   Private = access specifier can be accessed in the same class in which it is initialized 

   Default = access specifier is not initialized with any type of specifier we can access the default access modifier within the same package.

	Protected = Protected access specifier are allowed to be accessed from different package only if it is inherited

   Public = access specifier can be accessed from anywhere.
  **---**

---

#### 5. Advantages and Disadvantages of OOP

- **Advantages**  
  Enhanced code reusability, maintainability, and data security.

  **---**

- **Disadvantages**  
  Requires planning and can be complex for smaller projects.

  **---**

---

  **---**

---

#### 7. Structured vs. Object-Oriented Programming

- **Structured Programming**  
  Organizes code in functions and modules, suitable for small programs.

  **---**

- **Object-Oriented Programming**  
  Focuses on reusable objects with state and behavior, better for larger applications.

  **---**

---

#### 8. OOP Languages

- Popular OOP languages include: Java, C++, Python, C#, JavaScript, and Ruby.

  **---**

---

#### 9. Types of Polymorphism

- **Compile-Time (Static) Polymorphism**  
  Uses method overloading or operator overloading, where binding is resolved at compile-time.

  **---**

- **Runtime (Dynamic) Polymorphism**  
  Uses method overriding, where the actual function executed is determined at runtime.

  **---**

---

#### 10. Overloading vs. Overriding

- **Overloading**  
  The same method name with different parameters (compile-time).

  **---**

- **Overriding**  
  Redefining a parent class method in the child class with the same signature (runtime).

  **---**

---

#### 11. Limitations of Inheritance

- Increases tight coupling, leading to dependencies between parent and child classes, which can complicate maintenance.

  **---**

---

#### 12. Types of Inheritance

- **Single Inheritance**: One child class inherits from one parent class.

  **---**

- **Multiple Inheritance**: One child class inherits from multiple parent classes (not supported in Java).

  **---**

- **Multilevel Inheritance**: A class derived from another derived class.

  **---**

- **Hierarchical Inheritance**: Multiple child classes inherit from a single parent class.

  **---**

- **Hybrid Inheritance**: Combines two or more types of inheritance.

  **---**

---

#### 13. Interface

- An interface contains only method declarations, which implementing classes must define. In Java, it promotes multiple inheritance.

  **---**

---

#### 14. Abstract Class vs. Interface

     

- **Abstract Class**: Can have both abstract and non-abstract methods; supports single inheritance.

  **---**

- **Interface**: Only abstract methods by default; supports multiple inheritance.

  **---**

---

#### 15. Memory Usage by Class

- Classes themselves don’t occupy memory; only objects do, as they initialize class members and methods upon instantiation.

  **---**

---

#### 16. Object Creation

- Not always necessary if the class has static methods; otherwise, an object is needed for non-static methods.

  **---**

---

#### 17. Structure vs. Class in C++

- Structures default to public members; classes default to private. Structures use `struct` keyword, and classes use `class`.

  **---**

---

#### 18. Constructors

- **Constructor**  
  Constructor is a special function get called whenever the object of a class is created , Constructor doesn't have any return type , Constructor has the same name as the class. If we don't pass the value to the constructor than in the case of primitive data type it get initialized with zero and in the case of non - primitive it get initialized with NULL. 

  **---**

- **Types of Constructors in C++**  
  - **Default**: No parameters.
  - **User Defined :**: Created by user itself.
  - **Parameterized**: Takes parameters.

  **---**
```
  class Student{
    private int roll;
    private String name;
    private int id;
    This is user defined Constructor
    public Student(){
        this.roll = 4;
        this.name = "Aditya Uniyal";
        this.id = 100;
    }
    
    This is Default Constructor
    public Student(){
        this.roll = roll;
        this.name = name;
        this.id = id;
    }
    
    // This is Parameterised Constructor
    public Student(String name , int roll , int id)
    {
        this.roll = roll;
        this.name = name;
        this.id = id;
    }
    public void show()
    {
        System.out.println(this.name+" "+this.roll+" "+this.id);
    }
}
public class Main{
    public static void main(String agrs[])
    {
        Student obj = new Student("Aditya" , 4 , 100);
        obj.show();
    }
}
```
---

#### 19. Destructor

- A special method to clean up when an object is no longer needed (C++ uses `~` symbol).

  **---**

---

#### 20. Constructor Overloading

- Multiple constructors can be defined with different parameters for flexible object initialization.

  **---**

---

#### 21. Destructor Overloading

- Not allowed; only one destructor per class.

  **---**

---

#### 22. Virtual Function

- A method in the parent class that can be overridden in a child class for dynamic behavior.

  **---**

---

#### 23. Pure Virtual Function

- An abstract method with no body, to be implemented by derived classes, defining an abstract class.

  **---**

---

#### 24. Abstract Class

- A base class meant for inheritance, with abstract and non-abstract methods, that cannot be instantiated.

  **---**

---
## 25.  This keyword? ##
. This refers to the current object for which the code is being executed , Internally when compiler calls a function of an object it pass this keyword
```
class Student
{
    int x ;
    int y;
    Student(int x , int y)
    {
        this.x = x;
        this.y = y;
    }
    void print()
    {
        System.out.println(x + " " + y);
    }
}
public class B{
    public static void main(String args[])
    {
        Student obj = new Student(10 , 20);
        obj.print();
    }
}
```

## Method Overloading : =  occur when two or more than two methods in the same class have the same name but different parameter . It allow method to perfrom similar method to behave differently based upon the user input.
## 1. Basic Idea

Low-Level Design means planning the code before writing it.

- HLD (High-Level Design) → What system we are building
- LLD (Low-Level Design) → How we will write the code for it

Simple understanding:

- HLD = big picture
- LLD = detailed coding plan

---

## 2. Real-Life Analogy

Building a house:

- HLD → number of rooms, layout
- LLD → wiring, switches, pipes, materials

Conclusion:  
LLD focuses on small implementation details.

---

## 3. Definition

Low-Level Design is the phase where we design:

- classes
- methods
- data structures
- logic of the system

It acts as a bridge between design and coding.

---

## 4. What We Do in LLD

In LLD, we decide:

- What classes will exist
- What methods each class will have
- What data each class will store
- How classes interact with each other

---

## 5. Example: Login System

### HLD

We need a user authentication system.

### LLD

We design actual code structure:

class User {  
    String email;  
    String password;  
}  
  
class AuthService {  
    void login(String email, String password) {}  
    void signUp(String email, String password) {}  
    void forgotPassword(String email) {}  
}

Explanation:

- User class stores data
- AuthService handles logic
- Methods define behavior

---

## 6. Key Characteristics of LLD

### 1. Detailed (Granular)

Focus on small details:

- variables
- methods
- logic

Example:  
Not just "login system" but how login works step by step.

---

### 2. Implementation Focused

LLD is directly used while coding.

It may include:

- pseudocode
- flow diagrams
- sequence diagrams

---

### 3. Uses OOP Concepts

LLD heavily uses:

- Encapsulation → hide data inside class
- Inheritance → reuse code
- Polymorphism → same method, different behavior
- Abstraction → show only necessary details

---

## 7. Difference: HLD vs LLD

|Aspect|HLD|LLD|
|---|---|---|
|Purpose|System overview|Detailed implementation|
|Detail Level|High (abstract)|Very detailed|
|Focus|Modules, architecture|Classes, methods|
|Output|System diagrams|Class diagrams, code structure|

---

## 8. Why LLD is Important

### 1. Avoids Rework

Clear design reduces mistakes later.

### 2. Improves Team Understanding

Everyone knows:

- what to build
- how it works

### 3. Helps Scalability

Well-designed code can grow easily.

### 4. Encourages Clean Code

Promotes:

- modular code
- reusable components
- maintainable systems

---

## 9. Final Summary

- LLD = detailed blueprint of code
- It defines classes, methods, and logic
- It uses OOP principles
- It directly helps in writing clean and scalable code
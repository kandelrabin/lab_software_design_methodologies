# Software Design Methodologies

### 1. What do we mean by coupling and cohesion when discussing structured design?

Structured design is a systematic methodology to determine design specification of a software. **Coupling** and **Cohesion** are tools of structured design that are used to measure the quality of software system's design. 

> **Coupling** is the degree of interdependence between various modules.

When classes and modules are highly coupled it is difficult to change and maintain the software code, because making small change to a code could mean we also need to refactor other components and sub-components that depend on it. In a low coupling scenario, the classes exist independently so changing something major in one class will not affect other classes.

Low coupling helps improve maintainability, allows reusability of code and facilitates the scalability of the software.


> **Cohesion** is the degree to which the elements within a module are functionally related.

High cohesion implies that the elements within a class are focused on achieving the class' purpose. Whereas, low cohesion means the elements within a class serve multiple purpose and deviate away from class' purpose.

High cohesion helps improve readability, allows better exception handling, and increases reliability of the system.

A good software design has high cohesion and low coupling.


#### 2. What is the difference between top-down and bottom-up design? Which best describes a function oriented design?


#### 3. In which design methodology would a class diagram be most useful?


#### 4. What are the four pillars of object oriented programming? Give a single-sentence description of each.

#### 5. What is the strategy pattern? How would its implementation differ between a functional and object oriented system?

#### 6. Imagine your development team is creating a new online payment system. In order to gain maximum market share it can't be tied to a particular sector - it needs to work just as well when ordering a takeaway as when buying a new coat. Which design methodology would you suggest following? Give some justification for your decision.
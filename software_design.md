# Software Design Methodologies

### 1. What do we mean by coupling and cohesion when discussing structured design?

**Coupling** and **cohesion** are tools of structured design that are used to measure the quality of software system's design. 

> **Coupling** is the degree of interdependence between various modules.

When classes and modules are highly coupled it is difficult to change and maintain the software code, because making small change to a code could mean we also need to change other components and sub-components that depend on it. In a low coupling scenario, the classes exist independently so changing something major in one class will not affect other classes.
Low coupling helps improve maintainability, allows reusability of code and facilitates the scalability of the software.


> **Cohesion** is the degree to which the elements within a module are functionally related.

High cohesion implies that the elements within a class are focused on achieving the class' purpose. Whereas, low cohesion means the elements within a class serve multiple purpose and deviate away from class' purpose. High cohesion helps improve readability, allows better exception handling, and increases reliability of the system.

A good software design has high cohesion and low coupling.


#### 2. What is the difference between top-down and bottom-up design? Which best describes a function oriented design?

> The **top-down design** approach focuses on formulation of the whole system without giving specific details of the components at the start. The bigger problem is then broken down into smaller problems with more details.

- Top-down design is based on decomposition approach.
- Top-down design may cause scalability issues as there is high coupling between the components.


> The **bottom-up design** approach focuses on identifying and defining individual components of the system, and then integrating them together to build bigger components. 

- Bottom-up design is based on composition approach.
- Bottom-up design facilitates scalability as it allows component reusability and reduces data redundancy.


Function oriented design starts as a high level requirement, which is then refined to specific details to solve the problem. 

Function oriented design is best described by top-down design.


#### 3. In which design methodology would a class diagram be most useful?

A class diagram is a visualisation of classes and their relationships. It includes class name, attributes, methods and access modifiers.

Class diagram is most useful for object oriented design because a class defines blueprint for creating objects, and each class defines set of attributes and object's behaviours.


#### 4. What are the four pillars of object oriented programming? Give a single-sentence description of each.

The four pillars of OOP are inheritance, polymorphism, encapsulation and abstraction.

- **Inheritance**: It is the ability to create a class (sub class) from existing class (super class) where the sub class inherits all properties of the super class.
- **Polymorphism**: It is the ability of an object to take on multiple forms.
- **Encapsulation**: It is the process of hiding the attributes inside a class to prevent unauthorised access to them.
- **Abstraction**: It is the process of showing only the essential functionality to the user and hiding implementation details.



#### 5. What is the strategy pattern? How would its implementation differ between a functional and object oriented system?

> A **strategy pattern** is a behavioral design pattern that allows dynamically switching the behavior of an object at runtime. The strategy pattern allows family of algorithms or behaviors to be encapsulated into separate classes called strategies.

In object oriented implementation of strategy pattern the strategy is implemented as an interface and the family of algorithms and behaviors are encapsulated within the concrete implementations of the interface. With the strategy pattern, we are abiding by the Open/Closed principle, one of the SOLID principles, as new strategies can be added without without modifying existing code.

In functional oriented implementation of strategy pattern, a strategy could be implemented as a higher order function, or even a closure, which can then return other functions or take functions as arguments.


#### 6. Imagine your team is creating a new online payment system. In order to gain maximum market share it can't be tied to a particular sector - it needs to work just as well when ordering a takeaway as when buying a new coat. Which design methodology would you suggest following? Give some justification for your decision.

I would suggest using object oriented design approach for designing the new online payment system. This is due to following reasons:

- Debugging is easier when components are loosely coupled.
- By using encapsulation we can provide better data security.
- Improves code reusability across different parts of application.
- Ability to extend without modification makes application easy to scale.

To make the payment system generic that is compatible with many different sector, we can implement strategy pattern by creating a delegator class and strategies interface. For every new sector, we would only have to add new strategy concrete implementation with specific algorithms, attributes and behaviors.

The class diagram of such application could include following classes (to name a few): 

- **`Customer`**: Represents users of the system. Attributes are encapsulated for security, and getters and setters are provided only for non-sensitive information such as `user_id`. We could implement an interface for account, which provides common datatype to handle other user types, such as admins.
- **`<<Interface>> ISector`**: Enables polymorphism where many specific sector can have a type called ISector. This enables us to use same methods to process payments for various sectors.
- **`<<Payment>>`**: Is an abstract class that allows inheritance for multiple forms of payments, such as credit cards, debit cards, apple pay, pay pal. This class could provide methods to authenticate and receive payments from customers. All the methods contained in this class should follow single responsibility principle.


# Software Design Methodologies

### 1. What do we mean by coupling and cohesion when discussing structured design?

**Coupling** and **cohesion** are tools of structured design that are used to measure the quality of a software system's design. 

> **Coupling** is the degree of interdependence between various modules.

When classes and modules are highly coupled, it is difficult to change and maintain the software code because making a small change to one piece code could mean we also need to change other components and sub-components that depend on it. In a low coupling scenario, the classes exist independently, so changing something major in one class will not affect other classes.
Low coupling helps improve maintainability, allows reusability of code, and facilitates the scalability of the software.


> **Cohesion** is the degree to which the elements within a module are functionally related.

High cohesion implies that the elements within a class are focused on achieving the class's purpose. Whereas, low cohesion means the elements within a class serve multiple purposes and deviate from class's purpose. High cohesion helps improve readability, allows better exception handling, and increases the reliability of the system.

A good software design has high cohesion and low coupling.


#### 2. What is the difference between top-down and bottom-up design? Which best describes a function oriented design?

> The **top-down design** approach focuses on the formulation of the whole system without giving specific details of the components at the start. The bigger problem is then broken down into smaller problems with more details.

- Top-down design is based on a decomposition approach.
- Top-down design may cause scalability issues as there is high coupling between the components.


> The **bottom-up design** approach focuses on identifying and defining individual components of the system and then integrating them together to build bigger components. 

- Bottom-up design is based on a composition approach.
- Bottom-up design facilitates scalability as it allows component reusability and reduces data redundancy.


Function oriented design starts as a high-level requirement, which is then refined to specific details to solve the problem. 

Function oriented design is best described by top-down design.


#### 3. In which design methodology would a class diagram be most useful?

A class diagram is a visualisation of classes and their relationships. It includes class name, attributes, methods and access modifiers.

Class diagram is most useful for object oriented design because a class defines blueprint for creating objects, and each class defines set of attributes and object's behaviours.


#### 4. What are the four pillars of object oriented programming? Give a single-sentence description of each.

The four pillars of OOP are inheritance, polymorphism, encapsulation, and abstraction.

- **Inheritance** is the ability to create a class (sub-class) from an existing class (super-class) where the sub-class inherits all properties of the super-class.
- **Polymorphism** is the ability of an object to take on multiple forms.
- **Encapsulation** is the process of hiding the attributes inside a class to prevent unauthorised access to them.
- **Abstraction** is the process of showing only the essential functionality to the user and hiding implementation details.



#### 5. What is the strategy pattern? How would its implementation differ between a functional and object oriented system?

> A **strategy pattern** is a behavioral design pattern that allows dynamically switching the behavior of an object at runtime. The strategy pattern allows a family of algorithms or behaviors to be encapsulated into separate classes called strategies.

In the object oriented implementation of strategy pattern, the strategy is implemented as an interface and the family of algorithms and behaviors is encapsulated within the concrete implementations of the interface. With the strategy pattern, we are abiding by the open/closed principle, one of the SOLID principles, as new strategies can be added without modifying existing code.

In functional oriented implementation of strategy pattern, a strategy could be implemented as a higher-order function or even a closure, which can then return other functions or take functions as arguments.


#### 6. Imagine your team is creating a new online payment system. In order to gain maximum market share it can't be tied to a particular sector - it needs to work just as well when ordering a takeaway as when buying a new coat. Which design methodology would you suggest following? Give some justification for your decision.

I would suggest using an object oriented design approach for designing the new online payment system. This is due to the following reasons:

- Debugging is easier when components are loosely coupled.
- By using encapsulation, we can provide better data security.
- Improves code reusability across different parts of the application.
- The ability to extend without modification makes the application easy to scale.

To make the payment system generic and compatible with many different sectors, we can implement a strategy pattern by creating a delegator class and a strategy interface. For every new sector, we would only have to add a new strategy for concrete implementation with specific algorithms, attributes, and behaviors.

The class diagram of such an application could include the following classes (to name a few): 

- **`Customer`**: represents users of the system. Attributes are encapsulated for security, and getters and setters are provided only for non-sensitive information such as `user_id`. We could implement an interface for accounts that provides a common datatype to handle other user types, such as admins.
- **`<<Interface>> ISector`**: enables polymorphism, where many specific sectors can have a type called ISector. This enables us to use the same methods to process payments for various sectors.
- **`<<Payment>>`**: is an abstract class that allows inheritance for multiple forms of payments, such as credit cards, debit cards, Apple Pay, and PayPal. This class could provide methods to authenticate and receive payments from customers. All the methods contained in this class should follow the single-responsibility principle.


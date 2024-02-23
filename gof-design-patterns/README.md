---
description: Gang of Four
---

# GoF Design Patterns

### What is a Design Pattern?

A design pattern is a general, reusable solution to a commonly occurring problem within a given context in software design. It is not a finished design that can be transformed directly into source or machine code. Rather, it is a template for how to solve a problem that can be used in many different situations. Design patterns are about reusable designs and interactions of objects.

### Types of Design Patterns

Design patterns are categorized into three main types:

#### 1. Creational Patterns

Creational patterns are all about class instantiation or object creation. They can be further divided into class-creation patterns and object-creational patterns.

* **Singleton**: Ensures a class has only one instance and provides a global point of access to it.
* **Factory Method**: Defines an interface for creating an object, but lets subclasses alter the type of objects that will be created.
* **Abstract Factory**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
* **Builder**: Separates the construction of a complex object from its representation, allowing the same construction process to create various representations.
* **Prototype**: Creates new objects by copying an existing object, known as the prototype.

#### 2. Structural Patterns

Structural patterns are concerned with how classes and objects are composed to form larger structures. They help ensure that if one part of a system changes, the entire system doesn't need to do the same.

* **Adapter (or Wrapper)**: Allows objects with incompatible interfaces to collaborate.
* **Bridge**: Separates an object’s abstraction from its implementation so that the two can vary independently.
* **Composite**: Composes objects into tree structures to represent part-whole hierarchies.
* **Decorator**: Attaches new behaviors to objects by placing them inside special wrapper objects that contain the behaviors.
* **Facade**: Provides a simplified interface to a complex subsystem.
* **Flyweight**: Reduces the cost of creating and manipulating a large number of similar objects.
* **Proxy**: Provides a placeholder for another object to control access to it.

#### 3. Behavioral Patterns

Behavioral patterns are about identifying common communication patterns between objects and realize these patterns. By doing so, these patterns increase flexibility in carrying out communication.

* **Chain of Responsibility**: Passes the request along a chain of potential handlers until one of them handles the request.
* **Command**: Turns a request into a stand-alone object that contains all information about the request.
* **Interpreter**: Implements a specialized language.
* **Iterator**: Provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.
* **Mediator**: Reduces chaos between interrelated objects by defining an object that encapsulates how these objects interact.
* **Memento**: Captures and externalizes an object's internal state so that the object can be restored to this state later.
* **Observer**: Lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.
* **State**: Allows an object to alter its behavior when its internal state changes.
* **Strategy**: Lets you define a family of algorithms, encapsulate each one, and make them interchangeable.
* **Template Method**: Defines the skeleton of an algorithm in the superclass but lets subclasses override specific steps of the algorithm without changing its structure.
* **Visitor**: Lets you separate algorithms from the objects on which they operate.

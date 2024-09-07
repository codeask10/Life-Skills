# Technical Paper: SOLID Principles

## Introduction
SOLID are first five object-oriented design (OOD) principles by Robert C. Martin (also known as Uncle Bob) which help to create good software architecture. SOLID are design that help to create more understandable, flexible, and maintainable code.

SOLID stands for:

- **S** - Single-responsibility Principle
- **O** - Open-closed Principle
- **L** - Liskov Substitution Principle
- **I** - Interface Segregation Principle
- **D** - Dependency Inversion Principle

### 1. Single Responsibility Principle (SRP)

Single-responsibility Principle (SRP) states that A class should have one and only one reason to change, meaning that a class should have only one job.

Example:
```bash 
class Report {
    String content;

    Void generateReport(){
        // report generation logic
    }

    void saveToFile(){
        save to file logic
    }
}
```
In this example, the ‘Report’ class has two responsibilities: generating a report and saving it to a file. A better approach is to have separate classes for report generation and file saving.

### 2. Open/Closed Principle (OCP)

Open-closed Principle (OCP) states that bjects or entities should be open for extension but closed for modification. This means that a class should be extendable without modifying the class itself.

Example:
```bash 
class Rectangle {
    int width;
    int height;
}
    
class AreaCalculator{
    double calculateArea(Reactangle rectangle){
        return rectangle.width*rectangle.height;
    }
}
```
To adhere to the OCP, we can introduce an abstraction for shapes and extend the ‘AreaCalculator’ for different shapes without modifying its existing code.

### 3. Liskov Substitution Principle (LCP)
 Liskov Substitution Principle (LCP) states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.

 In simpler terms, if a class is a subclass of another, it should behave in a way that is indistinguishable from the superclass.

Example:
```bash 
class Bird {
    void fly(){
        // fly logic
    }
}
    
class Penguin extends Bird{
    // Penguins can\'t fly 

    void fly(){
        throw new UnsupportedOperationException(" Penguins can't fly, so this method should be reconsidered");
    }
}
```
In this example, the ‘Penguin’ class violates the LSP because it doesn’t behave like its superclass. A better approach might be to remove the ‘fly’ method from the ‘Bird’ superclass and create a separate ‘FlyingBird’ interface for birds that can fly.

### 4. Interface Segregation Principle (ISP)

The Interface Segregation Principle suggests that a class should not be forced to implement interfaces it does not use. It’s better to have several small, specific interfaces rather than a large, all-encompassing one.

Example:
```bash 
//Bad design
interface Worker {
    void work();
    void eat();
}
// Better design

interface Workable{
    void work();
}

interface Eatable{
    void eat();
}
```
In the improved design, classes can implement only the interfaces that are relevant to them, avoiding the need to implement unnecessary methods.

### 5. Dependency Inversion Principle (DIP)

The Dependency Inversion Principle states that high-level modules should not depend on low-level modules, but both should depend on abstractions. Additionally, abstractions should not depend on details; details should depend on abstractions.

Example:
```bash 
// without DIP
Class LightBulb{
    void turnOn(){
        //turn on logic
    }
}

class Switch {
    LightBulb bulb = new LightBulb();

    void operate(){
        bulb.turnOn();
    }
}
```
In this example, ‘Switch’ is tightly coupled to ‘LightBulb.’ With DIP, we can introduce an interface for devices and have ‘Switch’ depend on the abstraction.

## Risks of Ignoring SOLID Principles

If we don't follow the SOLID Principles, we:

- End up with tight or strong coupling of the code with many other modules/applications.
- End up with a code which is not testable.
- End up with duplication of code.
- End up creating new bugs by fixing another bug.
- End up with many unknown issues in the application development cycle.


## SOLID Principles

Following SOLID Principles helps us to:

* Achieve reduction in complexity of code

* Increase readability, extensibility and maintenance

* Reduce error and implement Reusability

* Achieve Better testability

* Reduce tight coupling


## Conclusion

This article introduced the five principles of the SOLID Code. Projects that adhere to these principles can be shared with collaborators, extended, modified, tested, and refactored with fewer complications.

## References

 [Digital Ocean](https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#single-responsibility-principle)

[Medium.com/SOLID]( https://medium.com/@GetInRhythm/mastering-solid-principles-a-comprehensive-guide-for-software-engineers-da53b054c9e1)

[Review Paper on SOLID](https://www.researchgate.net/publication/273451390_SOLID_Principles_in_Software_Architecture_and_Introduction_to_RESM_Concept_in_OOP)





# OOP JS
- JavaScript is not a class-based object-oriented language. But it still has ways of using object oriented programming (OOP).

## OOP

- Abstraction. Abstraction means using simple things to represent complexity. We all know how to turn the TV on, but we don’t need to know how it works in order to enjoy it. In Java, abstraction means simple things like objects, classes, and variables represent more complex underlying code and data. This is important because it lets avoid repeating the same work multiple times.
- Encapsulation. This is the practice of keeping fields within a class private, then providing access to them via public methods. It’s a protective barrier that keeps the data and code safe within the class itself. This way, we can re-use objects like code components or variables without allowing open access to the data system-wide.
- Inheritance. This is a special feature of Object Oriented Programming in Java. It lets programmers create new classes that share some of the attributes of existing classes. This lets us build on previous work without reinventing the wheel.
- Polymorphism. This Java OOP concept lets programmers use the same word to mean different things in different contexts. One form of polymorphism in Java is method overloading. That’s when different meanings are implied by the code itself. The other form is method overriding. That’s when the different meanings are implied by the values of the supplied variables. See more on this below.

### What is class?
- Collection of objects is called class. It is a logical entity.
- A class can also be defined as a blueprint from which you can create an individual object. Class doesn't consume any space.

### What is interface?
- An interface in Java is a blueprint of a class. It has static constants and abstract methods.

### What is static class?
- Can not be created in JS. But in JAVA we can create a nested class static.

### What is static methods?
- Methods those are defined as static can only be accessed by the class name. Can not be accessed by instances.

### What is access specifier?
- Access modifiers are keywords used to specify the declared accessibility of a member or a type.
  1. Private – Access is limited.
  2. Public – Can be access from anywhere, access is not restricted.
  3. Privileged/Protected – Access is limited to the containing class or types derived from the containing class.

### What is super?
- Calls constructor of parent class.
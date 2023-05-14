    #Java Basics (2)#

## The process of modelling

:question: **1. What is the process of modelling? Describe the steps involved.**

* The process of modelling means to create a model/representation for the structure, behaviour and interaction of a system. In order to create a model, we need to:
- consider the purpose of the system and the needs of the end-users;
- take a good look at the relevant attributes of the object in question to develop the system;
- develop a conceptual model of the system (think about the components and their interaction);
- develop a design model (detailed view of the system: data structures, classes, algorithms);
- implement the code;
- test the code;
- refactor the code, refine the model;
- write documentation that explains the system.

---
:question: **2. Which data type would you use to represent a fixed set of distinct values?**

* In Java, the data type used to represent a fixed set of distinct values is an `enum` (short for enumeration).

---
:question: **3. What is the difference between a class and an object? How do they relate to each other?**

* A class is a blueprint/ template that defines properties and behaviour of an object (data, methods, general concept).
* An object is an instance of a class (concrete realization of the class).

:black_nib: Example for class:
```
public class Car {
    private String make;
    private String model;
    private int year;

    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    public void drive() {
        System.out.println("The " + year + " " + make + " " + model + " is driving.");
    }
}
```

:black_nib: Example for object:

```
Car myCar = new Car("Toyota", "Camry", 2022);
```

---
:question: **4. What are getter and setter methods in Java?**

* The getter (accessor) and setter (mutator) methods in Java are used to access (get) and modify (set) the values of an instance variable in a class.

:black_nib: Example of accessor (getter):

```
public class Person {
    private String name;

    public String getName() {
        return name;
    }
}
```

:black_nib: Example of mutator (setter):

```
public class Person {
    private String name;

    public void setName(String newName) {
        name = newName;
    }
}
```

---
:question: **5. What is a constructor? Describe the different variants.**

* In Java, a Constructor is a special method, with the same name of the containing class, used to create/ initiate/ instantiate (variables of) an object.
* A Constructor is called when we create an object using "new" keyword.
* There are 2 main constructors: default Constructor (without parameters) and parameterized Constructor (with parameters).

---
:question: **6. What is the difference between mutable and immutable objects? Which one is usually preferred for model classes and why?**

* Mutable objects can be modified after they were created, whereas immutable objects cannot be modified following their creation.
* Usually, immutable objects are preferred because: they are more predictable, less vulnerable to security attacks, more efficient (can be reused), easier to use and maintain.

---
:question: **7. How can you implement a mutable model class?**

:black_nib: To implement a mutable model class in Java, we need to: 
- define the instance variables;
- define the constructor(s);
- implement getter(s) and setter(s).

---
:question: **8. How can you implement an immutable model class?**
:black_nib: To implement a immutable model class in Java, we need to:
- declare the instance variables (and set them with the `final` non-access modifier);
- define the constructor(s);
- implement getter(s).

---
:question: **9. What is the default value for objects?**

* In Java, the default value for an object reference is `null`.

---
___

##Object identity

:question: **10. What is the primary mechanism to create class hierarchies in OOP languages? How does it work?**

* The primary mechanism to create class hierarchies in OOP is inheritance (a mechanism by which a class can be derived from another).
* According to Codecool, `the class which inherits is called a subclass, derived class, or child class and the class from which we are inheriting is called the superclass, base class or parent class`.
* The derived class uses the keyword `extends`.

:black_nib: Example:

```
public class Animal {
    public void eat() {
        System.out.println("The animal is eating.");
    }
}

public class Dog extends Animal {
    public void bark() {
        System.out.println("The dog is barking.");
    }
}
```

```
Dog myDog = new Dog();
myDog.eat(); // Output: The animal is eating.
myDog.bark(); // Output: The dog is barking.

```

---
:question: **11. What is the base class for all other classes in Java? Describe some of its methods.**

:black_nib: The base class for all classes in Java is the `Object` class. Here are some of its methods:

- getClass(): Returns the Class object that represents the runtime class of the object.
- hashCode(): Returns a hash code for the object.
- equals(): Boolean indicates whether some an object is "equal to" another.
- clone(): Creates and returns a copy of the object
- toString(): Returns a string representation of the object.
- notify()
- notifyAll()
- wait()
- finalize()

---
:question: **12. Are private members available in subclasses?**

* Private members are not available in subclasses. Only public and protected members are available in subclasses.

---
:question: **13. Is multiple inheritance allowed in Java?**

* Multiple inheritance for classes (the ability of a class to inherit properties from more than another class) is not supported by Java, but multiple inheritance for interfaces is supported by Java.

---
___

## Memory management in Java

:question: **14. What are the two types of memory a Java program uses?**

:black_nib: A Java program uses 2 main types of memory and a special one:
- Stack Memory: for variables/ is used for static memory allocation and the execution of a thread
- Heap Memory: for objects/  is used for the dynamic memory allocation of Java objects and JRE classes at runtime
- PermGen/ Metaspace: for metadata

---
___

## Equality overriding

:question: **15. What is value-based equality in Java? How can you achieve it?

* The value-based equality in Java compares to see if the values of the objects fields, rather then their memory address (reference), are equals.
* In order to achieve value-based equality in Java, we need to override the `equals()` and `hashCode()` methods in a class.

---
:question: **16. What is the Object.hashCode method used for?

* The `Object.hashCode()` is a method used to return a hash code value for an object (an integer value used to improve performance).

---
___

## ToString overriding

:question: **17. How to print a human-readable text representation of an object?**

* To create a human-readable text representation of an object in Java we use `toString()`.

---
___

## Generating

:question: **18. How can you get an array with the values of an enum?**

* In Java, you can get an array with the values of an enum using the `values()` method.

---

:question: **19. What is a nested loop?**

* A nested loop is placed inside another loop.

---

:question: **20. What does the index refer to when dealing with arrays or lists?**

* The index (integer value that starts from 0) refers to the position of an element in an array or a list.
* The index goes up to the size of the array or the list minus 1.

---
___

## Improving readability

:question: **21. What is the primary method of making a piece of code more readable?

:black_nib: Tips to improve readability of the code:
- use descriptive names
- separate logical sections using whitespaces
- use indentation
- break up complex code into smaller pieces
- use comments to explain the code
- follow the standards and best practices

---
___

## Adding

:question: **22. Share your thoughts about simplicity vs robustness.

* Usually, we should prioritize simplicity over robustness, but there are times when it is better to pay more attention to robustness or find a better balance between simplicity and robustness.

---
___

## Creating the desk class

:question: **23. What do we mean by the state of an object?**

* The state of an object refers to a collection of values that define the object's properties at a particular moment.


---

:question: **24. Is it true that immutable objects have no state?**

* No, it is not true that immutable objects have no state.
* All objects in Java have a state.

---

:question: **25. What do we mean by an object's behaviour?**

* An object's behaviour describes actions that an object can perform or methods that an object can execute.

---

:question: **26. What are private instance variables used for?**

* Private instance variables encapsulate the state of an object and restrict direct access to it from outside the class.


---

:question: **27. What is the Optional class?**

* The main purpose of the Optional class is to provide a better alternative to returning null in methods that may or may not return a value.

---
___




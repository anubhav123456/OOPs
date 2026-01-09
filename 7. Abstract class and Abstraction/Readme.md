# Java Abstraction

## What is Abstraction?

Abstraction is an important concept of **Object-Oriented Programming (OOP)** that allows us to **hide unnecessary implementation details** and show **only the essential features** of an object.

It helps in:

* Reducing complexity
* Improving code readability
* Focusing on *what an object does* instead of *how it does it*

In Java, abstraction is mainly achieved using:

* **Abstract classes**
* **Interfaces**

---

## Abstract Class in Java

An **abstract class** is a class that:

* Cannot be instantiated (we cannot create objects of it)
* Can contain **abstract methods** (methods without a body)
* Can also contain **non-abstract (concrete) methods**

We use the `abstract` keyword to declare an abstract class.

### Key Rules of Abstract Classes

* Abstract classes **cannot be instantiated**
* They can have **both abstract and non-abstract methods**
* Abstract methods **do not have a body**
* If a class has **at least one abstract method**, the class **must be abstract**
* Subclasses **must implement all abstract methods** of the parent class (unless the subclass is also abstract)

---

## Example: Abstract Class with Abstract Methods

```java
abstract class Vehicle
{
    abstract void accelerate();
    abstract int brakes(int wheels);
    
    public void honks()
    {
        System.out.println("Vehicle Honks");
    }
}
```

Here:

* `Vehicle` is an abstract class
* `accelerate()` and `brakes()` are abstract methods
* `honks()` is a concrete (non-abstract) method

---

## Creating a Concrete Class from an Abstract Class

A **concrete class** must provide implementations for all abstract methods.

```java
class Car extends Vehicle
{
    @Override
    void accelerate()
    {
        System.out.println("Car is Accelerating");
    }

    @Override
    int brakes(int wheels)
    {
        System.out.println("Car breaks are pushed");
        return wheels;
    }
}
```

---

## Using the Subclass Object

Although we cannot create an object of `Vehicle`, we **can create an object of `Car`**, which is a subclass of `Vehicle`.

```java
public class Main
{
    public static void main(String[] args)
    {
        Car c1 = new Car();

        c1.accelerate();
        System.out.println(String.format("Number of wheels : %d", c1.brakes(4)));
        c1.honks();
    }
}
```

### Output

* Car is Accelerating
* Car breaks are pushed
* Number of wheels : 4
* Vehicle Honks

---

## Overriding Non-Abstract Methods

Abstract classes can also have **concrete methods**, and subclasses are allowed to **override them**.

### Example: Overriding `honks()` Method

```java
abstract class Vehicle
{
    abstract void accelerate();
    abstract int brakes(int wheels);
    
    public void honks()
    {
        System.out.println("Vehicle Honks");
    }
}

class Car extends Vehicle
{
    @Override
    void accelerate()
    {
        System.out.println("Car is Accelerating");
    }

    @Override
    int brakes(int wheels)
    {
        System.out.println("Car breaks are pushed");
        return wheels;
    }

    @Override
    public void honks()
    {
        System.out.println("Car Honks");
    }
}
```

```java
public class Main
{
    public static void main(String[] args)
    {
        Car c1 = new Car();

        c1.accelerate();
        System.out.println(String.format("Number of wheels : %d", c1.brakes(4)));
        c1.honks();
    }
}
```

### Output

* Car is Accelerating
* Car breaks are pushed
* Number of wheels : 4
* Car Honks

---

## Rule: Abstract Method Requires Abstract Class

If a class contains **any abstract method**, then the class **must be declared abstract**.

### ❌ Invalid Code (Compilation Error)

```java
class Human
{
    abstract void sleep();
}
```

### ✅ Correct Code

```java
abstract class Human
{
    abstract void sleep();
}
```

---

## Summary

* Abstraction hides implementation details
* Abstract classes cannot be instantiated
* Abstract methods have no body
* Subclasses must implement abstract methods
* Abstract classes can have concrete methods
* Concrete methods **can be overridden**
* Any class with an abstract method must be abstract

---

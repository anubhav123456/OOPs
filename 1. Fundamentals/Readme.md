
---

## Object-Oriented Programming System

**OOPs** is a programming paradigm in which a program is designed around **objects** rather than just functions and logic.

In OOPS:

* Everything is modeled around **objects**
* Real-world problems are broken down into **real-world entities**
* Each entity is represented as an **object**
* Focus is on **data + behavior together**, not separately

👉 Java is a **pure object-oriented language** (almost everything is an object).

---

## Real-World Entity → Object

Any **real-world entity** can be represented as an **object** if it has:

1. **Properties (State)**
2. **Behavior (Functionality)**

### 1. Properties (State)

Properties describe the **characteristics** of an object.
They are represented using **variables**.

**Examples:**

* **Dog** → color, age, breed
* **Car** → color, brand, type
* **Student** → name, rollNumber, marks

---

### 2. Behavior (Functionality)

Behavior represents the **actions** performed by an object.
They are represented using **methods (functions)**.

**Examples:**

* **Dog** → `bark()`, `sleep()`, `eat()`
* **Car** → `drive()`, `applyBrake()`, `accelerate()`
* **ATM** → `withdraw()`, `checkBalance()`

👉 **If something has both properties and behavior, it can be modeled as an object.**

---

## Class and Object in Java

### Class

* A **class** is a **blueprint / template**
* It defines:

  * What **data (variables)** an object will have
  * What **behavior (methods)** an object will perform
* No memory is allocated when a class is created

### Object

* An **object** is a **real-world entity**
* Created from a class
* Has:

  * **State** → variables
  * **Behavior** → methods
* Memory is allocated when an object is created

👉 From **one class**, **multiple objects** can be created.

---

### Example in Java

```java
class Dog {
    // Properties (State)
    String color;
    int age;
    String breed;

    // Behavior (Functionality)
    void bark() {
        System.out.println("Dog is barking");
    }

    void eat() {
        System.out.println("Dog is eating");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog();  // Object creation
        dog1.color = "Brown";
        dog1.age = 3;
        dog1.breed = "Labrador";

        dog1.bark();
        dog1.eat();
    }
}
```

---

## Why OOPS is Important in Java?

OOPS helps in:

* **Code reusability**
* **Better maintainability**
* **Real-world problem modeling**
* **Scalability**
* **Security**

---

## Four Pillars of OOPS in Java

Java OOPS is built on four main principles:

1. **Encapsulation** – Binding data and methods together
2. **Inheritance** – One class acquiring properties of another
3. **Polymorphism** – One method behaving in different ways
4. **Abstraction** – Hiding implementation details

---

## Simple One-Line Summary

> **OOPS in Java models real-world entities as objects that contain both data (properties) and behavior (methods), making programs more organized, reusable, and scalable.**

---

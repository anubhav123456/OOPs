
---

# 🔷 Inheritance

## 📌 What is Inheritance?

**Inheritance** is an **OOP mechanism** where one class (**child/subclass**) acquires the **properties (variables)** and **behaviors (methods)** of another class (**parent/superclass**).

👉 Achieved using the `extends` keyword.

```java
class Child extends Parent {
}
```

---

## 📌 Why Inheritance?

✔ Code reusability
✔ Eliminates redundancy
✔ Enables **polymorphism**
✔ Better maintainability
✔ Logical hierarchy (IS-A relationship)

Example:

> Car **IS-A** Vehicle
> Dog **IS-A** Animal

---

## 📌 Basic Example of Inheritance

```java
class Vehicle {
    int speed = 60;

    void run() {
        System.out.println("Vehicle is running");
    }
}

class Car extends Vehicle {
    void show() {
        System.out.println("Car speed: " + speed);
    }
}

public class Main {
    public static void main(String[] args) {
        Car c = new Car();
        c.run();     // inherited method
        c.show();
    }
}
```

✔ `Car` inherits `speed` and `run()`
✔ No duplicate code

---

## 📌 Important Rules of Inheritance

### 🔹 Rule 1: Child can access parent members

```java
class Parent {
    int x = 10;
}

class Child extends Parent {
    void print() {
        System.out.println(x);
    }
}
```

---

### 🔹 Rule 2: Parent cannot access child members

```java
class Parent {
}

class Child extends Parent {
    int y = 20;
}

public class Main {
    public static void main(String[] args) {
        Parent p = new Parent();
        // p.y ❌ NOT allowed
    }
}
```

---

### 🔹 Rule 3: Parent reference can hold child object (Upcasting)

```java
Parent p = new Child();
```

But parent reference:
❌ cannot access child-specific members
✔ can access overridden methods (runtime polymorphism)

---

## 📌 Types of Inheritance in Java

---

## 1️⃣ Single Inheritance

**One parent → one child**

```java
class Animal {
    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();
        d.bark();
    }
}
```

✔ Simple
✔ Most commonly used

---

## 2️⃣ Multilevel Inheritance

**Parent → Child → Grandchild**

```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

class Puppy extends Dog {
    void weep() {
        System.out.println("Weeping...");
    }
}

public class Main {
    public static void main(String[] args) {
        Puppy p = new Puppy();
        p.eat();
        p.bark();
        p.weep();
    }
}
```

✔ Chain of inheritance

---

## 3️⃣ Hierarchical Inheritance

**One parent → multiple children**

```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void meow() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        Cat c = new Cat();

        d.eat();
        c.eat();
    }
}
```

✔ Parent behavior shared across multiple classes

---

## ❌ Multiple Inheritance with Classes (NOT Allowed)

```java
class A {
    void getEngine() {}
}

class B {
    void getEngine() {}
}

// class C extends A, B {} ❌ Compile-time error
```

### ❓ Why Not Allowed?

```java
C obj = new C();
obj.getEngine(); // Which one? A or B?
```

➡ **Ambiguity problem**
Java avoids this at **compile time**.

---

## ✅ Solution: Multiple Inheritance using Interfaces

---

## 📌 Why Interface Works?

✔ Interfaces contain **only method declarations**
✔ No implementation conflict
✔ Child **must override** methods
✔ Removes ambiguity

---

## ✔ Multiple Inheritance via Interface

```java
interface A {
    void getEngine();
}

interface B {
    void getEngine();
}

class C implements A, B {
    public void getEngine() {
        System.out.println("Engine from C");
    }
}

public class Main {
    public static void main(String[] args) {
        C obj = new C();
        obj.getEngine();
    }
}
```

* ✔ No ambiguity
* ✔ Mandatory override


---

## 📌 Advantages of Inheritance

✔ Code reusability
✔ Cleaner code
✔ Easier maintenance
✔ Supports polymorphism
✔ Logical class hierarchy

---

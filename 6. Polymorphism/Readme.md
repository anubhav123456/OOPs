

---

## What is Polymorphism?

**Polymorphism** means **“many forms”**.

In Java, it allows:

* **Same method name**
* **Different behavior**
* Based on **context (object type / parameters)**

👉 One interface, multiple implementations.

### Simple definition (interview-ready)

> Polymorphism is the ability of an object to take many forms, where the same method behaves differently based on the object or parameters involved.

---

## Types of Polymorphism in Java

Java supports **two types**:

| Type                          | Decided At   | How                             |
| ----------------------------- | ------------ | ------------------------------- |
| **Compile-Time Polymorphism** | Compile time | Method Overloading              |
| **Runtime Polymorphism**      | Runtime      | Method Overriding + Inheritance |

---

# 1️⃣ Compile-Time Polymorphism (Method Overloading)

### What is it?

When **multiple methods have the same name** but **different parameters**, and the decision of **which method to call** is made **at compile time**.

### Key Points

* Same method name
* Different **parameter list**
* Happens **within the same class**
* Return type alone is **NOT enough**

---

## Example: Compile-Time Polymorphism

Let’s extend your example slightly 👇

```java
class Animal
{
    protected int age;

    public Animal(int age)
    {
        this.age = age;
    }

    // Overloaded methods (Compile-time polymorphism)
    void eat()
    {
        System.out.println("Animal is eating");
    }

    void eat(String food)
    {
        System.out.println("Animal is eating " + food);
    }

    void eat(String food, int quantity)
    {
        System.out.println("Animal is eating " + quantity + " units of " + food);
    }
}
```

### Usage

```java
public class Main
{
    public static void main(String[] args)
    {
        Animal animal = new Animal(5);

        animal.eat();                     // calls eat()
        animal.eat("Meat");               // calls eat(String)
        animal.eat("Meat", 2);            // calls eat(String, int)
    }
}
```

### Why is this Compile-Time Polymorphism?

* Method call is resolved **based on arguments**
* Compiler already knows which method to call
* No runtime decision needed

📌 **Also called:** *Static Polymorphism*

---

# 2️⃣ Runtime Polymorphism (Method Overriding)

Now let’s come to **your main code** 🔥

### What is it?

When:

* A **parent reference**
* Points to a **child object**
* And the **child overrides a method**

The decision of which method to call happens **at runtime**.

---

## Your Given Code (Runtime Polymorphism)

```java
class Animal
{
    protected int age;

    public Animal(int age)
    {
        this.age = age;
    }

    void eat()
    {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal
{
    public Dog(String color, int age, String breed)
    {
        super(age);
    }

    @Override
    void eat()
    {
        System.out.println("Dog is eating");
    }
}
```

### Main Method

```java
public class Main
{
    public static void main(String[] args)
    {
        Animal dog = new Dog("Brown", 3, "Labrador");

        dog.eat();   // Runtime polymorphism
    }
}
```

### Output

```
Dog is eating
```

---

## Why is this Runtime Polymorphism?

Let’s analyze 👇

```java
Animal dog = new Dog(...);
```

* **Reference type** → `Animal`
* **Object type** → `Dog`

At **compile time**:

* Compiler checks → `Animal` has `eat()` ✅

At **runtime**:

* JVM checks → actual object is `Dog`
* `Dog` has overridden `eat()`
* JVM calls `Dog.eat()`

📌 This is called **Dynamic Method Dispatch**

---

## Important Rule (Interview Gold ⭐)

> **Runtime polymorphism works only for overridden methods, not variables.**

### Example

```java
class Animal {
    int speed = 10;
}

class Dog extends Animal {
    int speed = 20;
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();
        System.out.println(a.speed);
    }
}
```

### Output

```
10
```

👉 Variables are **not polymorphic**, methods are.

---

## Your `toString()` Example (Also Runtime Polymorphism)

From your code:

```java
@Override
public String toString()
{
    return String.format(
        "%s{ color : %s, age : %d, breed : %s }",
        "Dog", color, age, breed
    );
}
```

### Usage

```java
Animal dog = new Dog("Brown", 3, "Labrador");
System.out.println(dog);
```

### Output

```
Dog{ color : Brown, age : 3, breed : Labrador }
```

📌 Even though reference is `Animal`, **Dog’s `toString()` is called** → runtime polymorphism.

---

## Compile-Time vs Runtime Polymorphism (Comparison)

| Feature              | Compile-Time        | Runtime              |
| -------------------- | ------------------- | -------------------- |
| Also Called          | Static Polymorphism | Dynamic Polymorphism |
| Achieved By          | Method Overloading  | Method Overriding    |
| Binding Time         | Compile time        | Runtime              |
| Inheritance Required | ❌ No                | ✅ Yes                |
| Method Resolution    | Based on parameters | Based on object type |
| Performance          | Faster              | Slightly slower      |

---

## Real-World Analogy 🧠

### Compile-Time

> You order **coffee** and choose size while ordering
> 👉 Decision made **before execution**

### Runtime

> You call **customer care**, and the person responding depends on **who picks up**
> 👉 Decision made **at runtime**

---

## Interview One-Liner Summary

* **Compile-time polymorphism** → method overloading, resolved at compile time
* **Runtime polymorphism** → method overriding, resolved at runtime using inheritance
* **Achieved using parent reference and child object**

---

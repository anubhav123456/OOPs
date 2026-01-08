
---

## What is Upcasting?

**Upcasting** means:

> Treating a **child class object** as a **parent class reference**

✔️ It is **implicit** (no cast needed)
✔️ It is **safe**
✔️ It supports **runtime polymorphism**

---

## Class Relationship in Your Code

```java
Animal  <-- parent (superclass)
   |
   |
Dog     <-- child (subclass)
```

`Dog` **IS-A** `Animal`, so Java allows upcasting.

---

## Normal Object Creation (No Upcasting)

```java
Dog dog = new Dog("Brown", 3, "Labrador");
```

Here:

* Reference type → `Dog`
* Object type → `Dog`
* You can access:

  * Dog methods (`bark`)
  * Animal methods (`eat`)
  * Dog + Animal properties

---

## Upcasting Example (Using Your Code)

```java
Animal animal = new Dog("Brown", 3, "Labrador");
```

This is **UPCASTING**.

### What happened here?

| Reference Type | Object Type |
| -------------- | ----------- |
| `Animal`       | `Dog`       |

* ✔️ A **Dog object** is stored
* ✔️ It is **referenced as Animal**

---

## What Can Be Accessed After Upcasting?

```java
animal.eat();   // ✅ Allowed (Animal method)
animal.getAge(); // ✅ Allowed (Animal method)

// animal.bark(); ❌ NOT allowed
```

### Why `bark()` is NOT accessible?

Because:

* Reference type is `Animal`
* `Animal` does **not** have `bark()`

> **Access is decided at compile time by reference type**

---

## Visual Understanding

```java
Animal animal = new Dog("Brown", 3, "Labrador");
```

```
animal ──▶ Dog object in heap
           ├── color
           ├── age
           ├── breed
           ├── bark()
           └── eat()
```

But **reference only sees Animal part**.

---

## Why Is Upcasting Useful?

### 1️⃣ Polymorphism (Most Important)

If `eat()` was overridden in `Dog`:

```java
@Override
void eat()
{
    System.out.println("Dog is eating");
}
```

Then:

```java
Animal animal = new Dog("Brown", 3, "Labrador");
animal.eat();   // 🔥 Calls Dog's eat()
```

* ✔️ Method call depends on **object**, not reference
* ✔️ This is **runtime polymorphism**




---

## One-Line Definition (Perfect for Interviews)

> **Upcasting is the process of converting a subclass object into a superclass reference, enabling runtime polymorphism while restricting access to subclass-specific methods.**

---

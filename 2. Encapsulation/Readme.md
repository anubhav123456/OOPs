### Encapsulation in Java

**Encapsulation** is one of the four fundamental principles of Object-Oriented Programming (OOP).

#### **Definition**

Encapsulation means **bundling data (variables) and methods that operate on that data into a single unit (class)**.
It is also known as **Data Hiding**, because the internal state of an object is hidden from the outside world.

---

### **Encapsulation Benefits**

* **Data protection** – prevents unauthorized access or modification of data
* **Controlled access** – data is accessed and modified only through well-defined methods
* **Loosely coupled code** – changes in one class don’t affect others
* **Better maintainability** – easier to update, debug, and extend code

---

### **How Encapsulation is Achieved in Java**

1. Declare class variables as **`private`**
2. Provide **public getter and setter methods** to access and modify those variables

---

### **Encapsulation Example in Java**

```java
class Dog
{
    // Properties (State)
    private String color;
    private int age;
    private String breed;

    public Dog(String color, int age, String breed)
    {
        this.color = color;
        this.age = age;
        this.breed = breed;
    }

    public void setColor(String color)
    {
        this.color = color;
    }

    public void setAge(int age)
    {
        this.age = age;
    }

    public void setBreed(String breed)
    {
        this.breed = breed;
    }

    public int getAge()
    {
        return age;
    }

    public String getColor()
    {
        return color;
    }

    public String getBreed()
    {
        return breed;
    }

    // Behavior (Functionality)
    void bark()
    {
        System.out.println("Dog is barking");
    }

    void eat()
    {
        System.out.println("Dog is eating");
    }

    @Override
    public String toString()
    {
        return String.format("%s{ color : %s, age : %d, breed : %s }", "Dog", color, age, breed);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        // Object creation
        Dog dog = new Dog("Brown", 3, "Labrador");

        System.out.println(dog);

        dog.bark();
        dog.eat();
    }
}
```

---

### **Why This is Encapsulation**

* `color`, `age` and `breed` are **private**, so they cannot be accessed directly
* Access is **controlled** using 
  - `public void setColor(String color)`
  - `public void setAge(int age)`
  - `public void setBreed(String breed)`
  - `public int getAge()`
  - `public String getColor()`
  - `public String getBreed()`
* The internal implementation can change without affecting other classes

---

### **Real-World Analogy**

Think of an **ATM machine**:

* You cannot directly access the bank’s database
* You interact only through buttons (methods)
* The internal logic remains hidden

---

### **One-Line Summary**

> **Encapsulation bundles data and methods into a class and hides internal details to ensure data protection, controlled access, loose coupling, and better maintainability.**
---
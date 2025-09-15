# Four principles of OOP 

This is a document that includes four principles of OOP (encapsulation, abstraction, polymorphism, and inheritance.)

## Encapsulation
- Leaving your instance variables exposed (reachable with a dot operator) is quite dangerous. By forcing everyone to call a **setter** method, we can protect the cat from unacceptable size changes.
- Encapsulation **rules of thumb**: mark your instance variables **private** and provide **public** *getters* and *setters* for access control. 
  - By forcing other code to go through setter methods. That way, the setter method can validate the parameter and decide if it's do-able.

## Inheritance
- When one class **inherits** from another, the subclass **inherits** from the superclass.
  - In Java, the subclass **extends** the superclass.
  - The subclass can add new methods and instance variables of its own, and it can *override* the **methods** it inherits from the superclass.
  - Instance variables are **NOT** overridden.
- Four access levels: private, default, protected, public
  - Public members are inherited
  - Private members are not inherited


## Polymorphism
- When we define a supertype for a group of classes, any subclass of that supertype can be substituted where the supertype is expected.
- With polymorphism, the reference and the object can be different. You can write code that doesn't have to change when you introduce new subclass types into the program.
```java
Animal[] animals = new Animal[5]; // Declare an array of type Animal. In other words, an array that will hold objects of type animal
animals[0] = new Dog(); // Put ANY subclass of Animal in the Animal array
animals[1] = new Cat();
animals[2] = new Wolf();
animals[3] = new Hippo();
animals[4] = new Lion();
for (int i = 0; i < animals.length; i++){ // Get to loop through the array and call one of the Animal-class methods, and every subject does the right thing
  animals[i].eat(); // i = 0: Dog's eat method; i = 1: Cat's eat method
  animals[i].roam();
}
```
- Types: Overriding and Overloading
  - Overriding: Methods were defined in a class, and subclass can use its own way for realization.
  ```java
  class Animal {
    void speak() {
        System.out.println("Some sound");
    }
  }  

  class Dog extends Animal {
      void speak() {
          System.out.println("Woof");
      }
  }

  class Cat extends Animal {
      void speak() {
          System.out.println("Meow");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Animal a1 = new Dog();
          Animal a2 = new Cat();
          a1.speak(); // Output Woof
          a2.speak(); // output Meow
      }
  }
  ```
  - Overloading: In the same class, the name of the methods are the same, but the parameters are different. Compiler will decide which method to use.
  ```java
  class MathUtils {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; }
  }
  ```

## Abstraction


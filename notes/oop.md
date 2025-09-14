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



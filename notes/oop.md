# Four principles of OOP 

This is a document that includes four principles of OOP (encapsulation, abstraction, polymorphism, and inheritance.)

## Encapsulation
- Leaving your instance variables exposed (reachable with a dot operator) is quite dangerous. By forcing everyone to call a **setter** method, we can protect the cat from unacceptable size changes.
- Encapsulation **rules of thumb**: mark your instance variables **private** and provide **public** *getters* and *setters* for access control. 
  - By forcing other code to go through setter methods. That way, the setter method can validate the parameter and decide if it's do-able.

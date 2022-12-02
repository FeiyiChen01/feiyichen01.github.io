---
layout: essay
type: essay
title: "Design Patterns"
# All dates must be YYYY-MM-DD format!
date: 2022-12-1
published: true
labels:
  - Reflection
  - Design Patterns
---

<img class="img-fluid" src="../img/Factory.png">

## Design Patterns
In software engineering, Design Pattern is a proposed solution to a variety of common (recurring) problems in software design

Usually we write code, most of the cases are pipeline-type code, basically can achieve business logic. The best way to have fun writing code, I think, is to use design patterns to optimize your own business code.

In a variety of design patterns, the Factory Method Pattern is my favorite and one that I often use. In the factory method pattern, the factory parent class is responsible for defining the public interface to create product objects, while the factory subclass is responsible for generating concrete product objects. The purpose of this is to defer the instantiation of the product class to the factory subclass, which determines which concrete product class should be instantiated.

Simulating the purchase process of users, the two customers ordered BMW730 and BMW840 models from BMW730 and BMW840 factories respectively, and then the factories produced them according to the corresponding models and delivered them to the users after the production was completed.

```
abstract class BMWFactory {
  abstract produceBMW(): BMW;
}

class BMW730Factory extends BMWFactory {
  produceBMW(): BMW {
    return new BMW730();
  }
}

class BMW840Factory extends BMWFactory {
  produceBMW(): BMW {
    return new BMW840();
  }
}
```

* We created two factory classes, BMW730Factory and BMW840Factory, respectively, and used instances of these two classes to produce different models of cars.

```
const bmw730Factory = new BMW730Factory();
const bmw840Factory = new BMW840Factory();

const bmw730 = bmw730Factory.produceBMW();
const bmw840 = bmw840Factory.produceBMW();

bmw730.run();
bmw840.run();
```
A class does not know the class of the object it needs: In the factory method pattern, the client does not need to know the class name of the specific product class, only the corresponding factory. The specific product object is created by the specific factory class. The client needs to know the factory class to create the specific product.

A class specifies which object to create through its subclasses: In the factory method pattern, the abstract factory class only needs to provide an interface to create a product, and its subclasses determine the specific object to be created. Using object-oriented polymorphism and the principle of Richter's substitution, the subclass object overwrites the parent object while the program is running, thus making the system easier to scale.

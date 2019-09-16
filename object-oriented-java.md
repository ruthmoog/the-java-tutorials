# Object Oriented

source: https://docs.oracle.com/javase/tutorial/java/concepts/QandE/questions.html

## Questions
- Real-world objects contain `states` and `behaviors`.
- A software object's state is stored in `fields`.
- A software object's behavior is exposed through `methods`.
- Hiding internal data from the outside world, and accessing it only through publicly exposed methods is known as data `encapsulation`.
- A blueprint for a software object is called a `class`.
- Common behavior can be defined in a `superclass` and inherited into a `subclass` using the `extends` keyword.
- A collection of methods with no implementation is called an `interface`.
- A namespace that organizes classes and interfaces by functionality is called a `package`.
- The term API stands for `application programming interface`?

## Exercises
0. Create new classes for each real-world object that you observed at the beginning of this trail. Refer to the Bicycle class if you forget the required syntax.
0. For each new class that you've created above, create an interface that defines its behavior, then require your class to implement it. Omit one or two methods and try compiling. What does the error look like?
> the error message will list the required methods that have not been implemented.

### Lamp class and interface

```java
interface Lamp {
  void changeAngle(int newValue);

  void plugIn();

  void switchOn();
}
```

```java
class myDeskLamp implements Lamp {
  boolean on = false;
  boolean pluggedIn = false;
  int angle = 160;

  void changeAngle(int newValue) {
    angle = newValue;
  }

  void plugIn() {
    pluggedIn = !pluggedIn;
  }

  void switchOn() {
    on = !on;
  }

}
```

### Chili plant class and interface

```java
interface Plant {
  void water();

  void pollinate();

  void pickFruit();
}
```

```java
class myChiliPlant implements Plant {
  boolean healthy = true;
  int soilDampness = 5;
  boolean fruitYield = 4;
  boolean readyToHarvest = false;

  void water(int waterUnits) {
    soilDampness = soilDampness + waterUnits;
  }

  void pollinate(int flowerVisits) {
    if readyToHarvest == false {
      fruitYield = flowerVisits
    }
  }

  void pickFruit(int fruitPicked) {
    if readyToHarvest == true {
      fruitYield = fruitYield - fruitPicked
      if fruitYield == 0 {
        readyToHarvest = !readyToHarvest
      }
    }
  }

}
```

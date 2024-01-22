# Java Overview
## Empty Main Function
```java
public class Main {
    public static void main(String[] args) {
        // Enter your code here
    }
}
```
make sure the class name `Main` is the same as the file name.

## Simple Variable Declaration
```java
public class Main {
    public static void main(String[] args) {
        // Declare and initialize variables
        int age = 25;
        double height = 1.75;
        String name = "John";

        // Print the variables
        System.out.println("Age: " + age + ", Height: " + height + ", Name: " + name);
    }
}
```
make sure to differentiate between primitive types and objects in datatypes.

## Control Structure - Conditional If
```java
public class Main {
    public static void main(String[] args) {
        // Conditional if, else if, else
        int number = 10;

        if (number > 0) {
            System.out.println("Number is positive");
        } else if (number < 0) {
            System.out.println("Number is negative");
        } else {
            System.out.println("Number is zero");
        }
    }
}
```

## Control Structure - For i loop
```java
public class Main {
    public static void main(String[] args) {
        for (int i = 0; i < 5; i++) {
            System.out.println("Iteration: " + i);
        }
    }
}
```

## Control Structure - For each loop + Simple ArrayList
```java
import java.util.List;
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        List<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");

        for (String fruit: fruits) {
            System.out.println("Fruit: " + fruit);
        }
    }
}
```
`ArrayLists` are arrays with variable sizes, they can be extended and shortened.

## Control Structure - While loop
```java
public class Main {
    public static void main(String[] args) {
        int count = 0;

        while (count < 5) {
            System.out.println("Count: " + count);
            count++;
        }
    }
}
```
Three parts in a loop:
* Initial value: `int i = 0;`
* Counter: `i < 10;`
* Condition: `i++`

## Simple Method
```java
public class Main {
    public static void main(String[] args) {
        int result = addNumbers(4, 5);
        System.out.println("Result: " + result);
    }

    static int addNumbers(int a, int b) {
        return a + b;
    }
}
```
`Methods` are functions inside classes.

## Empty Class
```java
public class Person {

}
```
`Classes` can have variables and methods.

## Class - Variables
```java
public class Circle {
    final double radius = 5.0;
    static final double pi = 3.14159;
}
```

## Class - Constructor
```java
public class Rectangle {
    double width;
    double height;

    Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }
}
```
`Constructors` are used to initialize class members.

## Class - Methods
```java
public class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    int subtract(int a, int b) {
        return a - b;
    }
}
```
`Static Methods` can be called without using classes/objects

## Abstract Class
```java
abstract class Animal {
    // Abstract method that must be implemented by subclasses
    abstract void makeSound();

    // Concrete method with default implementation
    void sleep() {
        System.out.println("Animal is sleeping");
    }
}
```
`Abstract Classes` NEED to be inherited to work.

## Interfaces
```java
interface Flyable {
    // Interface method that must be implemented by classes implementing this interface
    void fly();
}
```
`Interfaces` are an extra way to add data to classes outside of their definition.
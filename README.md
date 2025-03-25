# Composition
Composition is a design principle where one class contains another class as a field (object) instead of inheriting \
from it. This helps us build complex objects by combining smaller, reusable parts.Instead of "A Dog is an Animal" 
(inheritance), composition focuses on "A Dog has a Heart" (composition). Composition makes code cleaner, reusable, and flexible! Instead of forcing a class into a rigid hierarchy,
we build objects by combining smaller objects—just like assembling a car, a computer, or even a library system.

## 🔹 Why Use Composition?

🔧 More Flexible – Objects can be mixed and matched like LEGO blocks.
📦 Encapsulation – Keeps things modular (each class does only what it should).
♻️ Reusable Code – A SoundMaker can be used by any object, not just instruments.
🔄 Changes Are Easier – You can swap parts of an object without rewriting everything.

🚗 Scenario: A Car Has an Engine

A car isn’t an engine, but it has an engine. So instead of inheritance (class Car extends Engine ❌), we use
composition (class Car has Engine ✅).
```bash
// 🔧 Engine class (a separate component)
class Engine {
    private String type;

    public Engine(String type) {
        this.type = type;
    }

    public void start() {
        System.out.println("The " + type + " engine is starting... Vroom! 🔥");
    }
}

// 🚗 Car class (contains an Engine instead of inheriting)
class Car {
    private Engine engine;  // Composition: Car HAS an Engine
    private String brand;

    public Car(String brand, String engineType) {
        this.brand = brand;
        this.engine = new Engine(engineType);  // Car owns an Engine
    }

    public void startCar() {
        System.out.println(brand + " is starting...");
        engine.start();  // Delegates engine-related work to Engine class
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Tesla", "Electric");
        myCar.startCar();  
        // Output:
        // Tesla is starting...
        // The Electric engine is starting... Vroom! 🔥
    }
}
```

## Exercises: Composition Practice:

## 🟢 Easy: Create a Computer Class
A Computer has a Processor.
The Processor class has a speed (GHz).
The Computer class contains a Processor and calls showSpeed().

## 🟡 Medium: Create a Library System
A Library has Books (use an ArrayList<Book>).
The Book class has title and author.
The Library class adds and displays books.

## 🔴 Hard: Restaurant Order System
A RestaurantOrder has a List of MenuItems.
The MenuItem class has name and price.
The RestaurantOrder class adds items and calculates the total price



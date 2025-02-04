// Interface defining behaviors
interface Animal {
    void makeSound(); // Abstract method
}

// Abstract class providing base properties and methods
abstract class Mammal implements Animal {
    String name;
    
    // Constructor
    public Mammal(String name) {
        this.name = name;
    }
    
    // Concrete method
    void sleep() {
        System.out.println(name + " is sleeping...");
    }
    
    // Abstract method to be implemented by subclasses
    abstract void move();
}

// Concrete class implementing the abstract class
class Dog extends Mammal {
    
    // Constructor
    public Dog(String name) {
        super(name);
    }
    
    // Implementing abstract method
    @Override
    void move() {
        System.out.println(name + " is running...");
    }
    
    // Implementing interface method
    @Override
    public void makeSound() {
        System.out.println(name + " says: Woof Woof!");
    }
}

// Main class to test the implementation
public class AnimalTest {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy"); // Creating a Dog object
        myDog.makeSound(); // Calling interface method
        myDog.move(); // Calling abstract class method implementation
        myDog.sleep(); // Calling concrete method from abstract class
    }
}

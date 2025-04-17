# python-week-5-assignment
Assignment 1: Design Your Own Class! 🏗️
Create a class representing anything you like (a Smartphone, Book, or even a Superhero!).
Add attributes and methods to bring the class to life!
Use constructors to initialize each object with unique values.
Add an inheritance layer to explore polymorphism or encapsulation.
Activity 2: Polymorphism Challenge! 🎭

Create a program that includes animals or vehicles with the same action (like move()). However, make each class define move() differently (for example, Car.move() prints "Driving" 🚗, while Plane.move() prints "Flying" ✈️).
Design Your Own Class! 🏗️ (Superhero )
# Base Class: Hero
class Hero:
    def __init__(self, name, power):
        self.name = name       # Public attribute
        self.__power = power   # Encapsulated (private) attribute
    
    def get_power(self):
        # Getter method for accessing the private power attribute
        return self.__power
    
    def set_power(self, power):
        # Setter method to update the power attribute
        self.__power = power

    def introduce(self):
        # Method for Hero to introduce themselves
        print(f"I am {self.name}, and my power is {self.__power}.")
    
    def use_power(self):
        # A method to use the power of the hero
        print(f"{self.name} is using their {self.__power}!")


# Derived Class: SuperHero (Inheritance and Polymorphism)
class SuperHero(Hero):
    def __init__(self, name, power, alias):
        super().__init__(name, power)  # Inheriting from Hero class
        self.alias = alias  # Superhero's alias (e.g., secret identity)

    def introduce(self):
        # Polymorphism: Overriding the introduce method
        print(f"I am {self.name}, also known as {self.alias}, and my power is {self.get_power()}.")

    def save_the_day(self):
        # Superhero-specific method
        print(f"{self.alias} is saving the day!")
        

# Create instances
hero = Hero("Wonder Woman", "Super Strength")
hero.introduce()
hero.use_power()

superhero = SuperHero("Clark Kent", "Super Speed", "Superman")
superhero.introduce()
superhero.use_power()
superhero.save_the_day()

Activity 2: Polymorphism Challenge! 🎭 (Vehicles Example)
# Base Class: Vehicle
class Vehicle:
    def move(self):
        print("The vehicle is moving")

# Derived Class: Car
class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

# Derived Class: Plane
class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

# Derived Class: Boat
class Boat(Vehicle):
    def move(self):
        print("Sailing 🚤")

# Create instances
vehicles = [Car(), Plane(), Boat()]

# Polymorphism in action: each vehicle defines its own move() method
for vehicle in vehicles:
    vehicle.move()

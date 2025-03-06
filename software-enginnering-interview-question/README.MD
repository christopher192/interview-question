### Software Engineering Interview Question

1. What is OOP?
    - OOP (Object-Oriented Programming) is a way of writing code using objects. Objects are like real-world things with data (attributes) and actions (methods). OOP helps organize code better, making it easier to reuse and maintain.
    - The four main ideas in OOP are:
        - Encapsulation – Bundling Data (Attributes and Methods) inside the  class and restricting direct access to some details.
            ```
            class Car:
                def __init__(self, brand, speed):
                    self.brand = brand  
                    self.__speed = speed  # Private attribute

                def accelerate(self, amount):
                    self.__speed += amount

                def get_speed(self):  # Controlled access
                    return self.__speed

            # Usage
            car = Car("Toyota", 60)
            car.accelerate(20)
            print(car.get_speed())  # Allowed

            # print(car.__speed)  # Not allowed (Encapsulation)
            ```
        - Inheritance - Allowing one class to derive properties and behaviors from another, promoting code reuse.
            ```
            # Parent class (Base class)
            class Car:
                def __init__(self, brand, speed):
                    self.brand = brand
                    self.speed = speed

                def accelerate(self, amount):
                    self.speed += amount
                    return f"{self.brand} accelerates to {self.speed} km/h."

            # Child class (inherits from Car)
            class ElectricCar(Car):
                def __init__(self, brand, speed, battery_capacity):
                    super().__init__(brand, speed) # Call parent constructor
                    self.battery_capacity = battery_capacity # New attribute

                def charge(self):
                    return f"{self.brand} is charging. Battery: {self.battery_capacity} kWh."

            # Usage
            tesla = ElectricCar("Tesla", 60, 75)

            print(tesla.accelerate(20)) # Inherited method from Car
            print(tesla.charge()) # Method from ElectricCar
            ```
        - Polymorphism - Allows different classes to have methods with the same name but different implementations.
            ```
            # Parent class
            class Car:
                def start(self):
                    return "The car is starting."

            # Child classes with different implementations of `start()`
            class ElectricCar(Car):
                def start(self):
                    return "The electric car starts silently."

            class PetrolCar(Car):
                def start(self):
                    return "The petrol car starts with a roaring engine."

            # Usage
            tesla = ElectricCar()
            bmw = PetrolCar()

            tesla.start() # ElectricCar version
            bmw.start() # PetrolCar version
            ```
        - Abstraction -  Hiding implementation details and exposing only the necessary functionality.
            ```
            from abc import ABC, abstractmethod

            # Abstraction - Defining a blueprint with abstract methods
            class Car(ABC):
                def __init__(self, brand, speed):
                    self.brand = brand
                    self.__speed = speed # Encapsulation (Private attribute)

                def accelerate(self, amount):
                    self.__speed += amount

                def get_speed(self): # Encapsulation (Controlled access)
                    return self.__speed

                @abstractmethod
                def start(self): # Abstraction (Must be implemented by subclasses)
                    pass
    
            # Concrete Subclasses implementing the abstract method
            class ElectricCar(Car):
                def start(self):
                    return f"{self.brand} starts silently!"

            class PetrolCar(Car):
                def start(self):
                    return f"{self.brand} starts with a roaring engine!"
            
            # Usage
            tesla = ElectricCar("Tesla", 60)
            bmw = PetrolCar("BMW", 70)

            print(tesla.start()) # Tesla starts silently!
            print(bmw.start()) # BMW starts with a roaring engine.

            # car = Car("Generic", 50)  # Not allowed (Cannot instantiate abstract class)
            ```
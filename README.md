# Week-5_python_Assignment
Week 5 Python Assignment Submission

# Assignment 1: Design Your own Class
# Create a class representing a Smartphone. 
# Add attributes and methods to bring the class to life! Use constructors to initialize each object with unique values. Add an inheritance layer to explore polymorphism or encapsulation.


# Answwer
# class: Smartphone
class Smartphone:
    def __init__(self, brand, model, storage, battery_life):
        self.brand = brand
        self.model = model
        self.storage = storage  # Storage in GB
        self.battery_life = battery_life  # Battery life in hours

    def call(self, contact_name):
        return f"Calling {contact_name} from your {self.model}."

    def browse_web(self, website):
        return f"Browsing {website} on {self.model}."

    def display_specs(self):
        return (f"Smartphone Specs:\nBrand: {self.brand}\nModel: {self.model}\n"
                f"Storage: {self.storage}GB\nBattery Life: {self.battery_life} hours")

# Derived class: GamingSmartphone
class GamingSmartphone(Smartphone):
    def __init__(self, brand, model, storage, battery_life, cooling_system):
        super().__init__(brand, model, storage, battery_life)
        self.cooling_system = cooling_system  # Unique attribute for gaming phones

    def launch_game(self, game_name):
        return f"Launching {game_name} on {self.model} with {self.cooling_system} cooling system."

    def display_specs(self):
        base_specs = super().display_specs()
        return f"{base_specs}\nCooling System: {self.cooling_system}"

# Derived class: CameraSmartphone
class CameraSmartphone(Smartphone):
    def __init__(self, brand, model, storage, battery_life, camera_megapixels):
        super().__init__(brand, model, storage, battery_life)
        self.__camera_megapixels = camera_megapixels  # Encapsulation: private attribute

    def take_photo(self):
        return f"Taking a photo with the {self.__camera_megapixels}MP camera on {self.model}."

    def display_specs(self):
        base_specs = super().display_specs()
        return f"{base_specs}\nCamera: {self.__camera_megapixels}MP"

# Testing the classes
smartphone1 = Smartphone("TechWhales", "AdehaX", 128, 24)
print(smartphone1.display_specs())
print(smartphone1.call("Femi"))

gaming_phone = GamingSmartphone("GameCore", "GameBlast10", 256, 18, "Liquid Cooling 2.0")
print(gaming_phone.display_specs())
print(gaming_phone.launch_game("Space Racers"))

camera_phone = CameraSmartphone("CamVision", "ZoomPlus", 64, 20, 108)
print(camera_phone.display_specs())
print(camera_phone.take_photo())


# Activity 2: Polymorphism Challenge!
# Create a program that includes vehicles with the same action (like move()). However, make each class define move() differently (for example, Car.move() prints "Driving" , while Plane.move() prints "Flying


# Answer

# class: Vehicle
  class Vehicle:
    def move(self):
# General move method (can be overridden by derived classes)
        raise NotImplementedError("This method should be overridden by subclasses")
# Derived class: Car
  class Car(Vehicle):
    def move(self):
        return "Driving"

# Derived class: Plane
  class Plane(Vehicle):
    def move(self):
        return "Flying"

# Derived class: Boat
  class Boat(Vehicle):
    def move(self):
        return "Sailing"

# Derived class: Bicycle
  class Bicycle(Vehicle):
    def move(self):
        return "Pedaling"

# Test the polymorphism
  vehicles = [Car(), Plane(), Boat(), Bicycle()]

  for vehicle in vehicles:
    print(f"{vehicle.__class__.__name__}: {vehicle.move()}")


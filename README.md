from abc import ABC, abstractmethod

# 1. Animal and Dog
class Animal:
    def speak(self):
        print("Some generic animal sound.")

class Dog(Animal):
    def speak(self):
        print("Bark!")

# 2. Shape, Circle, and Rectangle
class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2

class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

# 3. Vehicle, Car, ElectricCar
class Vehicle:
    def __init__(self, v_type):
        self.type = v_type

class Car(Vehicle):
    def __init__(self, v_type, brand):
        super().__init__(v_type)
        self.brand = brand

class ElectricCar(Car):
    def __init__(self, v_type, brand, battery):
        super().__init__(v_type, brand)
        self.battery = battery

# 4. Bird, Sparrow, Penguin
class Bird:
    def fly(self):
        print("Bird can fly.")

class Sparrow(Bird):
    def fly(self):
        print("Sparrow flies high.")

class Penguin(Bird):
    def fly(self):
        print("Penguins cannot fly.")

# 5. Encapsulation with BankAccount
class BankAccount:
    def __init__(self):
        self.__balance = 0

    def deposit(self, amount):
        self.__balance += amount

    def withdraw(self, amount):
        if amount <= self.__balance:
            self.__balance -= amount

    def check_balance(self):
        return self.__balance

# 6. Instrument, Guitar, Piano
class Instrument:
    def play(self):
        print("Playing instrument.")

class Guitar(Instrument):
    def play(self):
        print("Playing guitar.")

class Piano(Instrument):
    def play(self):
        print("Playing piano.")

# 7. MathOperations with class and static methods
class MathOperations:
    @classmethod
    def add_numbers(cls, a, b):
        return a + b

    @staticmethod
    def subtract_numbers(a, b):
        return a - b

# 8. Person class counting instances
class Person:
    count = 0

    def __init__(self, name):
        self.name = name
        Person.count += 1

    @classmethod
    def total_persons(cls):
        return cls.count

# 9. Fraction with __str__
class Fraction:
    def __init__(self, numerator, denominator):
        self.numerator = numerator
        self.denominator = denominator

    def __str__(self):
        return f"{self.numerator}/{self.denominator}"

# 10. Vector with operator overloading
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"({self.x}, {self.y})"

# 11. Person greet
class PersonGreet:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

# 12. Student with average_grade
class Student:
    def __init__(self, name, grades):
        self.name = name
        self.grades = grades

    def average_grade(self):
        return sum(self.grades) / len(self.grades)

# 13. Rectangle with set_dimensions and area
class Rectangle2:
    def set_dimensions(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

# 14. Employee and Manager with salary calculation
class Employee:
    def calculate_salary(self, hours, rate):
        return hours * rate

class Manager(Employee):
    def calculate_salary(self, hours, rate, bonus):
        return super().calculate_salary(hours, rate) + bonus

# 15. Product with total_price
class Product:
    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

    def total_price(self):
        return self.price * self.quantity

# 16. Animal with sound() abstract
class AnimalSound(ABC):
    @abstractmethod
    def sound(self):
        pass

class Cow(AnimalSound):
    def sound(self):
        print("Moo")

class Sheep(AnimalSound):
    def sound(self):
        print("Baa")

# 17. Book with get_book_info
class Book:
    def __init__(self, title, author, year_published):
        self.title = title
        self.author = author
        self.year = year_published

    def get_book_info(self):
        return f"{self.title} by {self.author}, published in {self.year}"

# 18. House and Mansion
class House:
    def __init__(self, address, price):
        self.address = address
        self.price = price

class Mansion(House):
    def __init__(self, address, price, number_of_rooms):
        super().__init__(address, price)
        self.number_of_rooms = number_of_rooms

## OOPS:
Object-Oriented Programming (OOPs) is a programming paradigm based on the concept of "objects", which contain data (attributes) and functions (methods) that operate on the data.

#### Class and Object
#### Explanation:
- A class is a blueprint for creating objects.

- An object is an instance of a class with actual value

#### Example:
```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print(f"Hello, my name is {self.name}")

# Creating object
p1 = Person("Alice")
p1.greet()
```
#### Constructor (__init__ method)
#### Explanation:
- The __init__() method is called automatically when a new object is created.

- It initializes the object with default or user-provided values.

#### Example :
```python
class Car:
    def __init__(self, brand, year):
        self.brand = brand
        self.year = year

c = Car("Toyota", 2020)
print(c.brand, c.year)
```

#### self Keyword:
#### Explanation:
- self refers to the current object.

- It is used to access instance variables and methods inside the class.

#### Example:
```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(f"{self.name} says Woof!")

d = Dog("Bruno")
d.bark()
```

####  Encapsulation
#### Explanation:
- Encapsulation protects object data from being modified directly.

- Achieved using private variables (prefix with __).

#### Example:
```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # private variable

    def deposit(self, amount):
        self.__balance += amount

    def get_balance(self):
        return self.__balance

acc = BankAccount(1000)
acc.deposit(500)
print(acc.get_balance())
```

#### Abstraction
#### xplanation:
- Abstraction hides complex logic and shows only necessary details.

- Implemented using abstract classes and abstract methods.

#### Example:
```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side * self.side

s = Square(4)
print(s.area())
```

####  Inheritance
#### Explanation:
- A class can inherit attributes and methods from another class.

#### Example:
```python
class Animal:
    def speak(self):
        print("Animal sound")

class Cat(Animal):
    def meow(self):
        print("Meow")

c = Cat()
c.speak()  # inherited
c.meow()   # own method
```

#### Polymorphism
#### Explanation:
- Same method name with different behavior in different classes.

#### Example:
```python
class Bird:
    def sound(self):
        print("Chirp")

class Dog:
    def sound(self):
        print("Bark")

def make_sound(animal):
    animal.sound()

make_sound(Bird())
make_sound(Dog())
```

#### Class vs Instance Variables
### Explanation:
- Instance variable: Belongs to each object.

- Class variable: Shared by all objects.

#### Example:
```python
class Employee:
    company = "TechCorp"  # Class variable

    def __init__(self, name):
        self.name = name   # Instance variable

e1 = Employee("Alice")
e2 = Employee("Bob")

print(e1.name)       # Alice
print(e2.company)    # TechCorp
```

#### Static Method and Class Method
#### Explanation:
- @staticmethod: Doesn't access class or instance data.

- @classmethod: Uses class data via cls.

#### Example:
```python
class Math:
    @staticmethod
    def add(a, b):
        return a + b

    @classmethod
    def info(cls):
        print("This is a Math class")

print(Math.add(5, 3))
Math.info()
```

#### Magic Methods (Dunder Methods)
#### Explanation:
- Special methods like __str__, __add__, __len__.

- Allow customizing built-in operations.

#### Example:
```python
class Book:
    def __init__(self, pages):
        self.pages = pages

    def __add__(self, other):
        return self.pages + other.pages

b1 = Book(150)
b2 = Book(200)
print(b1 + b2)
```

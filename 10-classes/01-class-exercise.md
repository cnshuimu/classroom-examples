### 1
Create the class with the `__init__` method for the following.

```
Person
======
name: str
height: int
strength: int
health_points: int = 100
---------
__str__(self) -> str
introduce(self) -> void
punch(Person) -> void
```

```python
class Person:
    """
    Attrs:
        height (int): in cm
        name (str): First and last
        strength (int): How strong the person is 
        health_points (int): Out of 100 (everyone starts at 100)
    """
    def __init__(self, ...):
        pass
```

### 2
- Create two `Person` objects.

- Add a `__str__` (magic) method that displays the name and hp of the person.

- Print out each `Person` object.

### 3

- add an `introduce` method that will say "Hello, my name is {name}"

- Make both people objects introduce themselves.

### 4

- Add a `punch` method that will take another person as an argument, and subtract 10 from that person's hp.

- Make one `Person` object `punch` the other person object.

- Make one `Person` object punch themself.

### 5
- Add an `eat` method that, when used, will restor the health points back to 100.


class Person:
    """
    Attrs:
        height (int): in cm
        name (str): First and last
        strength (int): How strong the person is 
        health_points (int): Out of 100 (everyone starts at 100)
    """
    def __init__(self, height: int, name: str, strength: int, health_points = 100):
        """initialized the variables"""

        self.height = height
        self.name = name
        self.strength = strength
        self.health_points = health_points
    
    def __str__(self) -> str:
        """return a text.

        Args: 
            self
        
        Returns: 
            str
        """
        return f"{self.name}: {self.health_points}"
    
    def introduce(self) -> str:
        """display message of the class.

        Args: 
            self

        Returns: 
            str
        """
        return f"Hello, my name is {self.name}"

    def punch(self, person: 'Person') -> None:
        """reduce 10 health point from the person.

        Args: 
            self
            person: Person
        
        Returns: 
            None
        """
        person.health_points -= 10

    def eat(self) -> None:
        """recover the health point to 100.

        Args: 
            self
        
        Returns: 
            None
        """
        self.health_points = 100

Jack = Person(163, "Jack", 50)
Peter = Person(178, "Peter", 70)

print(Jack)
print(Peter)
print(Jack.introduce())
print(Peter.introduce())
Jack.punch(Peter)
Peter.punch(Jack)
print(Jack)
print(Peter)
Jack.eat()
Peter.eat()
print(Jack)
print(Peter)

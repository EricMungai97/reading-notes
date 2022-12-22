# Classes and Objects

[source](https://www.learnpython.org/en/Classes_and_Objects)

[source](https://www.w3schools.com/python/python_classes.asp)

A `Class` is like an object constructor, or a "blueprint" for creating objects.

Objects contain variables and methods.

```
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def myfunc(self):
    print("Hello my name is " + self.name)
```

The self parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class.

The `__init__()` function is called automatically every time the class is being used to create a new object.

To access object variables or object methods we can use dot notation.

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.variable
```

```
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.function()
```

## Thinking Recursively

[source](https://realpython.com/python-thinking-recursively/)

The typical structure of a recursive algorithm. If the current problem represents a simple case, solve it. If not, divide it into subproblems and apply the same strategy to them.

A recursive function will continue to call itself and repeat its behavior until some condition is met to return a result.

`lru_cache` is a decorator that caches the results. Thus, we avoid recomputation by explicitly checking for the value before trying to compute it.

### Pytest Fixtures and Coverage

[source](https://docs.pytest.org/en/latest/explanation/fixtures.html)

[source](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)

**Fixtures**

These are objects that all available to all your tests. Thes objects contain data that you want to share across tests.

They provide a defined, reliable and consistent context for the tests. 

```
class Fruit:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        return self.name == other.name


@pytest.fixture
def my_fruit():
    return Fruit("apple")


@pytest.fixture
def fruit_basket(my_fruit):
    return [Fruit("banana"), my_fruit]


def test_my_fruit_in_basket(my_fruit, fruit_basket):
    assert my_fruit in fruit_basket

```

**Coverage**

`Code coverge` checking that your tests have run all the code.

100% coverage does doesn't mean your code is perfect or that it lacks bugs.

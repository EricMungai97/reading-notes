# Pythonisms

## Dunder Methods

Special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

Dunder methods help you emulate the behavior of `built-in` types.

For example, to get the length of a string you can call `len('string')`. But an empty class definition doesn’t support this behavior out of the box:

## Python Data Model

Lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access etc.

Object  initialization `__init__`

Object representstion `__str__`, `__repr__`

Iteration: `__len__`, `__getitem__`, `__reversed__`

Operator Overloading: `__eq__`, `__lt__`

Operator overloading for merging `__add__`

You can make an object callable like a regualr function by adding the `__call__` dunder method.

A downside of having a `__call__` method on your objects is that it can be hard to see what the purpose of calling the object is.

Context Manager Support and With Statement: `__enter__`, `__exit__`.

A `context manager` is a simple “protocol” (or interface) that your object needs to follow so it can be used with the with statement. 

Basically all you need to do is add` __enter__ and __exit__ `methods to an object if you want it to function as a context manager.

## Iterators

Iterators provide a sequence interface to Python objects that’s `memory efficient` and considered Pythonic. Behold the beauty of the for-in loop!

To support iteration an object needs to implement the iterator protocol by providing the `__iter__` and `__next__` dunder methods.

Class-based iterators are only one way to write iterable objects in Python. Also consider generators and generator expressions.

How to build out an iterator that doesn't stop.

```python
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value
```

Iterators use `exceptions` to structure control flow.

To signal the end of iteration, a python iterator simply raises the built-in StopIteration exception.

Iterator that stops:

```python
class BoundedRepeater:
    def __init__(self, value, max_repeats):
        self.value = value
        self.max_repeats = max_repeats
        self.count = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.count >= self.max_repeats:
            raise StopIteration
        self.count += 1
        return self.value
```

## Generators

`Generator functions` are syntactic sugar for writing objects that support the iterator protocol. 

Generators abstract away much of the boilerplate code needed when writing class-based iterators.

The `yield statement` allows you to temporarily suspend execution of a generator function and to pass back values from it.

Generators start raising StopIteration exceptions after control flow leaves the generator function by any means other than a yield statement.

```python
def repeater(value):
    while True:
        yield value
```

 Calling a generator function doesn’t even run the function. It merely creates and returns a `generator object`:

```python
>>> repeater('Hey')
<generator object repeater at 0x107bcdbf8>
```
The code in the generator function only executes when next() is called on the generator object:

```python
>>> generator_obj = repeater('Hey')
>>> next(generator_obj)
'Hey'
```

**Whereas a return statement disposes of a function’s local state, a yield statement suspends the function and retains its local state.**

**this means local variables and the execution state of the generator function are only stashed away temporarily and not thrown out completely.**




# List Comprehensions

[source](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

[source](https://www.w3schools.com/python/python_lists_comprehension.asp)

List comprehension offers a shorter syntax when you want ot create a new list based on the values of an existing list.

It helps keep your code elegant and readable.

**The Syntax**

`newlist = [expression for item in iterable if condtiom == True]`

first is the expression we'd like to carry out

second is the object that the expression will work on

third is the iterable list of objects to build our new list from.

fourth is the condition which is like a filter that only accepts items that evaluate as true.

Example Code

```

newlist = [x for x in range(10)]

print(newlist) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x.upper() for x in fruits]

print(newlist) # ['APPLE', 'BANANA', 'CHERRY', 'KIWI', 'MANGO']

newlist = [x for x in range(10) if x < 5] 

print(newlist) # [0, 1, 2, 3, 4]

fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

newlist = [x for x in fruits if x != "apple"]

print(newlist) # ['banana', 'cherry', 'kiwi', 'mango']

even_numbers = [ x for x in range(1,20) if x % 2 == 0]

print(even_numbers) # [2, 4, 6, 8, 10, 12, 14, 16, 18]

```

We can even use functions in list comprehensions

example code 

```
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)

[2, 4, 6, 8, 10, 12, 14, 16, 18]
```

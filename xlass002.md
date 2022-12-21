# Testing and Modules

## Test Driven Development

[source](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)

TDD is a software development practice that focuses on creating unit test cases before developing the actual code.

```Unit tests ``` are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.

We need to be descriptive about our test names i.e. say ```what is expected``` and ``` what we are testing```

The test file name should follow the same name of module name. For instance, if our module is ```series.py```, our test name should be ```test_series.py```.


The Arrange, act and assert structure helps you write out your tests.

1.	Arrange: you need to organize the data needed to execute that piece of code (input);

2. 	Act: here you will execute the code being tested (exercise the behaviour);

3. Assert: after executing the code, you will check if the result (output) is the same as you were expecting.


TDD enables you grow your software design consciously and it makes your code more reliable in that after a change you can run you tests.

## Recursion

[source](https://www.geeksforgeeks.org/recursion/)

Recursion is the process by which a function calls itself directly or indirectly.

Recursive algorithms help solve certain problems easily.

A recursive function solves a particular problem by calling a copy of itself and solving smaller subproblems of the original problems.

Recursion uses more memory, because the recursive function adds to the stack with each recursive call, and keeps the values there until the call is finished. The recursive function uses LIFO (LAST IN FIRST OUT) Structure just like the stack data structure

There are two types of cases in recursion i.e. ```recursive case``` and a ```base case```.

 The base case is used to terminate the recursive function when the case turns out to be true.

Each recursive call makes a new copy of that method in the stack memory.

Infinite recursion may lead to running out of stack memory.


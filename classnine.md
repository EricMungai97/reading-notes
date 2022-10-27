# Functional programming concepts

[SOURCE](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

***What is functional programming?***

Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data

[SOURCE](https://en.wikipedia.org/wiki/Functional_programming)

******What is a pure function and how do we know if something is a pure function?***

It is a function that always returns the same results if the same arguments are passed.

We know it is a pure function if returns the same result if given the same arguments.

Also, it doesn't cause any observable side effects

***What are the benefits of a pure function?***

1. Thye are ```stable```, ```consistsent``` and ```predictable```

2. Makes code easier to test.


***What is immutability?***

Unchanging over time or unable to be changed.
Data that is immutable cannot change its state after it is created.

***What is Referential transparency****

When a function consistently yields the same result for the same input.

```pure function ``` + ```immutability``` = ```referential transparency```

## Modules and ```require();```

***What is a module?***

It basically  a JavaScript file.

***What does the word ‘require’ do?***

Require imports the module file.***

***How do we bring another module into the file the we are working in?***

Using require with the file path of the module.

***What do we have to do to make a module available?***

```module.export``` and the assign our require to a variable so we can use it.
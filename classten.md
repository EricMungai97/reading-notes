# Understanding the JavaScript Call Stack

[source](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4)

***What is a ‘call’?***

A ```call``` is a function invocation.

***How many ‘calls’ can happen at once?***

Only one because the call stack is single, meaning function execution is done one at time from top to bottom.

***What does LIFO mean?***

Last In First Out. It means that the last function that gets pushed into the stack is the first to be popped out when the function returns.

***Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.***

```
function smile(){
  throw new Error(Cant smile)
}

function cry(){
  smile();
}

function laugh(){
  cry();
}

laugh();
```

```
Uncaught Error: Stack Trace Error
 at smile
 at cry
 at laugh
 ```

***What causes a Stack Overflow?***

A recursive function i.e. a function that calls itself without an exit point. This is because the browser has a maximum stack call it can accomodate.

## JavaScript Error Messages

[SOURCES](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

***What is a ‘reference error’?***

Errors that pop up when you try and use a variable that has not yet been declared.

***What is a ‘syntax error’?***

An error that occurs when you have something that cannot be parsed in terms of syntax.

***What is a ‘range error’?***

An error thrown when trying to pass a value as an argument to a function that does not allow a range that includes the value

***What is a ‘type error’?***

An error that shows up when the types of data you are trying to use or access is incompatible .

***What is a breakpoint?***

A point in your program where the code will stop executing.

***What does the word ‘debugger’ do in your code?***

It sets a break point on your code.
# Stacks and Queues

## Stacks

A stack is a data structure that consists of `Nodes`. Each Node references the next Node in the stack, but does not reference its previous.

Common terminology for a stack is

* Push - Nodes or items that are put into the stack are pushed

* Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.

* Top - This is the top of the stack.

* Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.

* IsEmpty - returns true when stack is empty otherwise returns false.

Stacks follow these concepts:

FILO

`First In Last Out`

This means that the first item added in the stack will be the last item popped out of the stack.
LIFO

`Last In First Out`

This means that the last item added to the stack will be the first item popped out of the stack.

`Push O(1)`

Pushing a Node onto a stack will always be an `O(1)` operation. This is because it takes the same amount of time no matter how many Nodes (n) you have in the stack.

```
    def push(self, value):
        # Adds node to the top of the stack
        if self.top is None:
            self.top = Node(value)
            return
        old = self.top
        self.top = Node(value)
        self.top.next = old

```

`Pop O(1)`

Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.

```
 def pop(self):
        # Remove top node from stack, Returns value of removed node.
        if self.top is None:
            raise InvalidOperationError("Method not allowed on empty collection")
        popped = self.top
        self.top = self.top.next
        return popped.value

```

`Peek O(1)`

When conducting a peek, you will only be inspecting the top Node of the stack.

Typically, you would check isEmpty before conducting a peek. This will ensure that an exception is not raised. Alternately, you can wrap the
call in a try/catch block.

```
    def pop(self):
        # Remove top node from stack, Returns value of removed node.
        if self.top is None:
            raise InvalidOperationError("Method not allowed on empty collection")
        popped = self.top
        self.top = self.top.next
        return popped.value
```

**Stack visualization**

![Stack image](/images/stack1.PNG)

## Queues

Common terminology for a queue is

* Enqueue - Nodes or items that are added to the queue.

* Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.

* Front - This is the front/first Node of the queue.

* Rear - This is the rear/last Node of the queue.

* Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.

* IsEmpty - returns true when queue is empty otherwise returns false.

Queues follow these concepts:

`FIFO`

First In First Out

This means that the first item in the queue will be the first item out of the queue.

`LILO`

Last In Last Out

This means that the last item in the queue will be the last item out of the queue.

**Queue Visualization**

![Queue](/images/Queue.PNG)

***Enqueue O(1)***

When you add an item to a queue, you use the enqueue action. This is done with an O(1) operation in time because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.

```
    def enqueue(self, value):
        # check to see if queue is empty
        if self.rear:
            self.rear.next = Node(value)
            self.rear = self.rear.next
            return
        self.rear = self.front = Node(value)

```

***Dequeue O(1)***

When you remove an item from a queue, you use the dequeue action. This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue, you are always just removing the front Node of the queue.

Typically, you would check isEmpty before conducting a dequeue. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.

```
    def dequeue(self):
        if self.front is None:
            raise InvalidOperationError
        else:
            dequeued = self.front
            self.front = self.front.next
            return dequeued.value
```

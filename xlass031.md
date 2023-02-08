# Conditional Rendering

[source](https://reactjs.org/docs/conditional-rendering.html)

Conditional rendering in React works the same way conditions work in JavaScript.

Use JavaScript operators like `if` or the `conditional operator` to create elements representing the current state, and let React update the UI to match them.

`If statement` is a fine way to conditionally render a component, sometimes you might want to use a shorter syntax. There are a few ways to inline conditions in JSX, explained below.

1. Embedding expressions in JSX and wrapping them in curly braces together with the JavaScript logical `&&` operator

Example

```
function Mailbox(props) {
  const unreadMessages = props.unreadMessages;
  return (
    <div>
      <h1>Hello!</h1>
      {unreadMessages.length > 0 &&        <h2>          You have {unreadMessages.length} unread messages.        </h2>      }    </div>
  );
}
```

 if the condition is `true`, the element right after && will appear in the output. If it is false, React will `ignore` and skip it.
 
Note that returning a `falsy expression` will still cause the element after && to be skipped but will return the falsy expression. 

**Inline If-Else with Conditional Operator**

Another method for conditionally rendering elements inline is to use the JavaScript conditional operator `condition ? true : false.`

Example

```
render() {
  const isLoggedIn = this.state.isLoggedIn;
  return (
    <div>
      The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.    </div>
  );
}
```

## List and Keys

You can build collections of elements and include them in JSX using curly braces `{}`.

Example

```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>  <li>{number}</li>);
//Then, we can include the entire listItems array inside a <ul> element:
<ul>{listItems}</ul>
```

A `key` is a special string attribute you need to include when creating lists of elements.

Keys help React identify which items have `changed, are added, or are removed`. 

Keys should be given to the elements inside the array to give the elements a stable identity:

The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys:

```
const todoItems = todos.map((todo) =>
  <li key={todo.id}>    {todo.text}
  </li>
);
```

When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort:

Not recommended since the order of items may change.

Keys used within arrays should be `unique` among their siblings. However, they don’t need to be globally unique. We can use the same keys when we produce two different arrays:

## Lifting State

In React, sharing state is accomplished by moving it up to the `closest common ancestor` of the components that need it. This is called `lifting state up`.

There should be a single `source of truth` for any data that changes in a React application. 

Usually, the state is first added to the component that needs it for rendering. 

Then, if other components also need it, you can lift it up to their closest common ancestor. 

Instead of trying to sync the state between different components, you should rely on the top-down data flow.

## Composition vs Inheritance

Some components don’t know their children ahead of time. This is especially common for components like Sidebar or Dialog that represent generic “boxes.

such components use the special children prop to pass children elements directly into their output:

```
function FancyBorder(props) {
  return (
    <div className={'FancyBorder FancyBorder-' + props.color}>
      {props.children}    </div>
  );
}
```
This lets other components pass arbitrary children to them by nesting the JSX:

```
function WelcomeDialog() {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">        Welcome      </h1>      <p className="Dialog-message">        Thank you for visiting our spacecraft!      </p>    </FancyBorder>
  );
}
```

## Thinking in React

1. Break The UI Into A component Hierachy
2. Build a static version in react
3. Identify the minimal but complete representaion of UI 
4. Identify where your state should live
5. Add Inverse Data Flow

## Things I want to Know More About

Inheritance in react
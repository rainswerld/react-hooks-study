# React Hooks Study

## Study Intro

Use your favorite search engine and the provided readings to research and
respond to the following questions.

In your responses, be sure to cite any relevant sources you consulted in your
search. We ask you to write responses in your own words in order to see how you
process what you've read. Please do not respond with direct quotes from source
material. Instead, digest what you've read and repeat it in your own voice.

## Study Readings

- [Introducing Hooks](https://reactjs.org/docs/hooks-intro.html)
- [Hooks at a Glance](https://reactjs.org/docs/hooks-overview.html)

## What is a hook?

In your own words, define what a hook is in React.

```md
From the readings: "Hooks are functions that let you 'hook into' React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes."
```

## Hooks: State and Effects

The readings go into two built-in hooks in React. Explain each below.

```md
State Hooks: `useState` is a built-in hook for handling state in function components. Similar to `this.setState` but only works with a single argument of the updated state.

Effect Hooks: `useEffect` is a built-in hook for adding side-effects to components. These effects include things like updating the DOM or fetching data. `useEffect` works similar to lifecycle methods like `componentDidMount`.
```

## Hooks: Component Type

What type of component would you add hooks to?

```md
Function components
```

## Hook Benefits

What does adding a hook to a component allow that component to do?

```md
Hooks let you use state and other React features without writing a class.

Other features include
1. access to lifecycle methods with useEffect
2. access to context with useContext
```

## Rules of Hooks

What are the two "Rules of Hooks"?

```md
1. Only Call Hooks at the Top Level

Don’t call Hooks inside loops, conditions, or nested functions. Instead, always use Hooks at the top level of your React function. By following this rule, you ensure that Hooks are called in the same order each time a component renders. That’s what allows React to correctly preserve the state of Hooks between multiple useState and useEffect calls. (If you’re curious, we’ll explain this in depth below.)

2. Only Call Hooks from React Functions

Don’t call Hooks from regular JavaScript functions. Instead, you can:

✅ Call Hooks from React function components.
✅ Call Hooks from custom Hooks.

By following this rule, you ensure that all stateful logic in a component is clearly visible from its source code.
```

## Converting a Component

Take a look at [`Movie.js`](src/Movie.js). This component uses the regular
ES6 class syntax.

Now look at [`MovieHooks.js`](src/MovieHooks.js). This component is exactly the
same, but uses hooks instead of classes.

There are some big changes between these components. Describe them below:

```md
1. First big change is converting the component from a class to a function. This is done by replacing `class` with `const` and changing `extends Component` to function syntax `= (props) =>`. This means throughout the component we don't need to say `this.props` but can just reference the parameter `props`.

2. We no longer need to import `Component` from the react module, but instead import `{ useState }` for the built-in state hook.

3. In `Movie.js` we have a constructor to handle setting our initial state. In the hooks version, we instead initialize the state using the  `useState` hooks method. This gives us state variables `liked` and `hideActors`, and methods for changing those states, `setLiked` and `setHideActors`.

4. All of our methods like `toggleLike` were changed to use `const`, and instead of using `this.setState` they use the methods defined with `useState`. Similarly, we removed all instances of `this.state.key` and instead just reference the state variables we defined.

5. Finally, instead of a `render` method, we can just `return` our JSX with all relevant props and state where they need to be.
```

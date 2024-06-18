# React State Errors

- Welcome into state section, in this section we will explore examples of errors which can happen when working with states in react, we will explore hook used react which includes from the beginner level to intermediate.Before you dive into this section I think it will be best if you know the rules of each state which you are using into your component.

## useState

<details>
<summary>
- Into this section `useState` hook we will explore what is useState, what are the rules of react useState, when to use it and possible solution to react useState errors,
</summary>

## use State Rules

- **Call hooks at the top level**.Don't call hooks inside the condition or function, or nested functions it's a bad practice.

```jsx
import { useState } from "react";
```

- **Use Hooks in the same order**.If you have started to set the state of a certain object then it should start before another component into your project,**Why?** Some of the code in your project can depend on the first code to be executed then next but if you have changed then it will result into an error.Example:

```jsx

```

</details>

<details>
<summary>Here are some of the erros you can encounter when working with react useState</summary>

1: **Parsing error**: This occurs when you created a state for a certain object may be blog title but you have redeclared into your program example:

```jsx
const [blogTitle, setBlogTitle] = useState("");
const [blogTitle, setBlogTitle] = useState("");
```

**Solution** :
- Remove state for variables which has been redeclared inorder to follow best code practices such as DRY principle(Don't Repeat Yourself):Remove duplicates.

</details>

## useEffect

## useFetch

## useRef

## useParms

## Reference

- [useState React](https://react.dev/reference/react/useState)

# General

- [undefined error](#undefined-error)

- Welcome to this section where I will be documenting about common errors which are general and can happen into beginner concepts, intermediate to advanced concepts in react.

## undefined error

- This type of error occurs when you have inserted a certain function or any dynamic value into your component but you have not create a variable for it.Example: You have a button and you have included the `onClick` attribute in which when a user clicks into a button then deletes a post but You have not defined a function for it.

```html
<button oncLick="{handleDelete}">Delete</button>
```

- To solve this error depends on requirement of your project,but below are possible solutions.

<summary>
<details>

Before you do all of that identify your error then using <kbd>ctrl + f</kbd> into visual studio code and search for that error into your program.

1. Create a function to handle the delete,this can be about deleting blog post or anything depending on your project

2. Remove unnecessary code,If you have a button with the `handleDelete` Function but you don't use it simply remove it into your code to make code look clean and concise.
</details>
<summary>

- Note that undefined error it means that a functionality you have implemented is unknown so you need to add that functionality which is undefined into your project or remove it.
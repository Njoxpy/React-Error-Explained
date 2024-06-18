# Components  Error

## Syntax Errors

- Into this section we will look into common react errors which occurs when working with react components mostly  on beginner concepts.

## The use of className instead of class

- This error occurs in react because when using react with css or bootstrap to add an attribute for class it should be `className` instead of a class because class in JavaScript is a reserved keyword so it should not be used for other purpose instead of it's intended purpose.

```jsx
// bad practice
const Home = () => {
    return (
        <div class="text-center m-2">
            <h2>React Is Awesome</h2>
        </div>
    );
}
 
export default Home;

// good practice

const Home = () => {
    return (
        <div className="text-center m-2">
            <h2>React Is Awesome</h2>
        </div>
    );
}
 
export default Home;
```

- Sometimes it may not bring error into your project but it will show warning so possible solutions to that error is by using `className` instead of `class` attribute.

## forgetting to close tags, missing commas, or semicolons.

- This is the common error which occurs when working with react project,due to this errors can lead to syntax error compiler fails to compiling our code due to errors which have occured into a project.Let's some of the common errrs which occurs when working into it and see possible soultions into it.


```jsx
// closing tag error
const Home = () => {
    return (
        <div className="text-center m-2">
            <h2>React Is Awesome<h2>
        </div>
    );
}
 
export default Home;

// Line 5:14:  Parsing error: Unterminated JSX contents. (5:14)
```

- From the above the error which has occured is called parsing error and is telling that Unterminated JSX contents in a line 5 `<h2>React Is Awesome<h2>` possible solutions into it is to add a closing tag into the `h2` tag.Also before you start solving that error you should read the type of error and the line in which an error has occured also and description of an error.

## Missing Comma

- This type of error occurs when components are missing the comma for terminating a statement into a react project and can happen when creating stateless functional components in react,That's why is do advise to use [react code snippets extension](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets) for VS Code which provides a boilerplate for creating react functional components, let's look into how a comma can lead to errors into our program.

```jsx

```

## Props errors

- When passing data from one components to another component using prop there are some sort of errors can happen due to passing wrong value into a prop, passing wrong components into components.

## Unused Variable

- This type of error occurs when you have created a variable or any other object into your components but you have not used it so this reads into the `unused variable warning` into your project.Example:

```jsx
  const [eventName, setEventName] = useState("");
```

- From the above example we have created a state variable for eventName but we have nto used into the project so what leads is the unused variable warning.There are many tools to deal with this error but eaxmaple of tool to use is the linter,Linter scans and checks for unsused variable into your project which have `.jsx` or `.js` extension into your project to install just run the following command into your terminal.

```sh
# install eslint
npm init @eslint/config@latest

# install linter
```



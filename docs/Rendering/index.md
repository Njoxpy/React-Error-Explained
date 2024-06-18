## Rendering Erros

## Module not found:

- This type of errors happens when you are working with files into your project can be occuring when you have a file `Create.js` and you have imported into the `App.js` root component of your project but it comes that you have moved `Create.js` into another folder may be called `Form` which contains the list of forms into you project.

```jsx
ERROR in ./src/App.js 9:0-30
Module not found: Error: Can't resolve './Create' in 'C:\Users\Njox\Desktop\reactjs\fumbakasa-blog\src'

webpack compiled with 1 error and 1 warning
```

- Another cause of this problem is caused by deletion of your project file or folder of your project.

**Soulution**

- Update file path for your project inorder to solve this error.

- Crosscheck to see if the file you have imported exist into your project or not.

- Navigate into the app root component to resolve that error.
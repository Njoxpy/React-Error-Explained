# Warning

- [unused variables (no-unused-vars)](#unused-variables-no-unused-vars)

- In this section we will take a look into errors which are happening into react application are not errors but they exist to warn use that sometning is wrong as a time.

## unused variables (no-unused-vars)

- unused variables are type of errors which occurs in react when you create a variable or function, object, array for a certain things but you have not used it into your program.

- It is like you have allocated a memory to store a certain object, variable, function, array but you have not used it.Example:

```js
import { useState } from "react";

const Login = () => {
    const [userName, setUserName] = useState("")
    const [password, setPassword] = useState("")
    

    return (
        <div>
            <form className="container">
                <div className="mb-3">
                    <label for="exampleInputEmail1" className="form-label">Email address</label>
                    <input type="email" className="form-control" id="exampleInputEmail1" aria-describedby="emailHelp"  value={userName} onChange={handleUsernameChange}/>
                </div>
            </form>
        </div>
    );
}

export default Login;
```
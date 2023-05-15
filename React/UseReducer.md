# useReducer Hook

1. Import useReducer hook from react.

```js
import React, { useReducer } from "react";
```

2. Initialize useReduce hook inside the comp. function

```js
const [state, dispatch] = useReducer(reducer, initialState);
```

3. state is the current state of the component which accesss the initialState values.

```html
<p>Count is: {state.count}</p>
```

4. dispatch is the function which access the reducer function by using using action value.

```js
dispatch({ type: "Add" });
```

5. Create reducer function which have current state and action as a parameter.

```js
function reducer(currentState, action) {
  switch (action.type) {
    case "Add":
      return { ...currentState, count: currentState.count + 1 };
    default:
      throw new Error("What the fuck you are doing");
  }
}
```

6. Create initialState as an object

```js
const initialState = {
  count: 0,
};
```

---

### Understanding

- state access the initialState Object's values
- dispatch can access the reducer function
- - dispatch sends a object to the reducer which access it using action parameter
- reducer function also have currentState parameter which access the currentState from the component not the initialState from Object

- Full Component below

```js
import { useReducer } from "react";

const initialState = {
  count: 0,
};

function reducer(currentState, action) {
  switch (action.type) {
    case "Add":
      return { ...currentState, count: currentState.count + 1 };
    default:
      throw new Error("What the fuck you are doing");
  }
}
function App() {
  const [state, dispatch] = useReducer(reducer, initialState);

  function Increment() {
    dispatch({ type: "Add" });
  }

  return (
    <>
      <div>
        <p>Count is :{state.count}</p>
        <button onClick={Increment}>add</button>
      </div>
    </>
  );
}

export default App;
```

# Redux

1. Install redux and redux toolkit

```css
npm i redux react-redux @reduxjs/toolkit
```

2. Inside src create a new folder named store and inside this folder create a file name store.js in which:
3. The configureStore is used to create a store which will take all the states or reducer in it

```js
import { configureStore } from "@reduxjs/toolkit";
import colorSliceReducer from "./features/colorSlice";

const store = configureStore({
  reducer: { colorSlice: colorSliceReducer },
});

export default store;
```

4. Inside the store folder create Features folder and inside in it create ColorSlice.js
5. The slices are simple pieces of state management systems of store

```js
import { createSlice } from "@reduxjs/toolkit";

const colorSlice = createSlice({
  name: "colorSlice",

  // InitialState means the current State of Object which is accessed in components by using useSelector hoook
  // InitialState value is manipulated by reducers functions
  initialState: {
    value: { color: "" },
  },

  // reducers are collection of funtions
  // These funcitons have state and actoins
  // In which action insert their payload(data) into state value
  reducers: {
    changeColor: (state, action) => {
      state.value = action.payload;
    },
  },
});

export const { changeColor } = colorSlice.actions; // This will send the reducers funciotns to store.
export default colorSlice.reducer; // this will send the initialState and its value to store.
```

5. Now create a component name ChangeColor.js inside the Component Folder

```js
import React from "react";
import { changeColor } from "../store/features/colorSlice"; // ChangeColor is a function from colorSlice
import { useDispatch } from "react-redux";

const ChangeColor = () => {
  const dispatch = useDispatch(); // This hook used to send data to slice functions payload

  return (
    // This button will dispatch payload having key color and value as red or green inside changeColor reducer
    <div>
      <button onClick={() => dispatch(changeColor({ color: "red" }))}>
        Red Color
      </button>
      <button onClick={() => dispatch(changeColor({ color: "blue" }))}>
        Blue Color
      </button>
    </div>
  );
};

export default ChangeColor;
```

6. Now import this component in any parent component

```js
import React from "react";
import "./App.css";
import Profile from "./components/Profile";
import ChangeColor from "./components/ChangeColor";

function App() {
  return (
    <div className="App">
      <ChangeColor /> // This comp. will alter the data of colorSlice
      <Profile /> // This comp. will get the data of colorSlice
    </div>
  );
}

export default App;
```

7. Now inside the profile component you can access the data of colorSlice

```js
import React from "react";
// useSelector hook is used to fetch the data from store's slice
import { useSelector } from "react-redux";

const Profile = () => {
  const userData = useSelector((reducer) => reducer.userSlice.value);
  const colorData = useSelector((reducer) => reducer.colorSlice.value);

  return (
    <div style={{ color: colorData.color }}>
      <h1>Profile Page</h1>
      <p>Name: {userData.name}</p>
      <p>Age: {userData.age}</p>
      <p>Email:{userData.email}</p>
    </div>
  );
};

export default Profile;
```

# Context API

1. Create a new folder Context under root folder and create a new file a per your Context Feature.
2. This file will work as Provider of context to all its childrens example Theme.js here.

```js
import React, { createContext, useState } from "react";

// Creagte a Context
const ThemeContext = createContext();

// Provider will act a parent to its contexts
const Theme = ({ children }) => {

	// state for darkTheme
	const [darkTheme, setDarkTheme] = useState(false); 

	// Function to toggle Theme
	const toggleTheme = () => {
		setDarkTheme(!darkTheme);
	};

	// Return the ThemeContext.Provider with its values
	// Here Children means all other components inside this component
	return (
		<ThemeContext.Provider value={{ darkTheme, toggleTheme }}>
			{children}
		</ThemeContext.Provider>
	)
};

export { ThemeContext, Theme };
```

3. Now add the ThemeProvider into the parent component as parent provider
```Js
import "./App.css";
import Button from "./Button";
// Importing the ThemeProvider only 
import { ThemeProvider } from "./context/ThemeProvider";
function App() {
	return (
		<div className="App">
			<ThemeProvider>
				<Button />  {/* This will act as Children and can access the ThemeContext */}
			</ThemeProvider>
		</div>
	);
}
export default App;
```
4. Now inside the Children components which wants to access the access the Theme context
```JS
import React, { useContext } from "react";
import { ThemeContext } from "./context/ThemeProvider";
const Button = () => {
	// Accessing the values from ThemeContext
	const { darkTheme, toggleTheme } = useContext(ThemeContext);
	// Now these values can be used in this component
	return (
		<button onClick={toggleTheme}>
			{darkTheme ? "DarkMode" : "LightMode"}
		</button>
	);
};

export default Button;
```

5. Note Theme will act as a Parent of all components which can access ThemContext
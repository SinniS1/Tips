### Darkmode feature

> To create a toggle button which changes the theme of website we need these inside the parent component.
> 1. A useState hook for darkmode.
> 2. A function which can change alter the value of it.
>
> ```js
> // useState hook for darkmode
> const [darkMode, setDarkMode] = useState(true);
> // function which will switch the previous value.
> const toggleDarkMode = () => {
> 	setDarkMode((prevDarkMode) => !prevDarkMode));
> };
> ```
>
> 3. Pass the toggleDarkMode function and darkMode to the components as a prop.
>
> ```HTML
> <!-- Navbar will have toggleDarkMode function to switch as point 4 -->
> <Navbar toggleDarkMode={toggleDarkMode} />
> <!-- Content page will switch its CSS as point 5 -->
> <ContentPage darkMode={darkMode} />
> ```
>
> 4. In the component the button can run it on onClick
>
> ```HTML
> <input type="checkbox" onClick={toggleDarkMode} />
> ```
>
> 5. Now the togleDarkMode will switch the value of DarkMode which can be used to change the css.
>
> ```HTML
> <div className={darkMode ? "darkIntroContent" : "lightIntroContent"} >
> ```
>
> 6. So, if darkMode is true the darkIntroContent CSS will run. If false then lightIntroContent CSS will run.

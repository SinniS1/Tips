### React Router DOM
> ###### Installation
> ```CSS
> npm i react-router-dom
> ```
> ###### Setup
> ``` CSS
> import { BrowserRouter as Router, Routes, Route, Link } from "react-router-dom";
> ```
> ###### simple
> > ``` HTML
> > <Router>
> >    <Navbar />
> >    <Routes>
> >    	<Route exact path="/component" element={<Component } /> />
> >     </Routes>
> > </Router>
> > ```
> ###### Layout setup 
> > - Create a layout component
> > ``` HTML
> > <Navbar/>
> >      <Outlet />
> > <Footer />
> > ```
> > - add the layout component in main page component
> > - the layout page will always run and index route will be primary component
> > ``` HTML
> > <Routes>
> > 	<Route path="/" element={ <Layout/> }/>
> > 		<Route index element={ <Primary-Component/> } />
> >	    	<Route path="/other" element={ <other-component/> } />
> > 	</Route>
> > </Routes>
> > ```

---

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

  --- 
  
  ### Params from URL

> We need to follow these steps to pass the params and get the params from URL in ReactJS.
> 
> 1. We need to have a react-router-dom installed as dependency.
> 
> ```css
> npm i react-router-dom
> ```
> 
> 2. In first component we will import the useNavigate function from react-router-dom.
> 
> ```js
> import { useNavigate } from "react-router-dom";
> const navigate = useNavigate();
> ```
> 
> 3. Inside that component onClick function will run passParma function with two values.
> 
> ```html
> <div onClick={() => passParam(param1, param2)} >
> ```
> 
> 4. passParam function will use nvaigate property to get to that route with our values as params.
>    - Note: navigate property will find PostPage route not the param1 and param2 cause they're dynamic.
> 
> ```js
> const passParam = (param1, param2) => {
> 	navigate(`/PostPage/${param1}/${param2}`);
> };
> ```
> 
> 4. navigate property will run that Route which have one params or more as dyanmic
>    - Note: do not forget to insert -> /: <- before the params
> 
> ```html
> <Route path={`/PostPage/:param1/:param2/`} element={<PostPage />} />
> ```
> 
> 5. Now inside the PostPage component we can get the params value by.
> 
> ```js
> import { useParams } from "react-router-dom";
> let { param1, param2 } = useParams();
> ```
> 
> 6. Now you can use those param1 and param2 in postPage.

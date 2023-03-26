#### React Router DOM
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


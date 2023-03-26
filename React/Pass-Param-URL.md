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

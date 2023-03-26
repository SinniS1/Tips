#### Grid responsiveness
```css
. grid {
	width: 100%;
	display: grid;
	gap: 1rem;
	grid -template-columns: repeat (auto-fill, minmax(100px, 1fr));
	grid-auto-rows: 100px;
}
```

---

#### Clamp responsiveness
###### width: clamp(min-value,relative-value, max-value ); 
``` css
width: clamp(200px,75%, 500px ); 
font-size: clamp(0.75rem, 1.5vw, 2rem),
```

---

#### Bootstrap
 ###### CSS only
  ``` CSS
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet"
  integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
  ```
 ###### JavaScript only
  ``` CSS
  <script defer src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
  integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
  crossorigin="anonymous"></script>
 ```
 
 ---


##### HTML default reset
``` CSS
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
```

---

#### CSS container property
> - container works mostly like a media-query but it triggers when a div as container size is > changed not the view-port size change.
> - Example
> 
> ```HTML
> <div class="super-simple-example" >
>     <div class="container" data -type="'narrow" >
>         <p>Lorem ipsum dolor sit amet.</p>
>     </div>
>     <div class="container" data -type="medium" >
>         <p>Lorem ipsum do lor sit amet.</p>
>     </div>
>     <div class="container" data -type="wide" >
>         <p>Lorem ipsum dolor sit amet.</p>
>     </div>
> </div>
> ```
> 
> - now make all the children inside super-simple-example class as a container.
> - inline-size means only width and size means heigth and width.
> 
> ```CSS
> .super-simple-example > .container{
>     container-type: inline-size;
> }
> 
> @container(width>= 375px){
>     .super-simple-example > .container {
>         background-color: red;
>     }
> }
> 
> @container(width>= 800px){
>     .super-simple-example > .container {
>         background-color: red;
>     }
> }
> ```
> - now whenever size of .container hit the width of 375px or 800px then the css changed.
> - note now we are not dependent on view-port width.

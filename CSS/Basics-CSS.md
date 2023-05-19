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

```css
width: clamp(200px, 75%, 500px);
font-size: clamp(0.75rem, 1.5vw, 2rem);
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
>     container-name: hello;
> }
>
> @container  hello (width>= 375px){
>     .super-simple-example > .container {
>         background-color: red;
>     }
> }
>
> @container hello (width>= 800px){
>     .super-simple-example > .container {
>         background-color: red;
>     }
> }
> ```
>
> - now whenever size of .container hit the width of 375px or 800px then the css changed.
> - note now we are not dependent on view-port width.

### Interserction Observer

1. Import useEffect and useRef hook from react and create a ref.

```js
import React, { useEffect, useRef } from "react";
const userRef = useRef(null);
```

2. Give the parent container or div a ref by using useRef hook

```html
<div ref="{userRef}">{/* Children jsx elements */}</div>
```

2. Create a useEffect in which initialize a new IntersectionObserver function.

```js
useEffect(() => {
  const observer1 = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        // Do something
      } else {
        // Do something
      }
    },
    {
      root: null,
      rootMargin: "0px",
      threshold: 1,
    }
  );
  if (SlidingAnimation) {
    observer1.observe(userRef.current);
  }
  return () => {
    observer1.unobserve(userRef.current);
  };
}, []);
```

3. Now in the useEffect function we can do something when the element is in viewport or not.

4. If you feel confused about the code, you can check the [example 🔗🚀](https://github.com/SinniS1/Copilot/blob/master/src/Components/ContentBlock/ContentBlock.jsx)

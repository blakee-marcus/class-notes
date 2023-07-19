# Use Effect Hook

The `useEffect()` hook is a powerful feature in React that allows you to perform side effects in functional components. Side effects are actions that affect something outside the scope of the component itself, such as fetching data, subscribing to events, or manipulating the DOM.

Read More About Side Effects [here.](./Side%20Effects.MD)

The `useEffect()` hook takes two parameters: a callback function and an optional array of dependencies. Here's the basic syntax:

```javascript
useEffect(() => {
  // Side effect logic goes here
}, [dependencies]);
```

The callback function passed to `useEffect`` will be executed after the component renders. It will run every time the component renders, unless you specify a dependency array.

Here's a breakdown of how the useEffect hook works:

1. **Executing the callback function on mount**: When the component is first rendered, the callback function inside useEffect is executed immediately after the initial render.

2. **Running the cleanup function (optional):** If the callback function returns a cleanup function, it will be executed when the component is unmounted or before the next render (if the dependencies change).

3. **Running the callback function when dependencies change:** If you provide a dependency array as the second argument to useEffect, the effect will only be re-evaluated when the values in the dependency array change. If the dependency array is empty ([]), the effect will only run once, similar to componentDidMount.

4. **Skipping the effect:** If the dependency array is omitted (i.e., not provided as the second argument), the effect will run after every render, causing the callback function to execute on each update.

By specifying dependencies, you can control when the effect should be re-evaluated and avoid unnecessary re-renders.

Here's an example to illustrate how `useEffect` can be used to fetch data from an API:

```javascript
import React, { useState, useEffect } from 'react';

const MyComponent = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      const response = await fetch('https://api.example.com/data');
      const data = await response.json();
      setData(data);
    };

    fetchData();
  }, []); // Empty dependency array, so the effect runs only once on mount

  return (
    <div>
      {data ? (
        <ul>
          {data.map(item => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      ) : (
        <p>Loading...</p>
      )}
    </div>
  );
};

export default MyComponent;
```

The **useEffect** hook is used to fetch data from an API and store it in the component's state using the setData function. The effect runs only once when the component mounts, thanks to the empty dependency array. The fetched data is then rendered in the component.

Remember to import the **useEffect** hook from the react package at the top of your file to use it.
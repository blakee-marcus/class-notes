## GET fetch() ##

In Express.js, a `GET` request can be handled using the `app.get()` method, which is used to bind a callback function to a specific route and HTTP verb. This callback function is then executed whenever a `GET` request is sent to the specified route.

To fetch data from a server using Express.js, you can use the `fetch()` method. Here is an example of how to use `fetch()` to make a GET request to an Express.js server:

```javascript
// Make GET request to /users/:id route
fetch('/users/1')
  .then(response => response.json()) // Parse JSON response
  .then(user => {
    // Use the user data
  })
  .catch(error => {
    // Handle any errors
  })
```
In this example, the `fetch()` method is used to make a `GET` request to the `'/users/1'` route on the server. The `response.json()` method is used to parse the JSON response, and the `.then()` and `.catch()` methods are used to handle the successful response and any errors, respectively.
## POST Request ##

In Express.js, a `POST` request can be handled using the `app.post()` method, which is used to bind a callback function to a specific route and HTTP verb. This callback function is then executed whenever a `POST` request is sent to the specified route.

Here is an example of how to handle a `POST` request in Express.js:

```javascript
const express = require('express')
const app = express()

app.use(express.json()) // Parse JSON body

app.post('/submit-form', (req, res) => {
  // Handle form submission
  // Get data from the request body
  const formData = req.body

  // Process the form data
  // (e.g. save to database, send email, etc.)

  // Send response to client
  res.json({
    message: 'Form submitted successfully!'
  })
})
```

In this example, the `app.post()` method is used to bind a callback function to the `'/submit-form'` route. This function will be executed whenever a `POST` request is sent to this route. The `req.body` property is used to access the data sent in the request body, and the `res.json()` method is used to send a JSON response to the client.

Note that the `app.use(express.json())` middleware is used to parse the JSON body of the request. This is necessary because the `req.body` property will not be populated with the request data unless the body is parsed by this middleware.
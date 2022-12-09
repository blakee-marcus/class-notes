## Body Parsing ##
***

In Express.js, body parsing is the process of extracting the data from the request body and making it available in the request object (`req`) for the route handler to use. This data is typically sent in the request body as a JSON object or as form data (i.e. key-value pairs).

To parse the request body in Express.js, you can use the built-in `express.json()` and `express.urlencoded()` middleware. The `express.json()` middleware parses the request body when the Content-Type is set to application/json, while the `express.urlencoded()` middleware parses the request body when the Content-Type is set to application/x-www-form-urlencoded.

Here is an example of how to use these middleware to parse the request body in an Express.js application:
```javascript
const express = require('express')
const app = express()

// Parse JSON request body
app.use(express.json())

// Parse application/x-www-form-urlencoded request body
app.use(express.urlencoded({ extended: true }))

// Add route handlers
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

In this example, the `app.use()` method is used to add the `express.json()` and `express.urlencoded()` middleware to the application. The `express.json()` middleware is used to parse the request body when the Content-Type is set to application/json, while the `express.urlencoded()` middleware is used to parse the request body when the Content-Type is set to application/x-www-form-urlencoded.

Once these middleware are in place, the route handler for the `'/submit-form'` route can access the data in the request body using the `req.body` property. In this example, the `req.body` property is used to get the form data, which is then processed and used to create a response to send to the client.
**How to Set Up Express.js**
1. Open a terminal or command prompt, and navigate to the directory where you want to create your project.

2. Run the npm init command to initialize a new Node.js project. This will create a package.json file, which contains metadata and dependencies for your project.

3. Run the ``` npm install express ``` command to install the Express.js framework. This will add the express package to the dependencies section of the package.json file.

4. Create a new file called ```app.js```, which will contain the code for your web application.

5. In the ```app.js``` file, import the express module and create an app object using the express function.

6. Define one or more routes for the app object, using the ```app.get```, ```app.post```, ```app.put```, or ```app.delete``` methods. Each route should specify a path and a callback function that will be called when the route is matched.

7. Start the web server by calling the ```app.listen``` method, passing in the port number that you want the server to listen on.  

Here's an example of what the ```app.js``` file might look like, with a single route defined:

```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello, world!');
});
```


**Invoke `app.use()` and serve static files from the `/public` folder**  

To serve static files from the ```/public``` folder using the app.use method, you can use the built-in ```express.static``` middleware function. The middleware function will look for the requested file in the ```/public``` folder, and if it exists, it will serve the file to the client.  

Here is an example of how you might use the ```app.use()``` and ```express.static()``` methods to serve static files from the ```/public``` folder:  
```javascript
app.use(express.static('/public'));
```

**Create a route that will serve up the `public/paths.html` page**  

To create a route that will serve the ```public/paths.html``` page, you can use the ```app.get()``` method to define a route that matches incoming GET requests to the desired URL path, and the ```res.sendFile()``` method to send the HTML file as the response.

Here is an example of how you might use `app.get()` and `res.sendFile()` methods to serve up the `public/paths.html` page:  

```javascript 
app.get('/paths', (req, res) =>
  res.sendFile(path.join(__dirname, 'public/paths.html'))
);
```  

The `res.sendFile()` method takes a path to the file as the argument. In this case, the path is created using the `path.join()` method, which concatenates the path to the current directory (specified by the __dirname global variable) with the path to the `public/paths.html` file. This ensures that the correct path to the file is used, regardless of the current working directory.
## What is the difference between Query and Params? ##
***
### Query ###
In JavaScript, query parameters and URL parameters (also known as route parameters) are used to specify additional information or constraints for an HTTP request. However, they are specified in different parts of the URL, and they are accessed differently in the request object.  
Query parameters are values that are added to the end of a URL path, after a question mark (?). Query parameters are typically used to filter, sort, or paginate the data that is returned in the response. For example, consider the following URL:  
```
https://www.example.com/users?sort=asc&limit=10&page=2
```
In this URL, the sort, limit, and page query parameters are used to specify that the list of users should be sorted in ascending order, limited to 10 results per page, and that the second page of results should be returned.
***
### Params ###
In contrast, URL parameters (or route parameters) are placeholders in a URL path that are used to capture values from the URL. URL parameters are specified using a colon (:) followed by the parameter name, and they are typically used to identify a specific resource or set of resources. For example, consider the following URL:
```
https://www.example.com/users/:userId
```
In this URL, the `:userId` URL parameter is used to capture the ID of a specific user. When this URL is matched, the value of the :userId parameter will be extracted from the URL, and it can be used to retrieve the details of the specified user.  

In JavaScript, query parameters and URL parameters are accessed differently in the request object. Query parameters are typically accessed using the req.query property of the request object, while URL parameters are accessed using the req.params property. For example:
```javascript
app.get('/users/:userId', (req, res) => {
  // Access query parameter
  const { sort } = req.query;

  // Access URL parameter
  const { userId } = req.params;

  // Use the query and URL parameters
  // ...
});
```
In this example, the `req.query` property is destructured to extract the sort query parameter, and the `req.params` property is destructured to extract the userId URL parameter.
**What is Express.js?**  
Express.js is a lightweight framework for Node.js that allows you to write APIs, handle HTTP requests, and implement middleware in your server-side application.

**What are Routes?**  
Routes allow us to send and receive data depending on which route and HTTP method we use. A route can be used for different kinds of requests, to create, read, update, and delete data.  
&nbsp;&nbsp;&nbsp;&nbsp;**Post**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Submits data to the specified resource, often causing a change on the server.  
&nbsp;&nbsp;&nbsp;&nbsp;**Get**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Retrieves a resource from the server.  
&nbsp;&nbsp;&nbsp;&nbsp;**Delete**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Deletes a specified resource.  
&nbsp;&nbsp;&nbsp;&nbsp;**Put**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Replaces a specified resource with a payload.  

**What is a RESTful API?**  
A RESTful API is an API that follows the principles of REST, and provides a set of HTTP methods for creating, reading, updating, and deleting resources. These resources are typically represented by URLs, and the HTTP methods correspond to the standard CRUD (Create, Read, Update, Delete) operations for managing these resources.  

Here are the requirements for a RESTful API:  
* Comprise clients, servers, resources and requests (via HTTP).
* Use stateless communications between client and server.
* Serve cached objects to reduce bandwidth.
* Maintain a uniform interface between the client and the server so that they can evolve separately.
* Optionally, can perform code on demand.  

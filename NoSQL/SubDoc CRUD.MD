# CRUD for Subdocuments #

In Mongoose, subdocuments are a way to include nested documents within a parent document, and CRUD operations can be performed on subdocuments using the methods provided by Mongoose.

Here is a brief explanation of how CRUD operations can be performed on subdocuments using Mongoose:

1. Create: To create a new subdocument, you can use the `push()` method of the array that contains the subdocuments. This method takes an object that represents the new subdocument as an argument.
```javascript
let post = new Post({ title: "My post", content: "Content of my post" });
post.comments.push({ content: "Nice post!", author: "John Doe" });
post.save();
```

2. Read: To read a subdocument, you can access it directly by its index in the array, or you can use the `id()` method to retrieve a subdocument by its _id.
```javascript
console.log(post.comments[0]);
console.log(post.comments.id(post.comments[0]._id));
```

3. Update: To update a subdocument, you can access it directly by its index in the array, or you can use the `id()` method to retrieve a subdocument by its _id and then make the desired changes and call the `save()` method on the parent document.
```javascript
post.comments[0].content = "Great post!";
post.save();

let comment = post.comments.id(post.comments[0]._id);
comment.content = "Great post!";
post.save();
```

4. Delete: To delete a subdocument, you can use the `pull()` method of the array that contains the subdocuments, this method takes an object that represents the subdocument to be deleted as an argument and it can be an object or an _id.
```javascript
post.comments.pull(post.comments[0]);
post.save();

post.comments.pull({_id: post.comments[0]._id});
post.save();
```


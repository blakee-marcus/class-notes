# Subdocuments in Mongoose

In Mongoose, subdocuments are a way to include nested documents within a parent document, this can be useful for modeling one-to-many relationships, where one parent document has many child documents.

To define a subdocument in a Mongoose schema, you can create a separate schema for the subdocument and then include it as a property in the parent schema. Here's an example of how to define a subdocument for "comments" in a "post" schema:

```javascript
const mongoose = require('mongoose');

const commentSchema = new mongoose.Schema({
  content: {
    type: String,
    required: true,
  },
  author: {
    type: String,
    required: true,
  },
});

const postSchema = new mongoose.Schema({
  title: {
    type: String,
    required: true,
  },
  content: {
    type: String,
    required: true,
  },
  comments: [commentSchema],
});

const Post = mongoose.model('Post', postSchema);
```

In this example, the `comments` field in the `postSchema` is an array of `commentSchema` subdocuments, you can use the `.push()` method to add new comments to a post and the `.id()` method to access a specific comment.

```javascript
let post = new Post({ title: 'My post', content: 'Content of my post' });
post.comments.push({ content: 'Nice post!', author: 'John Doe' });
console.log(post.comments[0]._id);
```

It's important to note that Subdocuments are not saved to the database until their parent document is saved, and if the parent document is deleted, the subdocuments will also be deleted. Also, subdocuments don't have their own unique \_id or any other top-level properties, they share the \_id of the parent document.

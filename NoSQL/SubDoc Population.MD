# Populate Subdocuments

In Mongoose, subdocuments are a way to include nested documents within a parent document, but sometimes, it's required to have a direct reference to the subdocument instead of the whole subdocument embedded in the parent document. Mongoose provides the `populate()` method to handle this situation by automatically replacing the subdocument \_id with the referenced document.

To use population, you need to create a reference to the subdocument \_id in the parent schema, then use the `populate()` method to replace the \_id with the referenced document. Here is an example of how to use population to get comments and its author in a "post" schema:

```javascript
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
  },
  email: {
    type: String,
    required: true,
    unique: true,
  },
});
const User = mongoose.model('User', userSchema);

const commentSchema = new mongoose.Schema({
  content: {
    type: String,
    required: true,
  },
  author: {
    type: mongoose.Schema.Types.ObjectId,
    ref: 'User',
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

In this example, the `author` field in the `commentSchema` is an ObjectId that references the `User` schema, now you can use the `populate()` method to replace the \_id with the referenced document.

```javascript
Post.findOne({ title: 'My post' })
  .populate('comments.author')
  .exec((err, post) => {
    if (err) throw err;
    console.log(post);
  });
```

The `populate()` method takes one or more fields to populate as arguments, and it returns a promise or can be passed a callback. Once the population is done, the \_id fields in the comments array will be replaced with the full documents from the User collection.

It's important to note that population can be a complex and costly operation, it generates extra queries to the database, so it's best to use it only when it's necessary and be mindful of the performance implications.

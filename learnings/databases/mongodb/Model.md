
---
- Model takes the [[Schema]] and apply it to the document in  the collection.
- Models are used for all operations on documents like CRUD.
- The model is created using - 
```js
const Blog = mongoose.model("Blog", blogSchema);
```
---
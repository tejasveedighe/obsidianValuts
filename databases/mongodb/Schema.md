
---
- A schema in [[MongoDB]] is a structure of collection documents.
- A [[Mongoose]] schema directly maps the [[MongoDB]] collection.
- This is how a schema is created using [[Mongoose]]:
```js
const BlogSchema = new mongoose.Schema({
	title: String,
	content: String,
	tags: [String]
}, {
	timestamps: true
});
```
---
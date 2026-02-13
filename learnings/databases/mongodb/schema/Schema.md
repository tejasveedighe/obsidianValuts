
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
- Schema can have [[Instance methods]] that can be invoked using the [[Model]].
- Schema also [[Static Methods]]
- Schema also has [[learnings/databases/mongodb/Middleware]]
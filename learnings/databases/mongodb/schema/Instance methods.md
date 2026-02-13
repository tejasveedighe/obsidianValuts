
- The methods can be defined:
```js
	const schema = new mongoose.Schema({
		data: String
	}, {
		// 1. Way of declaring
		// methods object that will hold all the methods
		methods: {
			someMethod(callback) {
				// do something
				return true;
			}
		}
	});

// 2. Way of declaring
// DO not use arrow functions because arrow methods do not bind with the methods.
schema.methods.getSomething = function(callback) {
	// DO something
	return true;
}
```
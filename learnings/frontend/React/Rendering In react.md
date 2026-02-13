
---
- In react the components are first converted to a object, by the bundler. Code optimization and other stuff happens in the background.
- The object gets converted to the syntax that the function `render` expects and then the rendering process is done.
- We can write the component as a function or as a class, it is converted to the object syntax by the bundler.
- `React.createElement()` - this method expects many parameters that are used to create the element.
- All the ways we can create a component in react - 
	1. Regular function -
			```
			function Button(props) {
					return <button>{props.children}</button>
			}
			```
	2. using `function` express -
			```
			const Button = function(props) {
				return <button>{props.children}</button>
			}
			```
	3. Arrow Function - 
			```
			const Button = (props) => {
			return <button>{props.children}</button>
			}
			```
	4. Explicit Return - `let Button = (props) => <button>{props.children}</button>`
	5. Using a Class
			```
			class Button extends React.Component {
				render() {
					return <button>{this.props.children}</button>
				}
			}
			```
	6. Using `React.createElement()` -
			```
			function Button(props) {
				return createElement(
					'h1',
					{ className: 'greeting' }
					'Hello',
					`expression`
				);
			}
			```
- This is the reason that in JSX the evaluated expression is written instead of a expression that is required to be evaluated, as the code is then sent as a object in the bundler and it cannot be parsed as a expression.
---

---
- Terminology - 
- Context - any thing that you want to pass down to the children component. It exists outside the component, de-coupling from the component tree.
```js
import { createContext } from "react";

// This is the value that we want to use in different components of the app.
// in redux this is the store state
// a default value is taken in the hook so that it can be used when the provider does not specify a value to it.
const ThemeContext = createContext("contextValue");
```

> [!NOTE]- Context Provider
>```jsx
>const App = () => {
>
>return <ThemeContext.Provider>
>		<Component1 />
> 	</ThemeContext.Provider>
>}
>```

> [!NOTE]- Context Consumer
>```jsx
>const App = () => {
>
>return <ThemeContext.Consumer>
>	{theme => (
>			<Component1 value={theme} />
>		)
>	} 
>	</ThemeContext.Consumer>
>}
>```

>[!NOTE] useContext Hook
>```js
>	import {useContext} from "react";
>	import { ThemeContext } from "../ThemeContext";
>	const Component1 = () => {
>		const theme = useContext(ThemeContext);
>		return <div className={theme}>Box</div>
>	}
>```

--- 
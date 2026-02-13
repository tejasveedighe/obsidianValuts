
---
- A partial class is a class that is defined using the keyword `partial`. 
- The partial classes are classes whose definition can be broken into different files, such that multiple developers can work on the same class at the same time.
- The partial class definitions are combined at compile time, resulting in one single class.
- The `partial` keyword tells the compiler that the class can be defined in other parts of the namespace.
- Restrictions of Partial Class - 
	- All the class definitions must be defined with the `partial` keyword.
	- Nested Partial Types are allowed.
	- All the parts of partial class must be defined in the same assembly and the same module.
	- The `partial` keyword must be used before the `class` keyword.
	- All parts must have the same access modifier.
	- If any part of class if defined `abstract` will make the entire class as abstract.
	- All the parts must specify the same parent class, or else case of multiple inheritance will occur and dotnet does not support it.
- A partial class may contain Partial Methods.
	- Rules -
	1. Partial Methods cannot have the keywords - `virtual`, `abstract`, `override`, `new`, `sealed`, or `extern` modifiers.
	2. Partial Methods can only have a void return type.
	3. Partial Methods must be declared inside partial class or partial structs.
	4. Partial Methods must have the same signature as of its implementation and of its declaration.
	5. Partial Method can have only one declaration and one implementation.
---
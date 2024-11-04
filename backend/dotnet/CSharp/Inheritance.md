
---
- Inheritance is the consumption of the properties and methods or behaviors of parent class by child class.
- Inheritance is done by `Class Child : Parent` ':' is used to derive the class when declaring the child class.
- Inheritance has the following rules :
	1. The constructor must be `public` as the child cannot inherit the private properties and methods of parent.
		-  The constructor is called when the child class is instantiated, as the initialization of properties is done in the parent constructor and only after that the consumption in the child object is possible.
	2. Parent class Cannot access the methods of child class.
	3. Reference variable
		- The **reference variable of the parent** class **will not be able the access the methods defined purely in the child class**.
		- ` Parent p = new Child(); `
		- The reference is pointing to a memory location of the child class. It does not have any memory allocated to itself.
	4. Object class is the base class of every object. It is the default base class, and the members are the accessible to all the child classes.
			- The `System.Object` is the namespace for the object class.
	1. Multiple and Hybrid Inheritance is not allowed in C#.
	2. If the parent class has parameters
		- We have to call the parent class constructor using the base keyword likeso:
		- `public Child(int num) : base(num) {}` to send `num` as the argument to the parent class constructor.
- Types of Inheritance:
	1. [[Single Inheritance]]
	2. [[Multiple Inheritance]] -> not supported
---
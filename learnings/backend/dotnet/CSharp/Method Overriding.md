
---
- The process of re-implementing the `virtual` method of parent class in its derived class, such that the method signature remains same and using the keyword `override`.
```
class Parent {
	public virtual void Show() {
		Console.WriteLine("Show Of Parent");
	}
}
class Child : Parent {
	public override void Show() {
		Console.WriteLine("Show Of Child");
	}
}
class Program {
	public static void Main() {
		Parent p = new Child();
		p.Show(); // the child class method is run
	
		Parent p2 = new Parent();
		p2.Show(); // the parent class method is run

		Child c = new Child();
		c.Show(); // the child class method is run
	}
}
```
- The above code has method overriding taken place, where the parent class show method is overridden in the child class.
- The method that is found in the definition is ran that the CLR finds using the reference variable.
- When the reference variable does not have the method defined, it looks for the method in its parent class, if the method is not found in parent then the compile time error is produced, else the method of the parent is run.
- The dynamic polymorphism happens when the method is invoked at runtime, the CLR will find the method in the child first and then in the parent method, the method when overridden is invoked, as the memory of the child class is stored in the parent class variable.
---
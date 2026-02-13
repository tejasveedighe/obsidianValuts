
---
- It is the same as method overriding where the parent class method is reimplemented in the child class with the same signature, but instead the method can be `virtual` , even if the method is not virtual we can implement method hiding.
- Method hiding is done by using the `new` keyword in the derived class method signature.
```
class Parent {
	public void Show() {
		Console.WriteLine("Show of parent");
	}
}
class Child : Parent {
	public new void Show() {
		Console.WriteLine("Show of child");
	}
}
class Program {
	public static void Main() {
		Parent p = new Child();
		p.Show(); // parent class method is called

		Parent p2 = new Parent();
		p2.Show(); // parent class method is called

		Child c = new Child();
		c.Show(); // child class method is called
	}
}
```
- The only difference here is that when the parent reference object is used with the child memory then the parent method is called instead of the child method, as the method is pure method defined in child class.
- The parent class cannot access the child method as the method even when hidden in the child class is considered as pure method of child. And pure methods cannot be accessed by the parent class.
- So the CLR finds the method implementation in child class but as the parent reference is used, it cannot access that child method, then the CLR finds the method implementation in the parent class and executes it.
---
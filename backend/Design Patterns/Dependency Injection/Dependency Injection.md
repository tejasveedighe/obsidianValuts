
---
- It is a software design pattern that is used to achieve [[Inversion of Control (IoC)]].
- The [[.NET]] supports Dependency Injection.
- Dependency 
	- A dependency is a object of a class that is required by another object.
- [[backend/dotnet/ASP.NET Core/ASP.NET Core MVC/Services|Services]] are injected using DI.
---
- Problems that occur when not using DI and instead directly creating the object in the required class
```cs
///
/// <summary>
/// This is the dependency class
/// </summary>
///
public class Dependency {
	public void Method(string message) {
		Console.WriteLine(message);
	}
}
```
- The above class is required by some dependent class:
```cs
///
/// <summary>
/// The Dependent class directly creates the object of /// Dependency and manages it itself. 
/// </summary>
///
public class Dependent {
	public Dependency Dep = new();

	public void PerformAction() {
		Dep.Method("Jeep");
	}
}
```
- When the implementation of `Dependency` class changes, the entire code in the `Depenent` class will need to be updated.
- The `Dependency` and `Dependent` are both tightly coupled. They will require changes as one changes, the other is also forced to change.
- This causes unmaintainable code for large code bases and so DI is required.
---
#### How DI Addresses these problems 
- Using interface or base class to abstract the implementation of dependency.
- The [[.NET]] service container contains all the services, `IServiceProvider`.
- The Dependencies are injected via constructor.
---
#### [[Dependency Resolution]]
---
#### [[Multiple Implementation Services]]
---
#### [[Keyed Services]]
---
#### [[Services Lifetime]]
---

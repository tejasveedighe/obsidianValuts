
---
- When the a dependent class has more than one constructor that are requesting different dependencies like so:
```cs
public class DependentClass {
	public DependentClass(IService s1) {
		...
	}

	public DependentClass(IDifferentService s2) {
		...
	}
}
```
- The Following is the `Program.cs` where the dependencies are registered:
```cs
builder.Services.AddTransient<IService, Service>();
```

> [!caution]+
> Here the `IDifferentService` is not registered.

- The [[Dependency Container]] will not resolve the `IDifferentService` as it is not registered and then will call the first constructor in the class that requires the `IService` dependency.
- 

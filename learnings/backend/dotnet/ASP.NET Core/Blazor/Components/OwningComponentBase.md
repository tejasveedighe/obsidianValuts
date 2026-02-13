
---
- The `OwningComponentBase` is derived from `ComponentBase` and [[IDisposable]]
- It is used to insert transient and scoped services in Blazor Applications with the proper lifecycle as declared in the dependency injection.
- The services that are added using this class are created and destroyed according to the component lifecycle, this becomes very helpful as the garbage is cleared and no reason for memory leak are present.
---
- Usage: 
	1. `OwningComponentBase ` -> this will provide  the ` ScopedService ` Property of the component as the DI Container where all the services are available and can be accessed.
```cs
@inherits OwningComponentBase

---

public partial class ComponentName : OwningComponentBase
{
	void SomeFunction() {
		var data = ScopedService.GetRequiredService<IServiceType>().Get();	
	}
}
```
 
 2. `OwningComponentBase<ServiceType>` -> this will set the `Service` Property to the `ServiceType` service object.
```cs
@inherits OwningComponentBase<AppDbContext>

---

public partial class ComponentName : OwningComponentBase<AppDbConttext>
{
	void SomeFunction() {
		var data = Service.TableName.ToList();
	}
}
```
---
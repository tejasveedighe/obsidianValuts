
---
- Consider the following services - 
```cs
public class ImageUpload : IUpload {...}
public class FileUpload : IUpload {...}
```
- These are registered in the DI container -
```cs
builder.Services.AddTransient<IUpload, ImageUpload>();
builder.Services.AddTransient<IUpload, FileUpload>(); 
```
- The second service when added ==Overrides== the first service of the `IUpload` service type.
	- The order of the service matters.
- To get all the services that are registered in the [[DI Container]]
```cs
public class Dependent {
	public Dependent(IEnumberable<IUpload> services){
		// here the services contains all the services that have the service type of `IUpload`.
	}
}
```
- The services in the Enumerable will be according to the order that they were added.
---

---
- Blazor Application allows to add services as dependency for its components.
- The services can be simply used as services are used in dotnet applications.
> [!warning] The default injection way through constructor does not work in Blazor.
- To inject the service in the component - 
	
	- `@inject` followed by the service name in the razor file to inject the service to the component.
	- ```[Inject]``` can be used to insert the service in the class of component.
```cs
[Inject] // WILL only Work with Properties not with class Attribute.
private IServiceType ServiceName { get; set; }
```
- --
- The difference is when these services are used in a [[Web Assembly]] project.
	- The services that are added to the web assembly project are not available on the server, so pre-rendering won't work.
	- The services are called on while pre-rendering and the runtime error is produced:
		-  `InvalidOperationException: Cannot provide a value for {PROPERTY} on type '{ASSEMBLY}}.Client.Pages.{COMPONENT NAME}'. There is no registered service of type '{SERVICE}'.`
		
> [!info] Usage Guide
> - Remove Pre-rendering of component
> - Make the service available in the server or main project and make sure it is available at the time of pre-rendering.

---
- Services in Blazor do not follow the same lifecycle as of the services declared  in ASP. NET Core applications. The difference is of the garbage collection. [[Service Lifetime]]

---
- Used for dependency injection directly to the endpoint method of a [[backend/dotnet/Api Controllers/Controllers|Controller]]
- The following is the method for using [FromServices] attribute.
```cs
[ApiController]
[Route("api/[controller])]
class MyController : ControllerBase 
{
	[HttpGet]
	public IActionResult Get([FromServices] IDependencyContract contractInstance) {
		contractInstance.DoSomething();
	}
}
```
---
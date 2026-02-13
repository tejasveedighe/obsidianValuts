
---
- When the user makes a request, it is first intercepted by the middleware.
- The middleware based on the routing used (conventional or attribute) it will select the correct action method to call.
- The middleware makes an instance of the selected controller. It uses the concept of reflection.
- The IControllerActivator interface is used that provides the following methods - 

> [!NOTE IController Implements]
> 	1. object Create(ControllerContext context): Used to create a controller, context is used to call the method.
> 	2. void Release(ControllerContext context, object controller): Used to release the controller. The controller parameter is used to know which controller to release.
> 	3. valueTask ReleaseAsync(ControllerContext context, object controller): same as Release but does it asynchronously.

- The IControllerActivator interface is implemented by the class DefaultControllerActivator.
- In ASP.NET Core Application there can be many Middleware components. Each component has its use.

- app.Run(async delegate (HttpContext context) => { ... }) // used to run the middleware
- app.Use(async delegate (HttpContext context, RequestDelegate next) => { ... }) // used to run a middleware but also receives the request delegate that is used to chain more middlewares together.

- Custom Middleware classes
	- Non-Conventional class - 
		- To create a custom middleware class implement the IMiddleware interface.
		- To add this middleware it has to be added as a [[learnings/backend/dotnet/ASP.NET Core/ASP.NET Core MVC/Services]] to the WebBuilder before it is build. `builder.Services.AddTransient<CustomMiddlewareClass>();`
			- The InvokeAsync(HttpContext context, RequestDelegate next); will be called
		- `app.UseMiddleware<CustomMiddlewareClass>();`
	- Conventional Middleware class - 
		- Add from the add item menu a middleware class, that will add a conventional class.
		- This middleware class can be directly accessed using the name of extension method without adding it to the web builder dependency.

---
### .NET Core Overview
- Is a new version of .NET framework, which is a general purpose development platform for all OS.
- Applications like:
	1. Mobile
	2. Desktop
	3. Web
	4. Cloud
	5. IoT
	6. Machine Learning
	7. Microservices
	8. Game etc
- Cross Platform ASP.NET core
	- Internal Server - *Kestral*
	- Web Servers -
		- Linux/Mac OS - *Nginx/Apache*
		- Windows - *IIS*
			

- ASP.NET Core vs ASP.NET MVC vs APS.NET Web Forms

| Core                                                  | MVC                                                                                           | Web Forms                                                                   |
| ----------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Used to build moden, internet-connected applications. | Used to separate the three component Model, View and Controller in building web applicaitons. | Original Framework for building web applications with server side controls. |
|                                                       |                                                                                               |                                                                             |


### .NET Core Features
- One unified programming model for MVC and Web API.
- Is the next version of Asp.Net 4.x
- MVC and Web API can use the core for creating the APIs.
- Both MVC and Web API controller class can inherit from same Controller Base class and returns IActionResult.
`IActionResult {`
	`ViewResult();`
	`JsonResult();`
`}`
- Has inbuilt support for dependency injection.
- Testability is easy
- Cross Platform
- Open-source
- Modularity
	- With Middleware components
	- request and response pipelines are composed with middleware components

### Life Cycle of Request
1. [[Middleware]]
	- Middleware componet forms the basic building block of the application HTTP pipileine.
	- There are a series of components that are combined to form a request pipeline in order to handle any incoming request.
2. [[Routing]]
	- Routing is a middleware component that implements MVC framework.
	- The routing middleware component decides how an incoming request can be mapped to Controllers and action methods, with the help of convention routes and attribute routes.
	- The Controllers and action variables are placeholders that are replaced by matching segments of the URL.
	- Routing in MVC -
		a. Convention Routing -
			- This routing uses application wide patterns to match a different URL to various controller action methods.
			- Convention Routes represent default possible routes that can be defined with the help of controller and action methods.
		b. Attribute Routing -  
			- This type of routing is implemented through attributes and applied directly to a specific controller or action method.
			- The convention routing methodoloy is implemented inside startup.cs file.
3. Controller Initalization
	- The process of initialization and execution of controllers take place.
	- Controllers are responsible for handling the incoming requests.
	- The controller selects the appropriate action methods on the basis of route templates provided.
4. [[Action Methods]] Execution
	- After the controllers are initialized, the action methods are executed and returns a view which contains HTML document to be returned as reponse to the browser.
5. Result Execution
	- The response generated to the original HTTP request is executed.
	- If an action method returns a view result, the MVC view engine renders a view which contains HTML response.
	- If result is not of view type, then the action method generates its own response.
### [[Dependency Injection]]
- Is a design pattern concept that is used to reduce coupling and modularization of components within an application.
- The concept is to invert the creation and management of objects and give it to a external service common to all components.
- Container or DI container, is reponsible for creating and providing the instances of the required classes to the components that need them.
- ASP.NET has it inbuilt.
---
Continue With: [[ASP.NET Core MVC]]
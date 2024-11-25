---
tags:
  - Backend
---

Start With: [[ASP.NET Core]]

---
### **MVC:**
	1. Model
		1. Represents the data and business logic of the application.
		2. Consists of data transfer objects (DTOs), data access layer logic, and service layers.
		3. Responsible for accessing and storing data and the associated logic.
		4. It contains the classes that manage the data in memory and the logic to handle the data.
			1. It is accessible by both controller and view.
			2. It passes the data from controller action method to view.
	2. View
		1. Handles the presentation layer of the application.
		2. It usses the Razor view engine to embed .NET code with HTML.
		3. Responsible for displaying the application's user interface.
		4. It renders the model data to the user interface in HTML.
			1. cshtml page is created.
			2. It has only responsibility to render data.
			3. Request to view data can be made from a controller.
	3. Controller
		1. Acts as an intermediary between the Model and View.
		2. Processes incoming requests manipulates data using the Model, and renders the final output to view.
		3. Each controller action typically corresponds to a specific operation and view.
		4. It handles the HTTP request from client.
		5. Inhertied from System.Web.Mvc.Controller
### **File Structure of MVC:**
	1. Connected Services 
		1. Contains all the references of services that are added to the project.
	2. Dependencies 
		1. Contains all the references of NuGet packages added to the project.
		2. Runtime libraries and packages are listed here.
	3. Properties 
		1. Contains launchSettings.json file
		2. json file contains all the information required to launch the application.
	4. wwwroot
		1. Contains all the static files required by the project.
		2. CSS, JS and external libraries like bootstrap, JQuery are kept in this folder.
	5. Controllers 
		1. All controllers that are required by the project are stored here.
		2. Each controller file has a controller sufix to its name.
	6. Models
		1. All entity classes are stored here.
	7. Views
		1. It contains the cshtml files here.
	8. Program.cs
		1. It is the entry point of the web application.
### Web App setup
```
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddMvc(); // adds the MVC architecture to the app

builder.Serivces.AddControllersWithViews(); // adds the controllers, has all the options enabled.

var app = builder.Build();

app.UseRouting(); // matches a request to an endpoint
app.UseEndpoints(endpoints => {
	endpoints.MapDefaultControllerRoute(); // used to tell the app to map the controllers view to the routes.
}); // executes the matched endpoint
```
### [[backend/dotnet/ASP.NET Core/ASP.NET Core MVC/Controllers]]
### [[Action Methods]]
### [[Middleware]]
### [[Passing Data from Controller to View]]
- ViewBag -
- ViewData
- ViewModel
- TempData
### [[Routing]]
### [[Views]]
### [[Authorization]]
### [[State Management]]

---


### Findings in MVC
- Routing -
	- Routes are like so in MVC - https://localhost:3000/{ControllerName}/{ActionName}/{id?}
		- Controller Name is the name of controller file that we want to associate with this route
		- Action Name is the method name that we want to call for this particular route.
		- id is optional parameter that can be accessed by the action method when in passed.
- Views
	- Tags Helpers -
		- Examples of Tag helpers -
			- asp-controller="Home"
			- asp-action="Privacy"
		- They enable server side code to render the HTML code.
- IActionResult 
	- It is a generic return type that implements all the return types.
	- It is used when multiple result types are possible in a single action method.
- Application Db Context
	- It is used to create a db context for the application.
	- It contains the configuration that we can add to the web application builder object to add the db context.
	- It is used to run migrations and connection to the database.
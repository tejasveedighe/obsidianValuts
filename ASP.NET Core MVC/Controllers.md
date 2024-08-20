
---
- Controllers handle the request made by user.
- The controllers are classes that are inheriting from System.Web.Mvc.Controller class.
- The Controller class is inherited from ControllerBase class.
- It uses WebFormViewEngine to render ASP.NET page.
- ASP.Net maps requested URLs to classes, these classes are called as controllers.
- Controllers handle all business and logical operations, with user input.
- It has all the [[Action Methods]]
- Add MVC controller - 
	1. MVC Controller - Empty: It will create a empty controller.
	2. MVC Controller with read/write actions: Creates a controller with 5 methods to CRUD and List entries using Entity Framework.
	3. MVC Controller with views, using Entity Controller: Creates an MVC controller with actions and Razor Views to CRUD and List Entries using Entity Framework.
- *Naming a controller-*
	1. "Controller" Suffix added to the name.
	2. Inheriting from the Controller or ControllerBase class.
---
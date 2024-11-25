
---
- [[backend/dotnet/ASP.NET Core/ASP.NET Core MVC/Controllers]] can have multiple actions.
- Controller Actions - 
	1. Action Methods - Methods that respond to HTTP requests. The method name becomes the action name.
	2. Routing - Routing maps request to appropriate action.
	3. Action Results - returns IActionResult, represents various HTTP responses.
- Request Structure: " http://domainName.com/ControllerName/ActionMethodName "
- Return Type of Action Methods -
	1. IActionResult: Represents the result of a action method.
	2. ActionResult: Default Implementation of IActionResult.
	3. ContentResult: Represents a text result.
	4. EmptyResult: Represents an ActionResult that will do nothing.
	5. JsonResult: Action Result that formats the object in JSON format.
	6. PartialViewResult: Represents a action result that renders a partial view to the response.
	7. ViewResult: Represents an ActionResult that renders a view to the response.
	8. ViewComponentResult: An IActionResult which renders a view component to the response.
	9. FileResult: Represens a file download response. Can be used to return files for downloading at client side.
	10. NotFoundResult: 404
	11. BadRequestResult: 400
	12. StatusCodeResult: Represents a response with a specific HTTP status code. Custom code and messages can be returned.
	13. ObjectResult: Represents a response with a arbitrary object. It used with Content Negotiation to automatically select the appropriate response format (JSON, XML etc) based on client preferences.
	14. RedirectResult: Represents a response that redirects to a specific route.
	15. RedirectToActionResult: More flexible way to specify an action and controller instead of a URL.
- IActionResult Vs ActionResult -
	- IActionResult - When some custom response and inbuilt response is returned.
	- ActionResult - When only inbuilt type of result need to be sent.
---
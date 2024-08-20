
---
- To pass data between the [[Controllers]] and its views the following are used in the [[Controllers]] as well as [[Action Methods]].
### ViewData
- ViewData is a MVC dictionary object that allows to pass the data between the controller action method to view.
- It is a property of Controller class. It implements IDictionary<string, object>
- ViewData does not persist between requests, so it must be used only for current request.
- Usage - @ViewData["KeyName"]
- Returns null if the keyname is invalid, incoorect casting will cause runtime error. 
### ViewBag
- It is also a dynamic property of controller abstract method.
- Usage - @ViewBag.KeyName
- returns null for incorrect key name, no error compile-time error checking.
### TempData
- Implements the ITempDataDictionary interface.
- It is a very short lived instance, it should be used between current and the subsequent requests only.
- Usage - TempData["PropName"]
- It can be used for the next request too. It is present for the entire User session. So redirect will not clear the TempData.
- It will clear after the subsequent request is completed it is its default behaviour but can be saved.
	- Keep(string key?) - method to retain the value of the key, or all the keys.
	- Peek(string key) - to get the method instead using the indexer, it will retain the key value for the subsequent request.
### View Modal
- Using View(object) to send the modal the Strongly typed object that it will accept.
- @model ClassOfObject - used at the top of the View code to make it strongly typed.
	- When passing some data in View(obj) method, use the reference in View of the same type
	- `@model List<string>`  reference at the top of view file.
		- Then it can be accessed using the Model in the view.
- @Model.Property - to use the property value in View
---

###
---

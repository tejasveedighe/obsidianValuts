
---
- The forms in Blazor Server are created using the following - 
	- `EditForm` -> it is a form tag that is used to Server side forms, where the form is submitted in the server itself.
		- Each form that the server handles requires a `FormName` attribute so that it can be identified.
	- `InputText` -> used as input element under the `EditForm`
	- `SupplyParameterFromFormAttribute` -> The tag is used to mark the property that the `EditForm` is using to get the data. It binds that property to the form.
- External Links - 
	- [https://jonhilton.net/blazor-ssr-forms/]
---
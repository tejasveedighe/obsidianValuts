
---
#### Layout View
- Common view for all routes.
- `@RenderBody();` is used to render the content for that specific route. It injects the HTML code in that position as the routes change.
- `@{ Layout = "filePath" }` can be used to change the layout for that page.
#### Section
- We can sections to a view using `@RenderSection(sectionNameString, required: bool);` it will render the section that is defined with the same name.
	- If required is false then it will not render if it is not defined. Else it will throw error if section is not defined.
	- `@RenderSectionAsync(name, required);` does the same thing asynchronously.
- Section can be view specific we can define a section like so:
	- `@section SectionName {...}`
#### View Start
- `_ViewStart.cshtml` file is used to set the common settings for all the views.
	- Suppose `Layout = "layout.cshtml"` has to be defined in all the views of the app.
	- It is redundant code and will cause maintenance problems.
- In `ViewStart.cshtml` we can define the `@ { Layout = "layout.cshtml" ` that will be common to all the views where the Layout is not explicitly set.
- Hierarchy of view start file - 
	- If place in same directory as a view, it will be applied to that view.
	- If the view does not have a view start in the same directory the engine will look into view's parent directory.
	- Root directory - The ViewStart in Views folder will be used for all the subdirectories views.
#### View Imports
- `_ViewImport.cshtml` file is used to set the common namespaces, directives, and other elements to multiple views.
- Directives that can used to add elements -
	1. @using: to add namespaces
	2. @inject: to inject services from dependency injection container.
	3. @model: to add model to the view (strongly typed view).
	4. @addTagHelper: to add tag helper.
	5. @removeTagHelper: to remove a tag helper.
	6. @tagHelperPrefix: sets a prefix that can be used in tag helper attributes.
- Hierarchy of view import files -
	1. Application level
	2. Area level
	3. Controller level
	4. View level
#### [[Partial Views]]

---
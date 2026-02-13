
---
- Each Component is derived from [[ComponentBase]]
- The components in blazor are small pieces of code that can be reused and combined to create UIs.
- Blazor allows the components to have a different interactivity based on the interactivity that is set globally or per component using the `@rendermode`.
- Components have their [[Component Lifecycle]].
- Components also can be used with their [[References]]
- Parent and Child component can share the data using the following - 

> [!example]- Using  `CascadingStateProvider`
> 

> [!example]+ Parameter Attribute 
> - `[Parameter]` attribute can be used in a child component to set the property as a parameter that the parent component is passing down.
> ```razor
> // From Parent component razor
> <ChildComponent Name="Name"/>
>
> // Component Class
>public partial class ChildComponent {
>	[Parameter]
>	public string Name { get; set; } = string.Empty;
>}
>```

> [!example]- Using `@bind-{paramName}` Directive
> - Binding the parameter to the child component using the `@bind-` directive works similarly as passing the parameter, except that the child component also gets an additional parameter of type `EventCallback<parameterType>` that will be used to update the parameter.
> ```razor
> // In Parent component
> <ChildComponent @bind-Name="Name"/>
> @code {
> 	public string Name {get;set;} = "Tejasvee";
> }
> // In Child Component Class
> public partial class ChildComponent {
> 	[Parameter]
> 	public string Name {get;set;} = string.Empty;
> 	[Parameter]
> 	public EventCallback<string> NameChanged {get;set;}
> }
> ```

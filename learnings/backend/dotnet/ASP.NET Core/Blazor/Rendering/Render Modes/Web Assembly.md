- This is the client based render mode.
- In this mode the application uses the browser web assembly to run the entire app on the client.
- The complete app downloads in the browser, with all its dependencies, that might take time and also uses more resources of the client.
- This mode is interactive as the app does not have to make any request it can handle the interactions directly.
- This mode can be used for when the application has to be used in semi-online modes as it can be used without any internet. The data is with the client and so no need for communication.
---
- To add web assembly in the blazor app -
```cs
builder.Services.AddRazorComponents()
	.AddInteractiveWebAssemblyComponents();
---
app.MapRazorComponents<App>()
	.AddInteractiveWebAssemblyRenderMode();
```
---
- To add Interactive Web Assembly Mode in specific component/page:
```cs
@rendermode InteractiveWebAssembly
// OR
@rendermode @(
	new InteractiveWebAssemblyRenderMode(prerender: false)
)
```
--- 
> [!caution]
Web Assembly Mode will only work when the component/page is in the Client Project. Else it will throw an exception that the component cannot be found.


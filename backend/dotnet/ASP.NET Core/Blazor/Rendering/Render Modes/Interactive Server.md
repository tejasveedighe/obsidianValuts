- This mode is used to create interactive server generated pages/components.
- This mode allows to add interactivity to the site.
- The interactions made by the client are transported to the server, the server receives the interaction and updates the HTML DOM and resends the page with the changes.
- When the interactivity is communicated the server calculates the `DOM DIFF` for the component and sends that back in the response.
- The communication is done via `WebSockets`.
- ---
- To add Interactive Server Mode to the Blazor Application the following services are required - 
```cs
builder.Services.AddRazorComponents()
	.AddInteractiveServerComponents();

---

app.MapRazorComponents<App>()
	.AddInteractiveServerRenderMode();
```
---
- To make a specific component or page interactive:
```cs
@rendermode @(new InteractiveServerMode(prerender: false))
// OR
@rendermode InteractiveServer
```
---
- The server has to keep track of all the active components.
- The components are active until the session is active, as soon as the client changes tab or stays inactive for too long the server closes the connection to reduce the load from the server.
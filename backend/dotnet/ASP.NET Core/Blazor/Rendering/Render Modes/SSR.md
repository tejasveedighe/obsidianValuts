- Static Server Site Rendering
- It is used for sending static non-interactive HTML pages to the client, the server generates the HTML and sends it.
- It has no interactivity and is only used to show data.
- To add SSR in Blazor App -
```cs
builder.Services.AddRazorComponents();
---
app.MapRazorComponents<App>();
```
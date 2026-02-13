
---
- The JS Code can be called from .NET code using the `IJSRuntime` abstraction.
- The `IJSRuntime` has to be injected in the component before usage.
- The JS call ==cannot== be made from the page with [[Prerendering]].
- 
---
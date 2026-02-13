
---
- In Blazor the service lifetime is not same as of the Non-Blazor apps.
- In Non-Blazor Applications the [[learnings/backend/dotnet/ASP.NET Core/ASP.NET Core MVC/Services|Services]] are disposed after the request completes. The scoped, transient services are disposed by the DI system.
- In [[Blazor Server]] the services are not disposed until the circuit ([[SignalR]] ) is not completed. This causes the service to have longer lifecycle that the component itself.
- Transient services that ==are NOT== implementing [[IDisposable]] are [[Garbage Collection|garbage collected]]. 
- Transient services that ==are== implementing [[IDisposable]] are ==NOT== [[Garbage Collection|garbage collected]]. These services are maintained by the [[DI Container]] while the circuit is not complete.
- In Client side that does not use circuit for the interaction the DI container also does not dispose the service, at the end of component lifecycle.

> [!info] Alternative Approaches
>- Use [[OwningComponentBase]]  
>- Use `IServiceProvider`


---
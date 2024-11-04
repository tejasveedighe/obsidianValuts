- There are 3 ways to add a service to the app.
- These 3 methods differ with the lifecycle of that service
1. [[ Transient Lifetime ]] - 
	- A new service will be created every time a the service is required.
2. [[Singleton Lifetime]] - 
	- The service is created once for the entire lifetime of the application.
3. [[Scoped Lifetime]] - 
	- The service is created for each scope.
	- In a application when a HTTP request is made a [[HttpContext]] is created which has the information of the request.
	- The lifetime of a scope is equivalent to the lifetime of a HTTP Request.
	- Services with registered scope lifetime will be maintained and used during the lifetime of the scope they have been created in.
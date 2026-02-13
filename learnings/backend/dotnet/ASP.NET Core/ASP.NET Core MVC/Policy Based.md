
---
- Policy uses claims for authorization
```
builder.Services.AddAuthorization(options => {
	options.AddPolicy("PolicyName",
		policy => policy.RequireClaim("Admin"));
});
```
---
---
tags:
  - Backend
---

---
- Tag helpers are used to enable server-side code to create and render HTML elements in Razor pages.
- Anchor Tag Helper Attributes - 
	- asp-controller -
	- asp-action - 
	- asp-route-{value} -
	- asp-route -> for creating link to named route
	- asp-all-route-data -> is used to creation of dictionary of key-value pairs.
```
@{
var parms = new Dictionary<string, string>
            {
                { "speakerId", "11" },
                { "currentYear", "true" }
            };
}

<a asp-route="speakerevalscurrent"
   asp-all-route-data="parms">Speaker Evaluations</a>
```

- 
---
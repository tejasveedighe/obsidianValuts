
---
- Asp.Net Core Identity is -
	- Is an API that supports user interface UI login functionality.
	- Manages users, passwords, roles, claims, tokens, email confirmation etc.
	- In Short [[Authorization]] and Authentication.
- Component of Identity - 
	- Identity Core components - 
		- UserManager - CRUD for users
		- RoleManager - CRUD for roles
		- SignInManager - signin and out, two factor auth and external auth
	- Data Models - 
		- IdentityUser - all common properties
		- IdentityRole - role id and name
	- IdentityDbContext - context class that handles the db context of identity data.
- Difference between AddIdentity and AddIdentityCore - 

| AddIdentity                                                                                                   | AddIdentityCore                                            |
| ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Adds all the features of identity system, including role, user management and signin manager with UI support. | Adds only the core features such as User and Role manager. |
| Is used for setting up cookies, tokens for authentication and authorization.                                  | Is used to only add basic authentication to app.           |
|                                                                                                               |                                                            |
- UserManager Class - 
	- Is a generic class and can work with a TUser class that is inheriting from IdentityUser.
---
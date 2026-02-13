
---

- localdb instance are user specific, they stop and start when a user is using or when kept idel.
- iis hosting does not work with localdb as the instance keeps stopping.
- the application pool must be in the no managed code clr version.
- change the identity of application pool to localsystem.
- use the sqllocaldb info dbname cmd to get the status
- copy the pipeline name and paste it in the connection string of the app
- create a login with the NT Authority/System to be the owner of the db
- now restart the app.

---

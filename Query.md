
---
- To execute Query from the DBContext we can use the following methods - 

|        Method         | Introduced  |        Parameter Handling        | Safety Against SQL Injection |                                        Usage Example                                         |
| :-------------------: | :---------: | :------------------------------: | :--------------------------: | :------------------------------------------------------------------------------------------: |
|       `FromSql`       | EF Core 7.0 |  Supports parameterized queries  |             Yes              | `context.Customers.FromSql("EXEC GetCustomers @param1", new SqlParameter("@param1", value))` |
|     `FromSqlRaw`      | EF Core 3.0 | Requires manual parameterization |       Depends on usage       |       `context.Customers.FromSqlRaw("SELECT * FROM Customers WHERE Name = {0}", name)`       |
| `FromSqlInterpolated` | EF Core 3.1 |   Automatically parameterizes    |             Yes              |   `context.Customers.FromSqlInterpolated($"SELECT * FROM Customers WHERE Name = {name}")`    |

---
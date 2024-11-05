
---
- `async` and `await` keywords are used in [[C-Sharp]] to use [[Asynchronous Programming]].
- `async` and `await` are used with [[Task]] to create [[Asynchronous Programming|Asynchronous]] methods.
- `async` is used with method signature to tell the compiler that the method has a `await` operation and the method is using [[Asynchronous Programming]]. 
- `async` and `await` **do not cause** additional threads to be created.
- 
---
- The `await` keyword - 
	- The `await` keyword will make the thread wait till the operation is completed.
	- Until the operation that has been `awaited` is not complete the thread will not move forward.
```cs
Coffee coffee = new Coffee();
Console.WriteLine("Coffe Done!");

Task<Egg> eggTask = FryEggAsync();
Egg egg = await eggTask;
Console.WriteLine("Eggs Fried!");

Task<Bacon> baconTask = FryBaconAsync();
Bacon bacon = await baconTask;
Console.WriteLine("Bacon Fried!");

Task<Toast> toastTask = ToastBreadAsync();
Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("Bread Toasted");

Console.WriteLine("Breakfast is Ready!!");
```
- The above code performs the same as the synchronous code.
- As each step is awaited the operations will be done one by one.
- Instead the following is the correct way of using `await`:
```cs
Coffee coffee = new Coffee();
Console.WriteLine("Coffe Done!");

// All the tasks have started here.
Task<Egg> eggTask = FryEggAsync();
Task<Bacon> baconTask = FryBaconAsync();
Task<Toast> toastTask = ToastBreadAsync();

// Until the task is not done don't move forward.
// But awaiting and then starting operation is not happenind, the other operations are already working concurrently.
Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("Bread Toasted");

Egg egg = await eggTask;
Console.WriteLine("Eggs Fried!");

Bacon bacon = await baconTask;
Console.WriteLine("Bacon Fried!");

Console.WriteLine("Breakfast is Ready!!");
```
![Async Task](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/media/asynchronous-breakfast.png)

---

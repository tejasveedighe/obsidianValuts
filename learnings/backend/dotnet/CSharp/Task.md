
---
- Tasks are part of [[Task asynchronous programming model]].
- Tasks are used with [[Asynchronous Programming]].
---
- [[Async & Await in dotnet]]
- ---
- Compositions -
	- `Task` - returns a Task type.
	- `Task<TResult>` - returns a Task that returns `TResult` type of result on completion.
---
- Uses
	- I/O Bound Code
		- Use `Task` or `Task<TResult>` inside a `async` method.
	- CPU Bound Code
		- These tasks are run on a [[Background Thread|background thread]] with `Task.Run(...)`;
- Here are two questions you should ask before you write any code:
	1. Will your code be "waiting" for something, such as data from a database?
	    - If your answer is "yes", then your work is **I/O-bound**.
	2. Will your code be performing an expensive computation?
	    - If you answered "yes", then your work is **CPU-bound**.

- If the work you have is **I/O-bound**, use `async` and `await` _without_ `Task.Run`. You _should not_ use the Task Parallel Library.

- If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await`, but spawn off the work on another thread _with_ `Task.Run`. If the work is appropriate for concurrency and parallelism, also consider using the [Task Parallel Library](https://learn.microsoft.com/en-us/dotnet/standard/parallel-programming/task-parallel-library-tpl).
---
| Use this... | Instead of this... | When wishing to do this... |
|---|---|---|
| `await` | `Task.Wait` or `Task.Result`  | Retrieving the result of a background task|
|`await Task.WhenAny`|`Task.WaitAny`|Waiting for any task to complete|
|`await Task.WhenAll`|`Task.WaitAll`|Waiting for all tasks to complete|
| `await Task.Delay` | `Thread.Sleep` |Waiting for a period of time|

---
- 
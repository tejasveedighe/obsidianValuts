
---
- Delegates are used for dispatching and working with events in dotnet.
- Delegates are type-safe function pointers. They hold the reference to a function and then call the method for execution.
- `public delegate void DelegateName(params)`; are how the delegates are declared.
- Any method with the same signature can be assigned to the delegate. Either instance or static method both can be assigned.
- Multiple methods of same signature can be assigned to delegate and they can be the implementation of callback or iterative calls to various methods.
- the `delegate` is a abstract class
	- it has two properties -
		- `public MethodInfo Method {get;}` - used to get the information of the delegate.
		- `public object Target {get;}` - used to get the class instance that the method belongs to, incase of static method this property returns `null`.
	- it has the method -
		- `public virtual Delegate[] GetInvocationList()` - returns the list of delegates that the current delegate represents.
- Multi Caste Delegate Base Class - 
	- `MulticasteDelegate` inherits from `Delegate`class
- How to use Delegates - 
	- We cannot directly inherit from the Multi Caste Delegate class or Delegate class, we need to use delegate class and it will automatically create a delegate class instance.
	- Steps to use - 
		1. Declare the delegate signature 
			- `public delegate void WorkPerformerHandler(int hours, WorkType workType);`
		2. Create the Handler Method with the same signature as the delegate
			- `public static void Manager_WorkPerformed(int workHours, WorkType wType) {}`
		3. Creating the instance of Delegate
			- `WorkPerformerHandler del1 = new WorkPerformerHandler(Manager_WorkPerformed);`
- Invoking A Delegate - 
	1. `delegateName(params);`
	2. `delegateName.Invoke(params);`
- Types of Delegate on base of Caste - 
	- Single Caste Delegate
	- [[Multi Caste Delegate]]
- Also There are [[Generic Delegates]]
---
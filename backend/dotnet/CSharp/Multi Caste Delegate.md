
---
- They are used to call multiple handler methods one by one.
- They are called in the same order as they are added to the delegate.
- If the delegate have a return type the last functions return value will be returned, the old value will get replaced.
- Ways to create a multi caste delegate - 
	1.  Using +
		- `public delegate void DelegateName(int a, int b)`
		- `DelegateName d = new DelegateName(func1);`
		- `d += func2;`
	2. Adding Multiple Delegate
```
	DelegateName d1 = new DelegateName(func1);
	DelegateName d2 = new DelegateName(func2);
	DelegateName d3 = new DelegateName(func3);
	DelegateName d4 = new DelegateName(func4);		
	DelegateName final = d1 + d2 + d3 + d4;
```

---
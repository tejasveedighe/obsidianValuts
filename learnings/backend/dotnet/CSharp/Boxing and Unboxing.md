
---
- Boxing is the process of wrapping a value type into a object type, that is managed by heap.
	- The heap used to store is garbage collected heap.
	- The results is a reference is created on the heap, pointing to the value.
	- It is implicit.
```
	int i = 123;
	object x = i;	
```
- Unboxing is the reverse of boxing where the object type is converted back to its value type.
	- It is explicit.
```
	o = 123;
	i = (int)o;
```
---
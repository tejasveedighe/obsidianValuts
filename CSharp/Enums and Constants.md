
---
- Enums
	- Are known as enumeration.
	- named constants are stored in enums, the contants are called as enumerators.
	- Enum are named constants that start from 0 and increment one by one.
```
	Enum Days {
		Mon, Tue, Wed, Thur, Fri, Sat
	};
	Console.WriteLine(Days.Mon); // prints Mon
	Console.WriteLine((int)Days.Mon); // prints 0
```

- The value of the enums are increasing from the value of the previous enum, we can also specify the value of a enum constant and the enums after that will have a value increased from that value.
```
Enum Day {
	Monday = 5,
	Tue
};
Console.WriteLine((int)Day.Tue); // prints 6
```
- Reference for Enums
	- https://www.c-sharpcorner.com/UploadFile/f0b2ed/understanding-enums-constants-in-C-Sharp/
---
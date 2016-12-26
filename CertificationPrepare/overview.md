## Topics 
* Primitive/Wrapping class
* Exception
* File IO
* Inheritance (interface and abstract)
* Modifiers
* Initialization order

## Primitive/Wrapping class
### Integer
Integer is immutable object. 
Code snippet: 
```
		Integer x = 100;
		Integer y = x;
		x++;    // a new Integer object is constructed 
		System.out.println(x==101);	// true
		System.out.println(x==y);	// false
		System.out.println(y);	// 100
```

### String 
1. split() method. 
Code snippet: 
```
    String str= "She sells sea shells.";
    System.out.println(Arrays.toString(str.split("\\s")));	// space
    String inputString = "a1b2c3";
    System.out.println(Arrays.toString(inputString.split("\\d")));	// digit
    System.out.println(Arrays.toString(inputString.split("\\d", 2)));	// digit
```


## What is the output of the code snippet? 
```
		Integer x = 1000;
		long y = 1000;
		Integer zz = 1000;
		System.out.println(x==y); 	  // unboxing happens, true
		System.out.println(x == zz);  // false
		System.out.println(x >= zz);  // unboxing, no compile error, true
```


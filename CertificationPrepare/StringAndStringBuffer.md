## What is the [output?](http://stackoverflow.com/questions/2012305/comparing-stringbuffer-content-with-equals)
```
StringBuffer sb1 = new StringBuffer("Java");
StringBuffer sb2 = new StringBuffer("Java");
System.out.println(sb1 == sb2); // Reference equality
System.out.println(sb1.equals(sb2));
```
Both false. 

Reason: There is no overriden `equals()` for Stringbuffer class. 

## What is the output?
```
	String s1 = null;
		String s2 = null;
		if (s1 == s2)
			System.out.print("A");
		if (s1.equals(s2))
			System.out.print("B");
   ```
A and then an java.lang.NullPointerException. 

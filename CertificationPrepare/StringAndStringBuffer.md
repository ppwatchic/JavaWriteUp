## What is the [output?](http://stackoverflow.com/questions/2012305/comparing-stringbuffer-content-with-equals)
```
StringBuffer sb1 = new StringBuffer("Java");
StringBuffer sb2 = new StringBuffer("Java");
System.out.println(sb1 == sb2); // Reference equality
System.out.println(sb1.equals(sb2));
```
Both false. 

Reason: There is no overriden `equals()` for Stringbuffer class. 



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
	if (s1.equals(s2))	// Exception Here
		System.out.print("B");
   ```
A and then an java.lang.NullPointerException. 
Reason: `s1` is null then there is exception when it invokes any method on String class. 

## [Pattern](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)
1. What will be the output? 
```
	Pattern p = Pattern.compile("[a-f]\\d+");
	Matcher m = p.matcher("ab34ef0");
	while(m.find()) {
		System.out.print(m.start()+" "+m.group());
	}
```
**Output**: `1 b345 f0`. 
**Explanation**: 
* `[a-f]`: a through f (both inclusive). 
* `\\d`: a digit 0-9. 
* `+`: one of ther greedy quantifiers. one or more times. 
* For `start()` of Matcher class, it starts from **1**. 

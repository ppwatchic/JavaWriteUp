## Topics 
* Util class
* Primitive/Wrapping class
* Exceptions
* File IO
* Interface and Abstract class
* Modifiers
* Initialization order

## Util class
1. Locale  
There are 4 ways to create a Locale object. 
Code snippet: 
```
	Locale loc = new Locale("en", "US");	// constructor
	Locale loc2 = Locale.forLanguageTag("en-US");	// factory method
	Locale loc3 = new Locale.Builder().setLanguage("en").build();	// Builder
	Locale loc4 = Locale.ENGLISH;	// Locale constants
```

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

### Interface
1. How to access interface constant variable?
Code snippet: 
```
interface DoSomeStuff {
	public static final int STUFF = 3;
	
	void doStuff(int t);
}

public class TestDeclare {

	public static void main(String[] args) {
		int x = 5;
		new TestDeclare().doStuff(x++);
	}
	
	void doStuff(int s) {
		s += DoSomeStuff.STUFF+ ++s;
		System.out.println("s " + s);
	}

}
```

### Abstract class
1. NumberFormat is an abstract class. It has no public constrcutor; instead use factory method to create an object of this class.   
Code snippet: 
```
	NumberFormat nf = NumberFormat.getInstance(Locale.ITALY);
	String s = nf.format(123.45);
	System.out.println(s);
```

## Exceptions
1. ParseException
Code snippet: 
```
	NumberFormat numf = NumberFormat.getInstance(Locale.US);
	Number N;
	String ns = "123.4567";
	numf.setMaximumFractionDigits(2);
		
	try {
		N = nf.parse(ns);
		System.out.println(N);
	} catch(ParseException ne) {
		System.out.println("Exception");
	}
```
